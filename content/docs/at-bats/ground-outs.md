---
title: "Ground Outs"
weight: 30
description: "How to score a ground out in baseball — the 6-3, 4-3, and every other groundball notation explained."
---

# Ground Outs

The ground out is the most common play in baseball. Batter hits a grounder, an infielder scoops it up, throws to first, and the batter is out. It happens dozens of times per game, so you'll want this notation in your muscle memory fast.

## The Notation

A ground out is written as the fielder numbers separated by dashes, in the order the ball was handled:

**6-3** — Shortstop fielded, threw to first baseman.

That's it. The first number is who picked it up, the last number is who caught it for the out. If the ball went through more than two hands, you add the middle fielders too.

## Common Ground Outs

Here are the ground outs you'll see most often, roughly in order of frequency:

| Notation | Description |
|----------|------------|
| **6-3** | Shortstop to first. The most common ground out in baseball. |
| **4-3** | Second baseman to first. |
| **5-3** | Third baseman to first. |
| **1-3** | Pitcher to first. Typically on a comebacker or bunt. |
| **3U** | First baseman unassisted. He fielded it near the bag and stepped on it himself. |
| **1-6-3** | Pitcher to shortstop to first. Rare relay play. |
| **3-6-3** | First baseman to shortstop to first (1B fielded it, threw to SS covering second for a force, SS threw back to 1B for the out). You'll sometimes see this on bunt plays or with a runner on first. |

The "U" in "3U" means **unassisted** — only one fielder was involved. You'll see this when the first baseman fields a ball hit near the bag and doesn't need to throw to anyone.

## Bunt Ground Outs

Bunts that result in outs look the same as regular ground outs in the notation — the fielder numbers tell the story. A bunt fielded by the pitcher and thrown to first is **1-3**, same as any other comebacker.

If the bunt is a **sacrifice** (the batter bunted intentionally to advance a runner, giving themselves up), the notation adds "SAC" as a prefix: **SAC 1-3** or **SAC 5-3**. The sacrifice designation matters for statistics — a sac bunt doesn't count as an official at-bat, so it doesn't hurt the batter's average.

## Ground Outs with Multiple Runners

When there are runners on base during a ground out, the defense might throw to a different base first. A grounder to short with a runner on first might result in:

- **6-3** — Shortstop threw to first (got the batter, runner advances)
- **6-4** — Shortstop threw to second (got the lead runner, batter reaches first on a fielder's choice)
- **6-4-3 DP** — Shortstop to second to first (got both — a double play)

When the defense chooses to get the lead runner instead of the batter, that's a **fielder's choice**. When they get both runners, that's a **double play**.

## What About the Runners?

The ground out notation only records the batter's result. What happened to the other runners — did they advance? Were they thrown out? — is recorded separately through the runner's path on the scorecard.

In BaseballScorer, after you record a ground out with runners on base, the app asks you what happened to each runner. You'll see toggles for each runner showing **SAFE**, **OUT**, or **STAY**, with smart defaults based on the situation (forced runners with a three-fielder sequence default to OUT, since that's probably a double play).

![Runner resolution cards showing advancement options for each baserunner](/images/screenshots/runner-resolution.jpg)

## Scoring a Ground Out in BaseballScorer

Here's the flow:

1. **Tap "Ground Out"** (or "GO" on compact screens) from the outcome buttons
2. **Tap the fielders on the diamond** in the order they handled the ball — fielder position numbers appear at each position
3. **Tap "Complete"** (or "Unassisted" if only one fielder was involved)
4. **Resolve runners** if any were on base — toggle each runner's fate

The app builds the notation automatically: tap 6, tap 3, and you'll see "6-3" appear in the batter's completed at-bat card.

![Ground out 5-3 fielding sequence — fielder numbers highlighted on the diamond with GO notation](/images/screenshots/ground-out-sequence.png)

For a simple ground out with no runners on base, the whole thing takes about two seconds — tap GO, tap two fielders, done.

## The Unassisted Ground Out

The "3U" is a special case worth calling out. When the first baseman fields a grounder near the bag and steps on it himself, there's no throw involved — he just fields and tags the base. You record this by tapping just the single fielder (3), then tapping "Unassisted" instead of "Complete."

On paper, you'd write **3U**. The "U" makes it clear that only one player was involved. Without it, a bare "3" on the scorecard would be ambiguous — did the first baseman make an unassisted out, or did someone forget to write the rest of the play?

## Related

- **Double Plays** — when the ground out gets two runners (coming soon)
- **Fielder's Choice** — when the defense throws to a different base (coming soon)
- **Sacrifice Bunts** — when the batter bunts intentionally to advance a runner (coming soon)
- [Fielder Position Numbers]({{< relref "/docs/basics/fielder-numbering" >}}) — the complete numbering reference
