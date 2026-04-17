---
title: "Fielder's Choice"
weight: 90
description: "How to score a fielder's choice (FC) in baseball. When the defense retires a lead runner instead of the batter, and how FC differs from a hit or error."
---

# Fielder's Choice

A fielder's choice happens when the batter hits a ball in play, reaches base, but doesn't get credit for a hit — because the defense chose to retire a different runner instead of throwing to first.

Write **FC** followed by the fielding sequence:

- **FC 6-4** — shortstop fielded the grounder and threw to second to retire the lead runner; batter reached first
- **FC 5-4** — third baseman threw to second; batter safe at first
- **FC 1-6** — pitcher fielded it, threw to shortstop covering second

<!-- TODO: Screenshot of BaseballScorer showing FC in the scorecard cell -->

## What Qualifies as a Fielder's Choice

The defining feature: the defense had a play on the batter at first, but instead made a play on another runner. The batter ends up on first base, alive, but with no hit credited.

The classic situation: runner on first, ground ball to the shortstop. The shortstop can throw to second to get the force out on the lead runner — and they do. The batter beats the relay throw to first, or there's no throw at all. The shortstop made a *choice* about which runner to retire. Fielder's choice.

## FC vs. a Hit

The difference comes down to whether the defense *could* have gotten the batter. If the shortstop made an ordinary play on the ground ball and threw to second (instead of first), but a throw to first *also* would have retired the batter, it's a fielder's choice — no hit.

If the ground ball was hit hard enough that there was genuinely *no play* at first regardless, it might be scored as a hit, because the defense didn't really have a choice — the only available out was at second. This is a judgment call that scorers make in real time.

The practical test: **if the defense got the out they were going for, it's FC**. If they failed at the play they attempted (and the batter reached), it might be an error.

## FC vs. an Error

Both result in the batter reaching base without a hit. The distinction:

- **FC**: The defense made the play they chose to make (retiring the lead runner) and the batter reached as a result of that choice. No mistake involved.
- **E**: The defense attempted a play and failed to execute it. A throw that bounced away, a ground ball that went through legs — that's an error.

On a fielder's choice, everything went as the defense intended. They just chose the other runner. On an error, something went wrong.

## Color Coding

**FC is green.** The batter reached base, which is what the color tracks — regardless of whether they earned a hit. Green means safe; the notation distinguishes FC from an actual base hit.

## In BaseballScorer

Tap **FC** (Fielder's Choice) in the outcome grid. BaseballScorer then asks you to tap the fielders in sequence — who fielded the ball, and who they threw to for the out.

After the sequence is entered, BaseballScorer resolves the runners. The lead runner who was retired is marked out (you confirm this in the runner resolution screen). The batter is placed at first base with an FC notation.

The at-bat closes with the batter at first, green cell, **FC** notation with the fielding sequence. The retired runner shows an out marker in their original cell.
