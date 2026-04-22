---
title: "Fly Outs"
weight: 40
description: "How to score fly outs, line drives, and foul outs in baseball. F8, L7, FF notation explained. Sacrifice flies and tag-up plays in BaseballScorer."
---

# Fly Outs

Not every out is a grounder. When a batter hits the ball in the air and a fielder catches it before it touches the ground, it's a fly out — and the notation tells you both what *kind* of fly ball it was and *who* caught it.

## The Notation

Fly ball outs use a letter prefix followed by the [fielder's number]({{< relref "/docs/basics/fielder-numbering" >}}):

- **F** — fly ball (a routine fly out)
- **L** — line drive caught on the fly
- **FF** — foul fly (a pop-up caught in foul territory)
- **P** or **IF** — infield pop-up (some scorekeepers use this instead of F for short pop-ups)

Examples:
- **F7** — fly out to left field
- **F8** — fly out to center field
- **F9** — fly out to right field
- **L7** — line drive caught by the left fielder
- **FF2** — foul pop-up caught by the catcher
- **F5** — pop-up caught by the third baseman

![Baseball fielder position numbers on the diamond — 1 (pitcher) through 9 (right field)](/images/screenshots/fielding-positions.png)

The fielder number is always the person who made the *catch*. If a center fielder drifts to right-center and catches a ball that the right fielder was also running toward, it's still F8 because 8 (center field) made the play.

## Why Line Drives Get Their Own Letter

The distinction between **F** and **L** matters more than it might seem. Line drives are hit hard and on a flat trajectory — they're more dangerous to runners and more impressive defensively than routine fly balls. The L notation preserves that context in the scorecard.

A sharply hit ball directly at an infielder might be recorded as **L** (line drive) rather than **F** (fly ball) to reflect the nature of the contact, even if the fielder barely had to move.

## Why Pop Outs Don't

You might wonder why infield pop-ups don't get the same treatment. Some scorekeepers do use **P** or **IF** to distinguish them, but there's less reason to bother. A pop-up to the shortstop and a fly out to the shortstop are essentially the same play — the fielder caught a ball in the air. Line drives earn their own letter because they represent a fundamentally different kind of contact: hard, flat, and fast. Pop-ups are just lazy fly balls that didn't go very far. The **F** prefix covers both fine, and the fielder number already tells you it was an infielder.

## Foul Outs

A ball hit in the air into foul territory that a fielder catches is a foul out — **FF** followed by the fielder number. This is a legitimate out just like any other.

**FF2** (catcher catches a foul pop-up) is probably the most common. **FF3** or **FF5** (first or third baseman catches one near the line) happen regularly too. Occasionally an outfielder will drift into foul territory for one — **FF7** isn't unusual down the left field line.

## Sacrifice Flies

A sacrifice fly (SF) is a special category: the batter hits a fly ball that is caught for an out, but a runner from third base tags up and scores on the play. The batter is out, but they drove in a run and don't receive an at-bat.

Write it as **SF** followed by the fielder who caught it: **SF8** means a sacrifice fly caught by the center fielder while a runner scored from third.

Key rules for a sacrifice fly:
- There must be fewer than two outs (the play can't happen with two outs, since the inning would already be over if the runner had scored)
- A runner must score
- The batter does not receive an at-bat — their plate appearances count goes up, but their at-bat count doesn't, which protects their batting average

The sacrifice fly is the "nice try" of baseball statistics — the batter made an out, but they did something productive, and the rules recognize that.

![Sacrifice fly tag-up prompt — Schwarber tags up, Home or stay?](/images/screenshots/sac-fly-prompt.jpg)

## Tag-Up Situations

Any fly out — not just sacrifice flies — can involve a tag-up. After a fly ball is caught, runners may advance *if* they wait until the moment of the catch before leaving their base. A runner on third tags up on a shallow fly to right; a fast runner on second might tag on a deep fly to center.

In your scorecard, you record the batter's out normally (F9, L8, whatever), and then trace the advancement in the runner's original cell. If the runner on third tagged and scored, complete their diamond. If they tagged from second and went to third, extend the line to third.

If a runner leaves too early and the defense throws to the base for an appeal out, that's a separate out — record the tag-up violation as an appeal play in your notes or as an additional out on the fielding sequence (typically scored as a throw from the outfielder to the base involved).

## In BaseballScorer

To record a fly out, tap **Fly Out**, **Line Out**, or **Foul Out** in the outcome button grid. BaseballScorer will then ask you to tap the fielder who made the catch — the diamond diagram highlights the fielding positions, and you tap the number of the fielder involved.

![Fielding sequence interface showing fielder numbers on the diamond](/images/screenshots/fielding-sequence.jpg)

For most fly outs, that's the entire entry: outcome type + one fielder tap. BaseballScorer confirms the out automatically.

**Sacrifice flies:** When a runner is on third with fewer than two outs and you record a fly out, BaseballScorer will prompt you whether the runner scored. If you confirm the runner scored, the out is recorded as a sacrifice fly (SF) rather than a plain fly out, the run is credited, and the batter does not receive an at-bat.

**Runner tag-ups:** After recording the fly out, you can resolve runner advancement through the runner action sheet. If a runner on second tagged and advanced to third, you record that movement there.

BaseballScorer does not automatically assume any tag-up — it waits for you to tell it what actually happened. The app trusts you to report the play as it unfolded.
