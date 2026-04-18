---
title: "The Ghost Runner"
weight: 40
description: "How the automatic runner rule works in extra innings — the ghost runner, who it is, and how it appears on the scorecard."
---

# The Ghost Runner

Since 2020, Major League Baseball has used an automatic runner rule in extra innings: at the start of each extra-innings half-inning, a runner is automatically placed on second base. No one hit their way on. No one walked. The runner just appears. Fans and scorers have taken to calling this the **ghost runner**.

The rule exists to keep extra-inning games from turning into four-hour endurance tests. It creates immediate scoring pressure: every half-inning beyond the ninth starts with a runner in scoring position and nobody out. Teams adjusted their strategy quickly — sacrifice bunts and squeeze plays made a comeback almost overnight.

## Who Is the Ghost Runner?

The automatic runner is the last batter who made an out (or the last batter who batted, in some formulations) in the previous half-inning. If the bottom of the ninth ended when the number-five hitter grounded out to end the inning, that player becomes the ghost runner at second base to start the top of the tenth.

This means the ghost runner is a real player, already in the lineup. He's not a substitute — no roster moves are triggered. He simply starts the inning at second base as if he had reached there on his own.

If that player was already replaced in the lineup (by a pinch hitter or defensive sub), the player who replaced him in the lineup is the ghost runner.

## How It Shows on the Scorecard

On a paper scorecard, many scorers note the ghost runner with a circle or box around the runner's position on second, often with a small annotation like "AR" (automatic runner) or "GR" to distinguish the placement from a legitimate baserunner. The runner's path begins at second base rather than home plate — the portion of the diamond from home to second is not filled in, because that base advancement didn't happen in this at-bat.

The ghost runner's at-bat box for that inning gets special treatment: it's either left blank (he didn't have a plate appearance), marked with a dash, or annotated to show he started on base. Different scoring systems handle this differently.

If the ghost runner scores, the run is credited to the pitcher who was pitching when the ghost runner was "placed" — even though the ghost runner never actually faced that pitcher. This is a quirky wrinkle in how earned runs are assessed in extra innings.

<!-- TODO: Screenshot of scorecard showing ghost runner starting position at 2nd base with dashed or annotated path -->

## In BaseballScorer

When an extra inning begins, BaseballScorer automatically places the ghost runner on second base. The runner appears on the diamond with a **dashed border** instead of a solid fill, and a **"GHOST"** label to distinguish it from runners who reached base conventionally.

![Scoring view in extra innings showing GHOST label on Church at second base, walk-off celebration](/images/screenshots/walk-off-ghost.jpg)

The portion of the diamond path from home plate to second base — the path the ghost runner never actually ran — is shown with a **dotted line** rather than a solid one. When the ghost runner advances or scores, the paths from that point forward are drawn normally.

Tapping the ghost runner's base opens the same [Runner Action Sheet]({{< relref "stolen-bases" >}}) as any other baserunner. You can advance the ghost runner on a hit, move them on a wild pitch, or record them scoring just like any other runner. The dashed presentation is purely cosmetic — the ghost runner behaves like a real baserunner in every mechanical sense.

If the ghost runner is still on base when the half-inning ends, BaseballScorer clears them at the start of the next half-inning and places a new ghost runner as appropriate.

The rule applies starting in the tenth inning and continues for every extra inning after that. Games that require an eleventh, twelfth, or more innings each start fresh with a new ghost runner placement each half-inning.
