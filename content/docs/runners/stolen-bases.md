---
title: "Stolen Bases"
weight: 10
description: "How to score a stolen base, caught stealing, and pickoff — notation, official rules, and BaseballScorer's runner action sheet."
---

# Stolen Bases

A stolen base is one of the most exciting plays in baseball — a runner taking a base entirely through his own speed and instinct, with no help from the batter. Scoring it is straightforward once you know the notation, and it's one of the few events in a game that happens completely between pitches, independent of the at-bat in progress.

## What Counts as a Stolen Base

A stolen base (SB) is credited when a runner advances to the next base without the benefit of a hit, walk, error, or balk — and without the batter helping by putting the ball in play. The runner simply goes, and if he's safe, it's a stolen base.

A few nuances worth knowing:

**Defensive indifference** is not a stolen base. If the fielding team makes no attempt to throw out the runner — typically in late innings when the run doesn't matter — official scorers don't credit a stolen base. The runner advances, but it's scored as defensive indifference (DI). This comes up most often with a runner stealing second in the ninth inning when the defense is protecting a multi-run lead and doesn't want to risk a bad throw.

**Double steals** — two runners stealing simultaneously — each earn a stolen base, recorded separately.

**Delayed steals** — where the runner takes advantage of a slow return throw to the pitcher — still count as stolen bases, even though the action looks different from a traditional jump.

## Notation on the Scorecard

On a paper scorecard, a stolen base is typically noted at the base path segment where the runner advanced. The most common notation is **SB** written at the midpoint of the segment from the starting base to the stolen base, often with an arrow indicating direction.

![Mini diamond showing SB annotation on the first-to-second base path](/images/screenshots/stolen-base-annotation.jpg)

On the mini diamond in the at-bat box, the path from base to base is divided into segments. The SB label appears at the midpoint of the segment that was stolen — so for a steal of second, it appears on the segment between first and second base.

## Caught Stealing

When a runner attempts to steal and is thrown out, it's a caught stealing (CS). The runner is out, and the at-bat continues if the pitch count hasn't concluded.

Caught stealing is recorded with the **CS** abbreviation. On a paper scorecard, many scorers draw a **red crossbar** through the base path segment at the point where the runner was tagged — visually marking the path as "stopped here." The fielding notation shows who made the play: a catch by the catcher and tag by the shortstop at second would be noted as **CS 2-6** (catcher to shortstop, a common notation for the throwing sequence).

The caught stealing counts against the runner's stolen base statistics. Stolen base percentage (SB / (SB + CS)) is the standard measure of basestealing efficiency — anything above 70-75% is generally considered break-even.

### When Caught Stealing Makes the Third Out

Here's a scoring scenario that trips people up: a runner gets caught stealing for the third out of the inning *while another batter is mid-at-bat*. The batter didn't finish his plate appearance — the inning just ended underneath him. What do you write in his scorecard cell?

The answer: nothing, really. The batter's at-bat didn't happen. He comes back to lead off the next inning with a fresh count, as if the interrupted plate appearance never existed. On a paper scorecard, you'd leave the cell blank or draw a line through it.

BaseballScorer handles this automatically. When a caught stealing (or any runner event) records the third out mid-at-bat, the current batter's cell shows a crossed-out **AB** symbol — a visual shorthand for "this plate appearance was interrupted and doesn't count." The text below the cell explains what happened: the at-bat ended because of the runner event, not anything the batter did.

In the inning summary, you can see the full picture — Harper's single with the CS annotation on the runner path, and Garcia's interrupted at-bat below it:

![Inning summary showing Harper's single with CS on the base path, and Garcia's interrupted at-bat with crossed-out AB notation](/images/screenshots/caught-stealing-interrupted-scoring.jpg)

On the landscape scorecard, the same information is condensed into the grid. Garcia's cell shows the crossed-out AB with an arrow pointing to his next at-bat in the following inning. On a normal scorecard, a diagonal slash in the cell marks the end of an inning — the next cell to score is one column over and one row down. Here, because Garcia leads off the next inning with a fresh count, the arrow points directly to the right — same row, next column:

![Scorecard cell showing interrupted at-bat notation — crossed-out AB with arrow to Garcia's next at-bat in the following inning](/images/screenshots/caught-stealing-interrupted-scorecard.jpg)

This comes up more often than you'd expect — any time the third out happens on the bases while a batter is in the box. Caught stealing is the most common cause, but a runner thrown out trying to advance on a wild pitch or picked off can trigger it too.

## Pickoffs

A **pickoff** is different from a caught stealing. On a pickoff, the pitcher (or catcher on a pickoff from the catcher) throws to a base while the runner is not attempting to steal — the runner is simply caught too far off the bag. If the fielder tags the runner before he can return, the runner is out.

Pickoffs are scored as outs, typically noted as a throwing sequence (e.g., **1-3** for pitcher to first baseman). They don't count as caught stealing in official statistics because the runner wasn't attempting to advance — they were just picked off.

In practice, the line between a pickoff and a caught stealing can be blurry when a runner breaks late. The official scorer makes the call.

## Effect on the Pitcher's Record

Stolen bases during an at-bat don't affect the pitcher's ERA or any pitching stat directly. The pitcher isn't charged with anything for a stolen base — it's on the fielding team to prevent it. However, stolen bases certainly affect the game situation the pitcher is working in. A runner on second instead of first changes the defense, the pitcher's approach, and the pressure on every subsequent pitch.

Wild pitches and passed balls that allow runners to advance are handled differently — those are charged to the pitcher (WP) or catcher (PB) respectively. See [wild pitches and passed balls]({{< relref "wild-pitches" >}}) for details.

## In BaseballScorer

Stolen bases are recorded through the **Runner Action Sheet** — an overlay that appears when you tap an occupied base on the diamond.

![Runner Action Sheet showing Stolen Base, Caught Stealing, and Picked Off options](/images/screenshots/runner-action-sheet.jpg)

Tap the filled base indicator for the runner you want to act on. The action sheet presents several options:

- **Stolen Base** — runner advances one base; SB is recorded in the base path
- **Caught Stealing** — runner is put out; at-bat continues
- **Picked Off** — runner is put out via pickoff; distinct from CS in the record
- **Advance** — runner moves forward (for other non-steal situations)
- **Out Trying** — runner thrown out trying to advance
- **Advance on Error** — runner advanced because of a fielding error
- **Pinch Runner** — substitutes a new runner for the current one

After selecting Stolen Base, the mini diamond updates to show the SB annotation at the appropriate segment midpoint. If you select Caught Stealing, the runner is removed from the bases and the out total increases.

![At-bat card with SB annotation on the mini diamond after a stolen base](/images/screenshots/stolen-base-annotation.jpg)

The action sheet can be accessed at any point during an active at-bat — before, after, or between pitches. Stolen bases happen independently of the pitch sequence, and BaseballScorer lets you record them whenever they occur in the game without disrupting the pitch tracking flow.
