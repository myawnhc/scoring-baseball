# Cloudflare Pages Preview Deploy

Goal: serve unreleased doc changes (e.g., the `1.3-preview` branch carrying
docs for the next app release) from a separate URL, without touching the
GitHub Pages production deploy at `scoring.theyawns.com`.

## One-time setup

1. **Cloudflare account.** If you don't already have one,
   [sign up](https://dash.cloudflare.com/sign-up/pages) — free tier covers
   static-site preview deploys.

2. **Connect the GitHub repo.**
   - Dashboard → Workers & Pages → Create → Pages → Connect to Git
   - Authorize GitHub, pick `myawnhc/scoring-baseball`
   - Project name: `scoring-baseball` (this becomes the `*.pages.dev`
     subdomain)

3. **Configure the build.**
   - **Production branch:** `main` *(optional — see below)*
   - **Framework preset:** None (the "Hugo" preset on the newer Cloudflare
     build image (v2) tries to run `npx hugo`, which fails because Hugo
     isn't an npm package. Selecting "None" + an explicit download-and-run
     command is the reliable path.)
   - **Build command:** download Hugo, then build with the per-deploy URL:
     ```
     HV=0.160.1 ; curl -sL "https://github.com/gohugoio/hugo/releases/download/v${HV}/hugo_extended_${HV}_Linux-64bit.tar.gz" | tar -xzf - hugo && ./hugo --gc --minify --baseURL "$CF_PAGES_URL/"
     ```
     `$CF_PAGES_URL` is supplied per-deploy by Cloudflare; using it as the
     `baseURL` keeps canonical/og:url tags pointing at the right preview
     domain instead of the production `scoring.theyawns.com`.
   - **Build output directory:** `public`
   - **Environment variables:**
     - `TZ = America/New_York` (optional, matches workflow)
     - The Hugo version is pinned inside the build command above; no
       `HUGO_VERSION` env var needed.

   *Alternative:* if Cloudflare exposes a "Build system v1" toggle in
   the project's Build & deployments settings, switch to it — v1 ships
   Hugo preinstalled and the build command simplifies to
   `hugo --gc --minify --baseURL "$CF_PAGES_URL/"`.

4. **Branch deploys.**
   - In project settings → Builds & deployments → Configure preview deploys
   - **All non-Production branches** → enable preview deploys (Cloudflare
     will auto-build any branch you push)
   - Every push to `1.3-preview` will then publish at
     `https://1.3-preview.scoring-baseball.pages.dev` (or similar)

5. **Optional: custom subdomain.**
   - In project settings → Custom domains → Add a domain
     `next.scoring.theyawns.com` (or `preview.scoring.theyawns.com`)
   - Cloudflare shows the CNAME target to add at your DNS provider
     (WordPress DNS for `theyawns.com`)
   - Once DNS propagates, the preview URL is stable

## Per-release flow

1. Create a branch `<version>-preview` (e.g., `1.3-preview`) off `main`
   in `scoring-baseball`.
2. Push doc updates for the unreleased app version.
3. Cloudflare auto-deploys to `<branch>.scoring-baseball.pages.dev` (or
   the custom subdomain if set up).
4. Share the URL in the TestFlight changelog.
5. After the app ships and the docs are public, merge `<version>-preview`
   into `main`. GitHub Pages picks up the change for production.

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
