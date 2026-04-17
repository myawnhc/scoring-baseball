---
title: "Tag Ups"
weight: 30
description: "The tag-up rule explained — when runners can advance after a caught fly ball, and how to score sacrifice flies and tag-up outs."
---

# Tag Ups

The tag-up rule is one of those baseball rules that sounds complicated but makes intuitive sense once you see it in action. When a fly ball is caught for an out, runners don't have to stay frozen — they can advance, as long as they first return to (or remain touching) the base they were on when the ball was caught. That act of returning to the base before advancing is the "tag up."

## The Rule

Any time a fly ball is caught — by an outfielder, an infielder, anywhere in fair or foul territory — runners may attempt to advance after the catch. The requirement is that the runner must be touching their base at the moment the fielder catches the ball, or return to that base before advancing.

If a runner leaves their base before the catch, they have to get back to that base (tag up) before they can advance. A fielder can throw to that base to get the runner out on appeal — an appeal play, not a live play. If the fielder successfully gets the ball to the base before the runner returns, the runner is out even if they already advanced safely.

The tag-up rule applies to all caught fly balls, including foul balls.

## The Classic Situation: Sac Fly

The most common tag-up scenario is a runner on third with fewer than two outs. A batter hits a reasonably deep fly ball to the outfield. The outfielder catches it — that's out number two or three — but the runner on third tags up and scores after the catch. The run counts, even though the batter made an out.

This is called a [sacrifice fly]({{< relref "/docs/at-bats/sacrifices" >}}). The batter is credited with an RBI, is not charged with a time at bat (so it doesn't hurt the batting average), and the play is scored as a fly out with a runner scoring on the tag.

The scorer's job is to record both things: the out on the batter (fly to 8 — center field, for example) and the run scoring on the tag (the runner's path completes from third to home, marked as scoring on the tag-up).

<!-- TODO: Screenshot of mini diamond showing completed path from 3rd to home via tag-up notation -->

## Tag-Up Outs

Runners don't always make it safely. A runner tagging from second on a shallow fly to right field, or a runner trying to score from second on a fly to center, can be thrown out at the next base. This is a live play: the fielder catches the ball and throws to the base the runner is heading to. If the throw beats the runner and the tag is applied, the runner is out.

This out is recorded with the standard fielding notation — the throw from right field (9) to home (2) would be noted as **9-2** on the batter's scoring box or the runner's base path. If it ends the inning, the three-out marker closes the half-inning.

The [double play]({{< relref "/docs/at-bats/double-plays" >}}) variant — catching the fly ball and doubling off a runner who left early — is called a "double play" even though the second out comes on appeal rather than a direct relay. It's a relatively rare but very satisfying defensive play.

## Runners on Other Bases

The tag-up rule applies to all bases, not just third. A runner on second can tag up and advance to third. A runner on first can tag up and try for second. These advances are less common because it usually takes a very deep fly ball for a runner on first or second to gain a base this way — there's no margin for error with shallow flies.

The scorer tracks each runner's decision independently. On a fly ball with runners on first and third, the runner on third might tag and score while the runner on first holds. Both outcomes need to be recorded separately on the mini diamonds.

## In BaseballScorer

After you record a [fly out]({{< relref "/docs/at-bats/fly-outs" >}}), BaseballScorer checks whether there are runners on base and, if so, prompts you for each runner's decision: did they tag up and advance, or did they hold?

<!-- TODO: Screenshot of tag-up advancement prompt appearing after recording a fly out -->

You work through each runner individually. For runners who advanced, the base path updates to show the movement. If the runner scored, the run is added to the inning total. If the runner was thrown out trying to advance, you can record that out as well — it increments the out count and ends the at-bat entry.

The sacrifice fly credit is handled automatically: if the runner on third tags and scores, and the batter is out on the fly, BaseballScorer credits the batter with an RBI and excludes the plate appearance from the batting average calculation.

<!-- TODO: Screenshot of completed at-bat with sac fly notation and runner scoring from third -->
