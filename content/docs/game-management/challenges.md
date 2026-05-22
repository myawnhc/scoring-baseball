---
title: "Challenges"
weight: 30
description: "How to score replay challenges in baseball — manager challenges of on-field calls and ABS challenges of ball/strike calls, and how they appear on the scorecard."
---

# Challenges

Instant replay came to MLB in 2008 for home run calls and expanded to most reviewable plays in 2014. In 2026 the league added a second flavor: **Automated Ball-Strike (ABS)** challenges, letting batters, pitchers, and catchers contest individual ball/strike calls in real time. Both kinds can change the scoring of a play, so when they happen, you need to note them.

## How MLB Replay Review Works

There are two distinct challenge systems in today's game.

### Manager Challenges (on-field plays)

When a manager disagrees with an umpire's call on the field, they request a review. Play stops, the call goes to the Replay Operations Center in New York, and umpires review the video. Reviewable calls include:

- **Force/tag plays** at any base — safe vs out (stolen bases, force outs, tag plays at home)
- **Catch / no-catch (trap)** in the outfield
- **Fair / foul boundary** balls down the lines
- **Home-run boundary** calls — over the fence, off the wall, or a ground-rule double
- **Hit by pitch** — was the batter actually struck by the ball
- **Touching a base** / leaving early on a tag-up (appeal plays)
- **Fan interference**, **stadium boundaries**, **collision rules** at home plate, **slide-interference (Chase Utley) rules**

Each manager gets one challenge per game; teams keep their challenge if the call is overturned (so a team that wins challenges can keep going). Umpires can also initiate **crew chief reviews** on their own for certain plays.

The result is one of two outcomes:

- **Overturned** — the original call was wrong. The play is corrected: an out becomes a safe call (or vice versa), runners may be repositioned, a catch becomes a trap, a fair ball becomes foul.
- **Upheld** (or "stands" / "confirmed") — the original call holds. The challenging team loses their challenge.

A call that "stands" means there wasn't clear evidence to overturn it; a call that's "confirmed" means the video clearly supported the original. For scoring purposes both mean the same thing: the original call remains.

### Automated Ball-Strike (ABS) Challenges

Starting in 2026, MLB lets batters, pitchers, and catchers challenge ball/strike calls. ABS challenges work very differently from manager challenges:

- The player must signal (helmet/cap tap) **within roughly two seconds** of the pitch — no delay allowed.
- Only one of three players — the **batter, pitcher, or catcher** — can initiate. The manager cannot.
- The challenge is resolved **instantly** by the computerized strike-zone system. No replay center, no delay.
- Each team gets **two challenges per game**; teams keep them on overturns.

An ABS overturn changes a pitch from a ball to a called strike (or vice versa). That can have downstream effects on the count and the at-bat: a 3-1 ball becomes 3-2 strike, an apparent walk on ball four becomes a still-live at-bat, an apparent strikeout becomes a still-live at-bat with a ball added.

## Noting a Challenge on a Paper Scorecard

There's no universally standardized notation for challenges — they're a recent addition to the game and scoring conventions vary. Use whatever works for you. A few approaches scorers use in practice:

- A small **"Ch"** (or **"R"** for Review) somewhere on the play — in the corner of the at-bat cell, near a pitch in the pitch sequence, or next to a fielding notation
- For an **upheld** challenge, you might mark just "Ch" since nothing actually changed
- For an **overturned** challenge in pencil, erase the original and write the corrected scoring (with optional "Ch" annotation)
- For an **overturned** challenge in ink, you could strike through the original scoring and add the corrected version, perhaps as "Ch <new scoring>" — the strike-through preserves the history of what was first called

The right answer is whatever lets you read the scorecard later and understand both what happened and that a review took place. Many casual scorers don't note challenges at all if the corrected scoring is already on the card.

## In BaseballScorer

BaseballScorer handles each challenge type with its own UI path. ABS challenges produce a visible mark in the pitch-dot sequence (circled pitch or capsule); Manager challenges produce a small **"Ch" badge** in the top-leading corner of the at-bat cell.

### ABS (Pitch) Challenge

After recording a pitch or play, a **Pitch Challenge** button appears in the review panel. Tap it to open a Challenge Result alert with three options:

- **Overturned** — the call is reversed. The original pitch stays visible (as a hollow dot) and the corrected pitch appears next to it.
- **Upheld** — the original call stands. The team loses their challenge.
- **Cancel** — you tapped the button by accident; nothing changes.

![Challenge Result dialog with Overturned, Upheld, and Cancel options](/images/screenshots/challenge-dialog.jpg)

**Visual notation in the pitch sequence:** Challenges leave a distinct visual mark in the pitch dot display. Both upheld and overturned challenges are circled so you can spot them at a glance.

**Upheld challenge:** The original pitch dot is circled — the call was reviewed but stands unchanged. Here, a called strike was challenged and upheld:

![Pitch dots showing an upheld challenge — the called strike dot is circled](/images/screenshots/challenge-upheld.jpg)

**Overturned: ball becomes strike.** The original ball appears as a hollow green circle (voided), followed by the corrected called strike (filled orange dot). Both are enclosed in a capsule:

![Pitch dots showing an overturned challenge — hollow ball dot and filled strike dot in a capsule](/images/screenshots/challenge-overturned-ball-to-strike.jpg)

**Overturned: strike becomes ball.** The original called strike appears as a hollow orange circle (voided), followed by the corrected ball (filled green dot). Both are enclosed in a capsule:

![Pitch dots showing an overturned challenge — hollow strike dot and filled ball dot in a capsule](/images/screenshots/challenge-overturned-strike-to-ball.jpg)

The key idea: nothing is erased. The original call is always visible as a hollow circle so you can read exactly what happened — what was called, that it was challenged, and what it became. Your pitch sequence tells the full story.

### Manager Challenge (play challenges)

For on-field replay challenges — safe/out at a base, catch/trap, fair/foul, HR boundary, stolen-base reversal — open the at-bat in the review panel (tap its cell on the scorecard, or scroll back to it in the inning column). Next to the **Pitch Challenge** button you'll see a **Manager Challenge** button. Tap it to open the Manager Challenge sheet:

<!-- TODO: Screenshot of Manager Challenge sheet showing outcome picker, team picker, optional note -->

The sheet has three fields:

- **Outcome** — Upheld or Overturned (segmented picker)
- **Challenging Team** — Home or Away (defaults to the batting team of the play; flip if the defense challenged)
- **Note (optional)** — free-form text like "trap call", "missed tag at second", "fair down the line". The note appears in the inning summary alongside the play.

Tap **Confirm** to record the challenge.

**Upheld**: the challenge events are recorded against the at-bat, the challenging team's remaining-count decrements, and you're done. Nothing else changes — the original call stands.

**Overturned**: the challenge events are recorded, and you then use the existing **Edit Scoring** flow (or the runner-event editor) to enter the corrected scoring. For example:

| Original call | Overturned to | Edit you make |
|---|---|---|
| Flyout (catch) | Single (trap) | Edit Scoring → change result type to single |
| Out at 1B (groundout) | Safe (infield single) | Edit Scoring → change result type to single |
| Home run | Ground-rule double | Edit Scoring → change result type to double |
| Caught stealing | Safe (steal) | Review the at-bat's runner events → delete the CS event, add a steal event |
| Steal | Caught stealing | Review the at-bat's runner events → replace the steal with a CS |

**Scorecard badge:** an at-bat with a resolved Manager challenge shows a small **"Ch"** badge in the top-leading corner of the cell. (ABS challenges do *not* get this badge — the pitch-dot capsule / circle already conveys them.) The badge tells you a Manager challenge happened on this play; the note (in the inning summary) and the corrected scoring tell you the rest.

**Challenge status bar:** A persistent indicator shows how many challenges each team has remaining, broken out by pool — e.g., `ABS 2/2 • Mgr 1/1`. The two pools are separate in MLB 2026: each team gets **2 ABS challenges** and **1 Manager challenge** per game. Teams keep a challenge on an overturn (so a successful challenge doesn't decrement the remaining count); an upheld challenge consumes it. The status bar updates automatically when a challenge is resolved.

<!-- TODO: Screenshot of challenge status bar showing remaining challenges for each team -->

**Known limitation: real-time challenges of runner events (CS, pickoff, thrown out).** A caught-stealing or pickoff call lands on the *currently in-progress* at-bat — the one being pitched at the time. The Manager Challenge button lives on the *completed* at-bat's review panel, so there's no entry point until that batter finishes. By then, subsequent plays (especially a home run) may have produced side-effects that don't cleanly reconcile when the runner event is flipped after the fact. **Workaround:** if a real-time runner-event challenge happens during a live game, score it immediately as the *corrected* outcome (e.g., record the steal as safe rather than a CS), and use a play note to record that a challenge was made. The Manager Challenge button + "Ch" badge will then be missing for that play. A dedicated real-time challenge entry point is planned for a future release.

**Known limitation: overturns that revert to a still-live at-bat.** Some manager challenges put the at-bat back to in-progress rather than to a different final outcome — the most common is a home run overturned to a foul ball (the count goes back to where it was, the batter is still up). BaseballScorer's Edit Scoring picker today only offers terminal at-bat outcomes, so this case has no clean in-app path. **Workaround:** use single-at-bat **Undo** to roll back the entire at-bat, then re-pitch from the corrected count. You'll lose the "Ch" badge in this case (it's tied to the at-bat that no longer exists), so jot a manual note in the inning if you want to record that a challenge happened. This is rare in practice — most challenges produce a different terminal outcome, not a return to a live at-bat.

---

Challenges are relatively rare, but they can significantly change the scoring of an inning — especially if an overturned call puts a runner on base who later scores. Recording them accurately ensures your scorecard tells the true story of what happened.

---

*See also: [Pitch Tracking]({{< relref "/docs/pitches/pitch-tracking" >}}) | [Stolen Bases]({{< relref "/docs/runners/stolen-bases" >}})*
