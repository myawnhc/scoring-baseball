---
title: "Scoring Notation"
weight: 40
description: "The complete guide to baseball scoring notation — what all the symbols, numbers, and abbreviations on a scorecard mean."
---

# Scoring Notation

Baseball scoring notation is a shorthand for recording what happened during every at-bat. It's compact, standardized (mostly), and once you learn it, you can reconstruct an entire game from a single sheet of paper. Or, in our case, from a single screen.

## The Basics

Every at-bat gets a notation that tells you the result. The notation system uses three main elements:

1. **Fielder numbers** (1-9) to identify who handled the ball
2. **Letter codes** for the type of play (F for fly, L for line drive, K for strikeout, etc.)
3. **Suffixes** for modifiers (DP for double play, U for unassisted)

If you don't know the fielder numbers yet, read [Fielder Position Numbers]({{< relref "fielder-numbering" >}}) first — the notation won't make sense without them.

## Hits

Hits are the simplest notation — just the type of hit:

| Notation | Meaning |
|----------|---------|
| **1B** | Single |
| **2B** | Double |
| **3B** | Triple |
| **HR** | Home Run |

No fielder numbers needed for the basic hit notation. The scorecard shows where the runner ended up through the diamond path (we'll cover that in Reading the Mini Diamond).

## Ground Outs

Ground outs use the fielder numbers separated by dashes, describing the order the ball was handled:

| Notation | What Happened |
|----------|--------------|
| **6-3** | Shortstop to first base |
| **4-3** | Second baseman to first base |
| **5-3** | Third baseman to first base |
| **1-3** | Pitcher to first base |
| **3U** | First baseman unassisted (fielded it and stepped on the bag) |
| **1-6-3** | Pitcher to shortstop to first base (rare relay) |

The "U" suffix means unassisted — only one fielder was involved. This typically happens when the first baseman fields a grounder near the bag and steps on it himself.

## Fly Outs, Line Outs, and Foul Outs

These use a letter prefix plus the fielder who caught it:

| Notation | What Happened |
|----------|--------------|
| **F8** | Fly out to center field |
| **F7** | Fly out to left field |
| **F9** | Fly out to right field |
| **L6** | Line out to shortstop |
| **L4** | Line out to second baseman |
| **FF2** | Foul out caught by the catcher |
| **FF5** | Foul out caught by the third baseman |

- **F** = fly ball (arcing trajectory)
- **L** = line drive (hard, flat trajectory)
- **FF** = foul fly (caught in foul territory)

## Strikeouts

Baseball has a special tradition here: the letter **K** for strikeout.

| Notation | Meaning |
|----------|---------|
| **K** | Strikeout swinging — the batter swung and missed at strike three |
| **Kc** | Strikeout looking — the batter watched strike three go by (called strike) |

The "looking" strikeout is traditionally written as a **backwards K** on paper scorecards — the letter K mirrored horizontally. BaseballScorer renders this the same way, flipping the K in the display. You'll see this all over ballparks too, on those K-count signs fans hang from the upper deck.

## Walks and Hit By Pitch

| Notation | Meaning |
|----------|---------|
| **BB** | Base on balls (walk) — four balls, batter takes first |
| **IBB** | Intentional walk — pitcher deliberately walked the batter |
| **HBP** | Hit by pitch — the pitch hit the batter, who takes first |

## Errors

| Notation | Meaning |
|----------|---------|
| **E6** | Error by the shortstop |
| **E5** | Error by the third baseman |
| **E2** | Error by the catcher |

The "E" plus the fielder number who committed the error. The batter reaches base, but it's not counted as a hit — the official scorer decided the fielder should have made the play.

## Double Plays

Any out notation can be followed by **DP** to indicate a double play:

| Notation | What Happened |
|----------|--------------|
| **6-4-3 DP** | Shortstop to second base to first base (the classic) |
| **4-6-3 DP** | Second baseman to shortstop to first base |
| **5-4-3 DP** | Third baseman to second base to first base |
| **K DP** | Strikeout plus a runner caught (strikeout-throwout) |
| **F8 DP** | Fly out plus a runner doubled off |

The most common double play in baseball is the 6-4-3 — grounder to short, flip to second for the force, relay to first for the second out. You'll score this one a lot.

## Sacrifices

| Notation | Meaning |
|----------|---------|
| **SAC 1-3** | Sacrifice bunt — pitcher to first base |
| **SAC 5-3** | Sacrifice bunt — third baseman to first base |
| **SF8** | Sacrifice fly — fly out to center field that scored a runner from third |

A sacrifice bunt is an intentional out where the batter bunts to advance a runner. A sacrifice fly is a fly out deep enough that a runner on third can tag up and score. Neither counts as an official at-bat in the batter's statistics.

## Fielder's Choice

| Notation | Meaning |
|----------|---------|
| **FC 6-4** | Fielder's choice — shortstop threw to second base (chose to get the lead runner instead of the batter) |

The batter reaches first, but only because the defense chose to get a different runner out. It's not a hit.

## Other Notations

| Notation | Meaning |
|----------|---------|
| **INT** | Interference — batter reaches base due to catcher's interference |
| **?** | Unknown / incomplete — a placeholder for a play you missed or couldn't identify |

## Color Coding

On paper, all of this is black ink. In BaseballScorer, notation is color-coded to help you scan results at a glance:

| Color | Means |
|-------|-------|
| **Green** | Batter reached base (hits, walks, HBP, errors, fielder's choice) |
| **Red** | Strikeout (swinging or looking) |
| **Black/White** | All other outs (ground outs, fly outs, etc.) |

This means you can glance at a column of completed at-bats and immediately see the hits (green), strikeouts (red), and outs (neutral) without reading the notation.

## The Complete Table

For quick reference, here's every notation in one place:

| Notation | Result | Color |
|----------|--------|-------|
| 1B | Single | Green |
| 2B | Double | Green |
| 3B | Triple | Green |
| HR | Home Run | Green |
| BB | Walk | Green |
| IBB | Intentional Walk | Green |
| HBP | Hit by Pitch | Green |
| E*n* | Error (by fielder *n*) | Green |
| FC *n-n* | Fielder's Choice | Green |
| *n-n* | Ground Out | Default |
| *n*U | Unassisted Ground Out | Default |
| F*n* | Fly Out | Default |
| L*n* | Line Out | Default |
| FF*n* | Foul Out | Default |
| SAC *n-n* | Sacrifice Bunt | Default |
| SF*n* | Sacrifice Fly | Default |
| K | Strikeout Swinging | Red |
| Kc (backwards K) | Strikeout Looking | Red |
| *any* DP | Double Play | Default |
| ? | Unknown / Incomplete | Orange |
