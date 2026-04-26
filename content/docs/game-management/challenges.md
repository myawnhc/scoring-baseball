---
title: "Challenges"
weight: 30
description: "How to score replay challenges in baseball — overturned and upheld calls, and how they appear on the scorecard."
---

# Challenges

Instant replay came to MLB in 2008 for home run calls, and expanded to most reviewable plays in 2014. Today, each manager gets one challenge per game (teams keep their challenge if the call is overturned). Umpires can also initiate reviews on their own for certain plays. It doesn't happen on every play, but when it does, you need to note it on the scorecard.

## How MLB Replay Review Works

When a manager disagrees with a call — typically a safe/out call at a base, a catch/trap call in the outfield, or a fair/foul boundary — they can request a review. Play stops, the call goes to the Replay Operations Center in New York, and umpires review the video. The result is one of two outcomes:

- **Overturned** — the original call was wrong. The play is corrected: an out becomes a safe call (or vice versa), runners may be repositioned.
- **Upheld** (or "stands/confirmed") — the original call holds. The challenging team loses their challenge.

A call that "stands" means there wasn't clear evidence to overturn it. A call that's "confirmed" means the video clearly supported the original call. For scoring purposes, both outcomes mean the original call remains — the distinction is subtle and usually doesn't affect what you write down.

## Noting a Challenge on the Scorecard

There's no universally standardized notation for challenges — they're a recent addition to the game and scoring conventions vary. A common approach:

- Circle or annotate the pitch/play dot with a small **"Ch"** or **"R"** (for Review)
- For an **upheld** call: draw a small ring around the play dot to indicate it was reviewed but unchanged
- For an **overturned** call: show the original call as a hollow (open) circle alongside the filled corrected result — both circled together in a capsule

Since challenges typically happen on bang-bang plays — stolen base attempts, tag plays, force outs — the notation usually lives in the baserunner path on the mini diamond or next to the fielding notation in the cell.

## In BaseballScorer

BaseballScorer integrates challenge tracking directly into the pitch-by-pitch flow.

After recording a pitch or play, a **Challenge button** appears. Tap it to trigger a challenge alert with three options:

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

**Challenge status bar:** A persistent indicator shows how many challenges each team has remaining. In a standard MLB game, that starts at one per team and goes to zero after an upheld challenge. The status bar updates automatically when a challenge is resolved.

<!-- TODO: Screenshot of challenge status bar showing remaining challenges for each team -->

Challenges are relatively rare, but they can significantly change the scoring of an inning — especially if an overturned call puts a runner on base who later scores. Recording them accurately ensures your scorecard tells the true story of what happened.

---

*See also: [Pitch Tracking]({{< relref "/docs/pitches/pitch-tracking" >}}) | [Stolen Bases]({{< relref "/docs/runners/stolen-bases" >}})*
