# Cloudflare Pages Preview Deploy

Goal: serve unreleased doc changes (e.g., the `1.3-preview` branch carrying
docs for the next app release) from a separate URL, without touching the
GitHub Pages production deploy at `scoring.theyawns.com`.

## One-time setup

1. **Cloudflare account.** If you don't already have one,
   [sign up](https://dash.cloudflare.com/sign-up/pages) — free tier covers
   static-site preview deploys.

2. **Connect the GitHub repo as a Pages project.**
   - Dashboard → Workers & Pages → **Create** → **Pages** (important: not
     Workers — see the gotcha below) → Connect to Git
   - Authorize GitHub, pick `myawnhc/scoring-baseball`
   - Project name: `scoring-baseball` (this becomes the `*.pages.dev`
     subdomain)

   **Gotcha**: the Cloudflare dashboard's Create flow funnels you toward
   Workers by default. If you end up with a Workers-style project, the
   deploy step runs `npx wrangler versions upload`, which serves a
   default "Hello, World" page instead of your assets and is a pain to
   reconfigure. Delete and recreate as Pages explicitly.

3. **Configure the build.**
   - **Production branch:** the branch whose latest deploy you want at
     the bare `<project>.pages.dev` URL. Either:
     - Set to your current preview branch (e.g., `1.3-preview`) so the
       bare pages.dev URL serves the unreleased docs, or
     - Set to `main` and use Cloudflare's per-branch preview URLs for
       unreleased branches.
   - **Framework preset:** Hugo (Pages preinstalls Hugo and reads
     `HUGO_VERSION`).
   - **Build command:**
     ```
     hugo --gc --minify --baseURL "$CF_PAGES_URL/"
     ```
     `$CF_PAGES_URL` is supplied per-deploy by Cloudflare; using it as the
     `baseURL` keeps canonical/og:url tags pointing at the right preview
     domain instead of the production `scoring.theyawns.com`.
   - **Build output directory:** `public`
   - **Environment variables:**
     - `HUGO_VERSION = 0.160.1` (match `.github/workflows/hugo.yml`)
     - `TZ = America/New_York` (optional)

   *Fallback if Hugo preset breaks*: if Cloudflare's framework preset
   regresses and runs `npx hugo` (it isn't an npm package), drop the
   preset to "None" and replace the build command with an explicit
   download:
   ```
   curl -fsSL "https://github.com/gohugoio/hugo/releases/download/v0.160.1/hugo_extended_0.160.1_linux-amd64.tar.gz" | tar -xzf - hugo && ./hugo --gc --minify --baseURL "$CF_PAGES_URL/"
   ```
   Use the lowercase `linux-amd64` artifact name (renamed from
   `Linux-64bit` around Hugo v0.103). Hard-code the version — shell
   variable assignments in Cloudflare's build-command field don't
   reliably persist.

4. **Branch deploys.**
   - Project → **Settings → Builds & deployments → Configure preview
     deployments**
   - Choose **All non-Production branches** so Cloudflare auto-builds
     any branch you push.
   - Each push to a non-production branch publishes at
     `https://<branch>.<project>.pages.dev` (with `<branch>` slugified).

5. **Switching the production branch later.**
   - Changing the production-branch setting in Cloudflare does NOT
     auto-trigger a build with the new branch. To make the change
     visible at the bare pages.dev URL, either:
     - Push any commit (an empty `git commit --allow-empty` works) to
       the new production branch to force a rebuild, OR
     - In the Deployments tab, find an existing build on that branch
       and **⋯ → Promote to production**.

6. **Optional: custom subdomain.**
   - Project → Custom domains → Add `next.scoring.theyawns.com` (or
     similar).
   - Cloudflare shows the CNAME target to add at your DNS provider
     (WordPress DNS for `theyawns.com`).
   - Once DNS propagates, the preview URL is stable across pushes.

## Per-release flow

1. Create a branch `<version>-preview` (e.g., `1.3-preview`) off `main`
   in `scoring-baseball`.
2. Push doc updates for the unreleased app version.
3. Cloudflare auto-deploys to a preview URL.
4. Share the URL in the TestFlight changelog.
5. After the app ships and the docs are public, merge
   `<version>-preview` into `main`. GitHub Pages picks up the change
   for production at `scoring.theyawns.com`.

## Important: don't change the production GitHub Pages workflow

The current `.github/workflows/hugo.yml` deliberately does NOT pass
`--baseURL`; it relies on `hugo.toml`'s `baseURL = "https://scoring.theyawns.com/"`.
That's load-bearing — overriding it in the workflow once caused HTTP
canonicals (GitHub Pages `Enforce HTTPS` was off at the time) and broke
Google Search Console validation (commit `b680c13`).

Cloudflare Pages overrides `baseURL` per-deploy via the build command
above. The two systems coexist cleanly:
- **GitHub Pages on `main`** → uses `hugo.toml`'s baseURL → production site
- **Cloudflare Pages on any branch** → uses `$CF_PAGES_URL` → preview site
