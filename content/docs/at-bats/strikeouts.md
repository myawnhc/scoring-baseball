---
title: "Strikeouts"
weight: 50
description: "Strikeout notation in baseball — K for swinging, backwards K for called. Why the backwards K exists, dropped third strikes, and strikeout double plays."
---

# Strikeouts

The strikeout is baseball's most symbolic out. Three strikes and you're done — but how you got there matters enough to record differently depending on whether the batter went down swinging or stood there watching strike three go past.

## K and the Backwards K

**K** is the universal symbol for a strikeout. It dates to the 1860s, when Henry Chadwick (the father of baseball statistics) chose K because "struck" — the root of "strikeout" — ends in K. S was already taken for sacrifice.

- **K** — strikeout swinging. The batter swung at strike three and missed.
- **Backwards K** (Ꝁ) — strikeout looking (called). Strike three was called by the umpire; the batter did not swing. Some scorekeepers write this as **Kc** instead.

The backwards K has become iconic in baseball culture. Fan sections hang backwards K signs for each strikeout by a dominant pitcher, counting them across the outfield wall. It's a mirror letter for a batter who didn't move — who stood frozen while the pitcher made them look foolish.

<!-- TODO: Illustration of K vs backwards K notation -->

**BaseballScorer uses the backwards K** for called strikeouts — the mirror-image letter that's become iconic in baseball culture.

## Color Coding

Strikeout text is rendered in red on the scorecard. This makes strikeouts visually pop when scanning the grid — you can quickly see how many Ks a pitcher racked up without reading every cell. The red text stands out against the otherwise neutral scorecard, giving you an instant read on a pitcher's dominance.

## Dropped Third Strike

Here's a wrinkle: a strikeout is not always an out.

If the catcher fails to catch strike three cleanly — the ball bounces away — the batter may attempt to run to first base. The rule: the batter can run if first base is unoccupied (or if there are two outs). The catcher must then throw to first to retire the batter, just like any other ground ball.

If the batter reaches first safely on a dropped third strike:
- The pitcher still gets credit for a strikeout (K)
- The catcher gets charged with a passed ball (PB) or the pitcher with a wild pitch (WP), depending on the scorer's judgment
- The batter is credited as reaching on a strikeout — write **K-WP** or **K-PB** to show what happened

If the catcher recovers and throws to first in time:
- Score it **K, 2-3** — strikeout, catcher to first baseman
- The pitcher gets the strikeout; the catcher gets an assist

<!-- TODO: Screenshot of BaseballScorer's dropped third strike flow -->

## Strikeout Double Plays

A strikeout can be part of a double play in rare situations. The most common: bases loaded, batter strikes out on a wild pitch, catcher picks it up and throws home to get the runner from third who broke for the plate. Score it **K, WP, 2-5-3** or similar, depending on the exact sequence.

These are unusual enough that you may never see one in a season of casual scoring. But if it happens, record the strikeout first and then the subsequent fielding sequence.

## In BaseballScorer

**With pitch tracking on:** BaseballScorer detects strikeouts automatically. As you record each pitch, the count updates in real time. When the third strike is recorded — whether swinging, looking, or foul tip — BaseballScorer recognizes the at-bat is complete.

If the final pitch was a swinging strike, the outcome is recorded as **K**. If you mark the pitch as "called strike," it becomes a **backwards K**.

A dropped third strike (wild pitch or passed ball on strike three) is handled by continuing the at-bat after the strikeout — BaseballScorer stays in the at-bat and lets you record what happened to the batter.

**Without pitch tracking (manual entry):** Tap **K** (swinging) or **Ꝁ** (looking) directly in the outcome button grid. The at-bat closes immediately. No additional input is needed for a standard strikeout.

![Outcome button grid with K (swinging) and other result options](/images/screenshots/outcome-button-grid.jpg)

The scorecard cell shows the K or backwards K notation in red text. If pitch dots are enabled, you'll see the sequence of pitches that led to the strikeout.
