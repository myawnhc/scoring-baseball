---
title: "Walks and Hit by Pitch"
weight: 60
description: "How to score a walk (BB), intentional walk (IBB), and hit by pitch (HBP) in baseball. All three put the batter on first base."
---

# Walks and Hit by Pitch

Three different outcomes, one common result: the batter takes first base. Walks and hit by pitches are all counted as times on base and count against the pitcher's totals, but they're recorded distinctly because they got there by different means.

## BB — Base on Balls (Walk)

Four balls before a third strike, and the batter walks to first. Write **BB** in the cell.

On the mini diamond, draw a line from home plate to first base — the same as a single. The batter is on base, the pitch count was 4-0 (or some count that reached four balls), and the pitcher fell behind badly enough that the batter never had to swing.

Color coding: **green**. The batter reached base safely, just like a hit.

Here's a walk on a hand-scored card — the diamond path traced from home to first, with the batter later scoring (the completed diamond):

![Hand-scored walk cell showing the batter reaching first and later scoring — scorecard by Steven Harrison](/images/hand-scored/steven-harrison-walk.jpg)

## IBB — Intentional Walk

When the defense wants to put the batter on base deliberately — typically to set up a force play or avoid pitching to a dangerous hitter — they issue an intentional walk. Write **IBB**.

An intentional walk may happen with four intentional ball pitches, or (in MLB since 2017) the manager can simply signal for the walk without any pitches being thrown.

Statistically, a walk is a walk — but IBB is tracked separately because it reflects a strategic choice rather than a pitcher losing the strike zone.

## HBP — Hit by Pitch

The pitcher throws a pitch that strikes the batter. The batter takes first base, no questions asked (unless they made no effort to avoid it, which umpires almost never call). Write **HBP**.

A hit by pitch is generally considered more of a negative outcome for the pitcher than a walk, because the pitcher had *less* control — they didn't just miss the strike zone, they hit someone. HBP counts separately in many statistical contexts.

## Runner Advancement

All three outcomes put the batter on first base. If first base was already occupied, the runner on first is forced to second. If first and second were both occupied, runners advance one base all around. If the bases were loaded, a run scores.

This is called a *force advance* — runners move because they have no choice. Record the batter at first, and trace each forced runner's advancement in their original cell.

## In BaseballScorer

**With pitch tracking on:** BaseballScorer automatically detects walks when the fourth ball is recorded. The at-bat closes and BB is entered. If all four ball pitches were recorded consecutively at the start of the at-bat (0-0 count to 4-0), BaseballScorer may prompt you to confirm whether it was an intentional walk.

**Without pitch tracking:** Tap **BB**, **IBB**, or **HBP** directly from the outcome grid. The at-bat closes and the batter is placed at first.

After any of these outcomes, runner advancement is resolved — BaseballScorer shows you the current baserunner situation and lets you confirm that forced runners advanced correctly. Typically this is automatic (forced runners must advance), but you can adjust if something unusual happened.

The scorecard cell shows **BB**, **IBB**, or **HBP** with a green background and a line traced to first base on the mini diamond.
