---
title: "Errors"
weight: 70
description: "How to score an error in baseball — E6, E8 notation. What counts as an error, when the official scorer decides, and how BaseballScorer handles it."
---

# Errors

An error is the official scorer's judgment that a fielder failed to make a play they should have made with ordinary effort — and that failure allowed the batter or a runner to reach base (or advance) when they otherwise wouldn't have.

Write **E** followed by the [fielder's number]({{< relref "/docs/basics/fielder-numbering" >}}):

- **E6** — error by the shortstop
- **E4** — error by the second baseman
- **E8** — error by the center fielder
- **E1** — error by the pitcher (usually a failed fielding play, not a pitch)

<!-- TODO: Screenshot of BaseballScorer's fielder tap interface for recording an error -->

## What Counts as an Error

The official scoring rules are clear on the principle but require judgment in practice: a fielder commits an error when they misplay a ball that a fielder in that position, with ordinary effort, would have handled successfully.

Common errors:
- A ground ball that goes through an infielder's legs on a routine hop
- A throw that sails into the stands or past the fielder's target
- A dropped fly ball that was catchable
- A bobbled ball that allows the runner to reach safely or advance an extra base

What's *not* an error:
- Making a difficult catch look easy (no error if you catch it)
- Failing to reach a ball hit into a gap — if it was a hit, it's a hit
- A bad hop on an otherwise routine grounder — *bad hops* can be judgment calls, but a truly unusual bounce usually earns the benefit of the doubt for the fielder

## The Official Scorer's Call

In Major League Baseball, a specific person (the official scorer) has the authority to make the hit/error call on every play. Their decision affects statistics: the pitcher's ERA (errors don't count as earned runs), the batter's batting average (no hit credit on an error), and the fielder's fielding percentage.

When you're scoring recreationally, *you* are the official scorer. Use your judgment. Was it a routine play? Did ordinary effort get it done? Give the fielder the benefit of the doubt on genuinely hard plays; hold them accountable on truly routine misplays.

## Color Coding: Green

Despite being an out-of-the-ordinary bad play, the batter *reached base* on an error. That makes the cell **green** in color-coded scorecards — the same color as a hit. The batter got to first (or wherever), which is what the color tracks.

The distinction is in the notation: **E6** looks different from **1B** even if both cells are green. The batter reached, but they don't get credit for a hit, and the pitcher's ERA is unaffected.

## In BaseballScorer

To record an error, tap **Error** in the outcome grid. BaseballScorer then displays the fielder selection interface — tap the number of the fielder who committed the error.

After the fielder is selected, the at-bat closes with the batter placed at first base (or wherever they ended up). If additional runners advanced on the error — for example, a runner on second scores because the throw to first was wild — you can record that advancement in the runner resolution step.

The scorecard cell shows the error notation (**E6**, **E4**, etc.) with a green background and the batter's path traced to first on the mini diamond.
