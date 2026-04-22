---
title: "Double Plays"
weight: 80
description: "How to score a double play in baseball — the 6-4-3, 4-6-3, and other combinations. DP notation and how BaseballScorer handles runner resolution."
---

# Double Plays

Two outs on one batted ball. The defense executes perfectly, the innings ticks along twice as fast, and the pitcher pumps their fist. The double play is one of baseball's most satisfying sequences — and one of the more interesting things to record on a scorecard.

## The Notation

A double play is recorded as the fielding sequence (the chain of players who touched the ball) with a **DP** suffix or simply by the nature of the sequence itself.

The notation follows the ball: each number represents a [fielder]({{< relref "/docs/basics/fielder-numbering" >}}) who handled it, in the order they touched it.

### The Classic 6-4-3

The most common double play in baseball:
1. Batter hits a ground ball to the shortstop (**6**)
2. Shortstop throws to second baseman (**4**), who catches it and steps on second to retire the lead runner
3. Second baseman throws to first baseman (**3**) to retire the batter

Write: **6-4-3 DP**

The batter's cell shows 6-4-3 (the ground out), and the runner who was on first is recorded as out at second in their original cell.

### Other Common Double Plays

- **4-6-3** — Second baseman starts it, shortstop covers second, throw to first. Same concept, different initiator.
- **5-4-3** — Third baseman to second baseman to first baseman. Common on a hard grounder down the third base line.
- **1-6-3** — Pitcher fields a comebacker, throws to shortstop covering second, throw to first.
- **3-6-3** — First baseman fields it, throws to shortstop covering second, gets the throw back at first. Requires a first baseman who can get off the bag quickly.
- **5-3** — Third baseman fields it and throws directly to first. Only one out at first — but if a runner was already being retired elsewhere (e.g., a tag on third), this completes the double play.

![The 6-4-3 double play: the ball is hit to the shortstop (6, blue), who throws to second base (4, red) to retire the lead runner, then on to first base (3, red) to retire the batter](/images/screenshots/DP6-4-3.png)

## Strikeout Double Plays

Not all double plays involve a ground ball. A strikeout can be part of a double play if:

- **Dropped third strike + runner thrown out:** The batter strikes out but the ball gets away from the catcher. The catcher throws to first to retire the batter (**K, 2-3**), but if a runner was already out elsewhere in the sequence, it's a double play.
- **Strikeout + caught stealing:** The batter strikes out; simultaneously the runner on first was caught stealing. Both outs happen on the same pitch. Score the K for the batter and the caught stealing (CS) for the runner.

These are rarer and require careful recording — you're noting two simultaneous outs rather than a single fielding sequence.

## Fly Ball Double Plays

A fly out can produce a double play if a runner fails to tag up. The runner leaves early, the ball is caught, and the defense throws to the base the runner vacated for the appeal out.

Example: Runner on first, batter hits a fly ball to right field (F9). The runner on first took off running and can't get back. Right fielder catches it, throws to first — **F9, 9-3 DP**.

The batter is out on the caught fly. The runner is out on the throw to first before they can tag up and return.

## Recording in the Scorecard

For a standard ground ball double play:

- In the **batter's cell**: write the fielding sequence (6-4-3). This is an out, so the cell is red.
- In the **runner's cell** (whoever was put out on the throw): mark them as out on that play. Draw an X on their diamond path, or a notation showing where they were retired.

The second out of the double play is recorded in the cell where that runner originally reached base, not in a new cell — because no new batter came to the plate for that out.

Here's a 5-4-3 double play from a hand-scored card. Two cells tell the story: the batter's cell shows the fielding sequence and "DP," and the runner's cell (above) records the first out at second base:

![Hand-scored 5-4-3 double play showing both the batter's cell and the runner's cell — scorecard by Rick Moreno](/images/hand-scored/rick-moreno-double-play.jpg)

## In BaseballScorer

To record a ground ball double play, tap **Ground Out** and then select the fielders in sequence. BaseballScorer lets you tap up to three fielders for a single ground out sequence.

![Fielding sequence interface for recording fielder-to-fielder plays](/images/screenshots/fielding-sequence.jpg)

When you have runners on base and record a ground out, BaseballScorer opens the runner resolution screen. For each runner, you can mark them as **advanced**, **safe at next base**, or **out**. For a typical double play with a runner on first, you'd mark the runner on first as out (retired at second), and the batter is already out via the ground out.

BaseballScorer does not automatically assume any runner is out — it waits for you to resolve each one. This is by design: on a ground out with a runner on first, sometimes the defense only gets one out (the lead runner is safe, batter is out at first), and sometimes they get two (classic DP). You decide what actually happened.

The runner who was retired shows an out marker on their diamond in the scorecard — the path ends where they were tagged or thrown out.
