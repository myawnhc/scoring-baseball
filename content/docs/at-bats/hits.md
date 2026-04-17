---
title: "Hits"
weight: 10
description: "How to score hits in baseball — singles, doubles, triples, and home runs. Notation, runner placement, and how BaseballScorer handles hit entry."
---

# Hits

A hit is the most fundamental positive outcome in baseball. The batter put the ball in play, the defense couldn't retire them, and they've reached base safely with no error involved. Hits come in four varieties depending on how far the batter advances, and each has its own notation.

## The Four Hit Types

### Single (1B)

The batter reaches first base on a fair ball. Write **1B** in the cell (some scorekeepers just draw the line to first without any abbreviation — both are fine).

On the mini diamond, draw a line from home plate to first base along the right edge of the diamond.

A batter who reaches first but then advances further on the throw (or other action) is still credited with a single — the hit type records where the batter was *entitled* to go based on the hit, not necessarily where they ended up.

### Double (2B)

The batter reaches second base. Write **2B** in the cell. On the diamond, draw lines from home to first and first to second.

**Ground rule doubles** are scored the same way — **2B** — but some scorekeepers add a note like "GRD" or "GR" to distinguish them. The batter gets second base automatically by rule (typically because the ball bounced into the stands), but statistially it's identical to any other double.

### Triple (3B)

The batter reaches third base. Write **3B**. Three sides of the diamond — home to first to second to third.

Triples are the rarest of the base hits. They require a combination of batted ball quality, outfield depth, and batter speed. When you score one, it tends to be a memorable moment worth a small asterisk in your notes.

### Home Run (HR)

The batter circles all the bases and scores. Write **HR**. All four lines of the diamond, completing the square — and most scorekeepers fill in the diamond or circle it to make it visually unmistakable.

**Inside-the-park home runs** are scored identically (**HR**). The distinction is colorful but statistically it doesn't matter — the batter touched all four bases.

<!-- TODO: Diagram of mini diamonds showing 1B, 2B, 3B, and HR paths -->

## Bunt Singles

A batter who lays down a bunt and reaches safely gets credit for a single. Write **1B** just as you would for any other single. Some scorekeepers add a small "B" or "bunt" notation to distinguish it. If it's a *sacrifice bunt* — where the batter was intentionally bunting to advance a runner and is retired — that's a different situation covered in the Sacrifices section.

The key: if the batter reaches base on a bunt with no error involved, it's a hit.

## Color Coding

Hits are green. On a paper scorecard this might be implicit (reaching base is generally good), but in digital scoring apps like BaseballScorer, the cell background or the diamond trace turns green for any outcome where the batter reached base safely. Green means safe; red means out. You'll internalize this quickly.

<!-- TODO: Screenshot of BaseballScorer showing green cells for a hit -->

## Runner Placement After Hits

Hits create interesting complexity because other runners are already on base. When a batter singles, what happens to the runner on first? It depends on the hit, the number of outs, the runner's speed, and the throw.

The general conventions:

- A **single** typically advances runners one base, though runners on first or second might go two bases on a single to the outfield (especially with two outs).
- A **double** typically advances runners two bases, meaning a runner on first often scores.
- A **triple** typically clears the bases — any runner anywhere is expected to score.
- A **home run** always scores everyone.

These are conventions, not rules. What actually happens is what you record. If a runner on first stops at third on a single, you draw the line from first to third on their original cell. If a runner scores from first on a double, you complete their diamond.

**Advancement you record in the runner's original cell.** The batter's cell shows only the hit outcome. The story of how far each runner went is traced in the cell from the at-bat when they originally reached base.

## In BaseballScorer

To record a hit in BaseballScorer, tap the **1B**, **2B**, **3B**, or **HR** button in the outcome grid during an active at-bat.

<!-- TODO: Screenshot of outcome button grid with hit buttons highlighted -->

After tapping the hit type, BaseballScorer will prompt you to resolve the runners — you'll see a runner action sheet showing where each current baserunner ended up. Tap to confirm their final position (or that they scored).

For home runs, BaseballScorer automatically scores the batter and all runners — there's nothing to resolve. For other hits, you're making the call about runner advancement, which is where your knowledge of what actually happened on the field comes in.

If pitch tracking is on, the pitches leading up to the hit are already recorded. The hit itself is the final pitch of the at-bat (a ball put in play), and BaseballScorer closes out the at-bat when you confirm the outcome.

The scorecard cell updates immediately: green diamond trace showing the hit, the abbreviation in the center, and pitch dots along the edge.
