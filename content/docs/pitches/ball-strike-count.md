---
title: "The Ball-Strike Count"
weight: 20
description: "What the ball-strike count means, how it drives at-bat outcomes, and how BaseballScorer tracks it automatically."
---

# The Ball-Strike Count

Every at-bat in baseball has a count — two numbers that tell you exactly where things stand between pitcher and batter. The count is always expressed as **balls first, strikes second**: a "2-1 count" means two balls and one strike. If you hear a broadcaster say "he's behind in the count," it means the batter has more strikes than balls, and the pitcher has the advantage.

Understanding the count is essential for scoring, because most at-bat outcomes are defined by what happens when the count reaches its limits.

## What the Count Means

A **ball** is a pitch outside the strike zone that the batter doesn't swing at. Balls favor the batter — accumulate four of them and the batter takes first base automatically. This is called a [walk (BB)]({{< relref "/docs/at-bats/walks-hbp" >}}).

A **strike** is a pitch in the strike zone (whether swung at or not), a pitch swung at and missed, or a foul ball. Strikes favor the pitcher — three of them and the batter is out. This is a [strikeout]({{< relref "/docs/at-bats/strikeouts" >}}).

The count starts at 0-0 every at-bat and progresses from there. The at-bat continues until one of three things happens: the count reaches four balls (walk), three strikes (strikeout), or the batter puts the ball in play.

## The Count Ranges

| Count | Situation | Who has advantage |
|-------|-----------|-------------------|
| 0-0 | Fresh start | Neutral |
| 3-0 | Three balls, no strikes | Strong batter's count |
| 3-1 | Three balls, one strike | Batter's count |
| 3-2 | Full count | Neutral — something has to happen |
| 0-2 | No balls, two strikes | Strong pitcher's count |
| 1-2 | One ball, two strikes | Pitcher's count |

**Hitter's counts** (more balls than strikes) are when batters see the most fastballs. Pitchers can't afford to walk batters when they're already behind, so they come into the zone. Smart batters sit on the fastball in these counts.

**Pitcher's counts** (more strikes than balls) are when pitchers can afford to experiment. They'll throw breaking balls off the plate, trying to get the batter to chase. A batter who expands the zone at 0-2 is giving the pitcher exactly what he wants.

## The Full Count

A **3-2 count** is called the full count, and it's the most dramatic moment in a typical at-bat. The batter can't take another strike. The pitcher can't throw another ball. Everything happens on the next pitch.

On a full count, baserunners typically start running with the pitch — if the pitch is ball four, they'd advance anyway, so there's no reason to wait. This makes full-count pitches exciting: a well-placed breaking ball can freeze the batter, or a high fastball can get lifted for a grand slam.

## Foul Balls and the Count

Foul balls are strikes — with one exception. A foul ball with two strikes does **not** become the third strike. The count stays at two strikes, and the at-bat continues. A batter can foul off pitch after pitch indefinitely at two strikes.

The exception to the exception: a **bunted foul ball with two strikes is the third strike**. The batter is out. This prevents batters from fouling off bunt attempts to extend at-bats indefinitely.

This rule is why a batter who runs up a long pitch count before striking out or walking is genuinely valuable — every extra pitch is work done on behalf of the team, tiring out the pitcher and potentially improving the look for the next hitter.

## How the Count Resets

The count goes back to 0-0 at the start of every new at-bat, every inning, and for every batter regardless of how the previous at-bat ended. The count is purely an in-at-bat phenomenon — it carries no information from one batter to the next.

The one edge case worth knowing: if a pitcher is replaced mid-at-bat, the new pitcher inherits the count exactly as it was. The count doesn't reset on a pitching change. If the previous pitcher ran the count to 3-1 before leaving, the new pitcher walks in facing a 3-1 count.

## In BaseballScorer

BaseballScorer displays the current count in "balls-strikes" format — for example, **2-1** — prominently in the active at-bat card. The count updates automatically after each pitch button tap.

![At-bat card showing pitch dots and count display](/images/screenshots/pitch-dots.jpg)

Auto-conclusions handle the endpoints:

- **4th ball** → at-bat immediately closes as a walk (BB); no extra confirmation needed
- **3rd swinging strike** → at-bat closes as a strikeout (K)
- **3rd called strike** → at-bat closes as a called strikeout (Kc — the backwards K notation)
- **Foul at 2 strikes** → foul dot is recorded, count remains at 2 strikes

This means you can't accidentally "over-tap" your way into an invalid count. The moment the count reaches a conclusion, the at-bat is resolved and the next batter becomes active.

See [pitch tracking]({{< relref "pitch-tracking" >}}) for a full explanation of the pitch buttons and what each color represents.
