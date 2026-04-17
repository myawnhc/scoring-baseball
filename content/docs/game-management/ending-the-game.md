---
title: "Ending the Game"
weight: 50
description: "When and how a baseball game ends — regulation, walk-offs, extra innings, shortened games, and mercy rules."
---

# Ending the Game

Most baseball games end the same way: nine innings, three outs per half, and the team with more runs wins. But baseball has enough edge cases around game endings that it's worth knowing them — especially since they affect how you close out your scorecard.

## Regulation Games

A standard game is nine innings. Each team gets three outs per half-inning. After the top of the ninth, if the visiting team leads, the home team gets their final three outs. If the home team leads after the top of the ninth, or ties it, they bat in the bottom half.

The game ends when the **third out of the final half-inning is recorded** — assuming the home team needs to bat. If the home team is already ahead after eight and a half innings, the bottom of the ninth isn't played.

## Walk-Off Wins

A **walk-off** is when the home team scores the winning run in their final at-bat, ending the game immediately. The name comes from the losing team "walking off" the field.

Walk-offs can happen on a hit, a walk with the bases loaded, a sacrifice fly, a wild pitch — anything that scores the go-ahead run. The moment that run scores, the game ends. The batter doesn't need to reach base (on a bases-loaded walk or HBP); the runner scoring from third is what matters.

On the scorecard, the walk-off at-bat is the last entry. If the winning run scores mid-play, subsequent baserunner movement doesn't matter — the game is over.

<!-- TODO: Screenshot of the walk-off screen with fireworks icon and "Walk-Off!" heading -->

## Extra Innings

If the score is tied after nine innings, the game continues. Each additional half-inning is played out until one team leads at the end of a complete extra inning, or until the home team takes the lead in the bottom half.

Since 2020, MLB uses a "ghost runner" rule in extra innings: each half-inning starts with a runner on second base (the player who made the last out in the previous inning). This was introduced to shorten extra-inning games. Minor leagues and youth leagues may use the same rule.

On the scorecard, extra innings continue in additional columns to the right of the ninth inning. Ghost runner cells get a special marker to indicate the runner didn't reach base through normal play. See the [ghost runner]({{< relref "/docs/runners/ghost-runner" >}}) page for notation details.

## Shortened and Suspended Games

A game can be shortened by weather, field conditions, or other circumstances. The rules for what counts as an official game (and what happens to stats) vary by league, but generally:

- In MLB, a game is official after **five complete innings** (or four and a half if the home team leads)
- Stats from unofficial games may not count
- A suspended game is resumed from where it stopped; a called game ends immediately

On your scorecard, note the reason for shortening in the notes field if the game doesn't go the full nine.

## Mercy Rules (Non-MLB)

Youth leagues, high school, college, and amateur leagues often use a **mercy rule** (also called run rule): the game ends early if one team leads by a certain margin after a minimum number of innings. Common thresholds are 10 runs after five innings or 15 runs after three. The specific numbers vary by league.

Mercy rules don't apply in MLB, but if you're scoring amateur or youth ball, know your league's rule and note it when the game ends early.

## In BaseballScorer

BaseballScorer detects the end of the game automatically based on the score, the inning, and the number of outs.

**Half-inning complete view:** After three outs in any half-inning, the app shows a summary screen with the R/H/E/LOB recap and a "Next Half-Inning" button. The game doesn't advance automatically — you confirm the transition. This gives you a moment to double-check the inning before moving on.

![Half-inning summary showing runs, hits, and the at-bat cards for the inning](/images/screenshots/half-inning-complete.jpg)

**Walk-off detection:** When the home team scores the winning run, the app recognizes the walk-off condition and displays a celebratory screen with a fireworks icon and "Walk-Off!" heading. The End Game button appears here.

**Game over:** When the final out is recorded, the app shows a game-over screen with the reason (final out, walk-off) and the final score. You can then end the game from the action menu.

**End Game and Delete:** The action menu always contains an "End Game" option if you want to close out manually — for example, if a game is called due to rain. A "Delete & Exit" option is also available if the game needs to be removed entirely.

![Action menu with End Game option at the bottom](/images/screenshots/action-menu.jpg)

---

*See also: [Ghost Runner]({{< relref "/docs/runners/ghost-runner" >}}) | [Reading the Grid]({{< relref "/docs/scorecard/reading-the-grid" >}}) | [Line Score]({{< relref "/docs/scorecard/line-score" >}})*
