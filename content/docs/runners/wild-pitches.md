---
title: "Wild Pitches and Passed Balls"
weight: 20
description: "How to score a wild pitch (WP), passed ball (PB), and balk — the difference between them and how they advance runners."
---

# Wild Pitches and Passed Balls

Wild pitches and passed balls are two different ways a pitch can get away from the battery — the pitcher-catcher tandem — allowing baserunners to advance. They happen mid-at-bat, between pitches, completely independently of the batter. Knowing the difference between them, and how to record each, is one of the finer points of keeping a complete scorecard.

## Wild Pitch (WP)

A wild pitch is the **pitcher's fault**. The pitch was thrown so far out of the zone — too high, too low, too far outside — that a catcher making a reasonable effort could not have stopped it. The ball gets by, and any runners on base can advance.

Notation: **WP** is written along the base path segment the runner traversed, or in the margin alongside the pitch sequence. On the mini diamond, the runner's path gets a WP label at the relevant segment.

In official statistics, a wild pitch is charged to the pitcher. It doesn't affect ERA — earned runs are calculated separately — but it does appear in pitching records as a counting stat. A pitcher with a lot of wild pitches is generally struggling with command, which tells a story worth tracking.

**WP and the pitch count:** A wild pitch is still a pitch. If the pitch was a ball (outside the zone, hence wild), it counts as a ball in the at-bat's count. This means a WP can contribute to walking a batter — you might see a walk credited partly to a sequence that included a wild pitch. In [pitch tracking mode]({{< relref "/docs/pitches/pitch-tracking" >}}), the pitch is recorded as a ball with the WP annotation alongside it.

## Passed Ball (PB)

A passed ball is the **catcher's fault**. The pitch was catchable — a catcher making a reasonable effort should have held it — but the catcher failed to do so, and runners advanced as a result.

Notation: **PB** is written the same way as WP, along the relevant base path segment.

The catcher is charged with a passed ball in official statistics. Unlike wild pitches, passed balls are purely a defensive stat — they don't interact with the pitch count or the at-bat's ball-strike numbers. A passed ball on a strike is still a strike; the at-bat continues from wherever it was.

## The Gray Area

The WP vs. PB distinction is one of the trickier calls an official scorer makes. On a borderline pitch that gets away — say, a hard slider in the dirt — the scorer has to judge whether a competent catcher should have blocked it. Over the decades, official scoring has trended toward charging pitchers more often (more WPs), partly because elite blocking has become more expected at the catcher position.

For casual scoring purposes, you can use your own judgment. If it looked like the pitcher bounced it three feet in front of the plate and the catcher had no chance, that's a WP. If the pitch was catchable and the catcher just blew it, that's a PB. When in doubt, go with WP — that's also what official scorers tend to do.

## Balk

A balk is a different kind of infraction — it's not about a pitch going wild, it's about the pitcher making an illegal motion. Balks are called when a pitcher deceives or fails to properly complete a pitching motion with runners on base. Common violations include:

- Starting a pitching motion and stopping without throwing
- Not coming to a complete stop in the set position
- Throwing to a base with an improper or incomplete motion
- Failing to step toward first on a pickoff throw (rules vary)

When a balk is called, **all runners advance one base automatically**. There's no play — no throw, no tag. Every runner just moves up. If there's a runner on third, that's a run scoring on a balk.

Notation: **BK** is written on each runner's path at the base they advanced to, or in the margin. It's one of the few events that affects all runners simultaneously.

Unlike WP and PB, a balk doesn't change the pitch count. The at-bat pauses, runners advance, and play resumes from the same count.

<!-- TODO: Screenshot of mini diamond showing multiple runner advancement with BK notation -->

## Per-Runner Advancement

Not every wild pitch or passed ball advances every runner. A WP with runners on first and third might advance the runner from first to second while the runner on third stays put — maybe the run doesn't matter, maybe the runner was caught off guard. You need to record each runner's decision separately.

This is important for accuracy. If a WP moves the runner from first to second but the runner on third doesn't score, the third-base runner is still on third. Record the WP segment only for the runner who actually moved.

## In BaseballScorer

When there are runners on base, three additional buttons appear in the active at-bat controls: **WP**, **PB**, and **Balk**.

![Pitch input buttons showing WP, PB, and Balk options when runners are on base](/images/screenshots/pitch-input-buttons.jpg)

Tapping **WP** or **PB** opens a per-runner prompt: for each runner currently on base, you're asked whether that runner advanced. This lets you accurately record partial advancements — runner on first advances, runner on third stays — without having to manually edit each base.

Tapping **Balk** automatically advances all runners one base simultaneously. No per-runner prompt is needed because a balk moves everyone; you just confirm the action.

After the WP or PB is recorded, the pitch count updates appropriately (WP counts as a ball if it was a ball-in-the-dirt), runners are shown at their new positions on the diamond, and the at-bat continues. The event appears in the at-bat log for that inning.

For stolen base and other mid-at-bat runner movements, see [stolen bases]({{< relref "stolen-bases" >}}). For tag-up situations after a fly out is caught, see [tag ups]({{< relref "tag-ups" >}}).
