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
- For an **overturned** call: show the original call (crossed out or open) alongside the corrected result

Since challenges typically happen on bang-bang plays — stolen base attempts, tag plays, force outs — the notation usually lives in the baserunner path on the mini diamond or next to the fielding notation in the cell.

<!-- TODO: Screenshot of scorecard cell showing challenge notation for upheld vs overturned call -->

## In BaseballScorer

BaseballScorer integrates challenge tracking directly into the pitch-by-pitch flow.

After recording a pitch or play, a **Challenge button** appears. Tap it to trigger a challenge alert with three options:

- **Overturned** — the call is reversed. The pitch or play result is removed and replaced with the corrected outcome.
- **Upheld** — the original call stands. The team loses their challenge.
- **Cancel** — you tapped the button by accident; nothing changes.

<!-- TODO: Screenshot of the challenge alert with the three options -->

**Visual notation in the pitch sequence:** Challenges leave a distinct visual mark in the pitch dot display.

- An **upheld** challenge shows the original pitch dot with a ring around it — the dot is unchanged but visually flagged as reviewed.
- An **overturned** challenge shows the original (hollow) dot alongside the corrected (filled) dot in a connected capsule — you can see both what was called and what it became.

<!-- TODO: Screenshot of pitch dot row showing upheld (dot with ring) and overturned (capsule with hollow + filled dot) -->

**Challenge status bar:** A persistent indicator shows how many challenges each team has remaining. In a standard MLB game, that starts at one per team and goes to zero after an upheld challenge. The status bar updates automatically when a challenge is resolved.

<!-- TODO: Screenshot of challenge status bar showing remaining challenges for each team -->

Challenges are relatively rare, but they can significantly change the scoring of an inning — especially if an overturned call puts a runner on base who later scores. Recording them accurately ensures your scorecard tells the true story of what happened.

---

*See also: [Pitch Tracking]({{< relref "/docs/pitches/pitch-tracking" >}}) | [Stolen Bases]({{< relref "/docs/runners/stolen-bases" >}})*
