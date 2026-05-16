---
title: "Dropped Third Strike"
weight: 55
description: "How to score an uncaught third strike — when the rule applies, the six common notations (K-WP, K-PB, K 2-3, K 2T, K E2, K E3), and the statistical impact on pitcher, catcher, and earned runs."
---

# Dropped Third Strike

A strikeout is not always an out. If the catcher fails to cleanly catch the third strike, the batter may attempt to run to first base — and depending on what happens next, the play can be recorded six different ways. This is one of baseball's stranger rules and one of the more common spots where casual scorers get stuck.

## When the Dropped Third Strike Rule Applies

The rule (MLB Rule 5.05(a)(2), with the same logic in most amateur rulebooks) lets the batter run on a third strike that the catcher does not catch cleanly, but only when **either** of these is true:

- **First base is unoccupied**, regardless of the number of outs, **or**
- **There are two outs**, regardless of whether first base is occupied

The two-outs exception exists because the rule's original purpose was to prevent a catcher from intentionally dropping the third strike to start an easy force-play double play. With two outs already, no double play is available — so the catcher can be required to make the throw.

If first base is occupied with fewer than two outs, the batter is automatically out on the third strike no matter how the catcher handles the ball. There's no D3K to record; it's a straight strikeout.

## The Six Notations

When the rule applies, what happens next determines the notation. There are six common outcomes, all of which still credit the pitcher with a strikeout.

### K-WP — Batter Reaches on a Wild Pitch

The third strike was uncatchable — bounced in the dirt, sailed past, or otherwise impossible for the catcher to handle. The batter runs and reaches first safely. Record it as **K-WP**: strikeout with a wild pitch.

The pitcher gets the strikeout *and* a wild pitch charged against them. The catcher is not charged with anything.

### K-PB — Batter Reaches on a Passed Ball

Same outcome, different fault. The third strike was catchable — a competent catcher should have held it — but the catcher failed to. Record it as **K-PB**: strikeout with a passed ball.

The pitcher gets the strikeout. The catcher is charged with a passed ball.

The WP-vs-PB judgment is the same one made on any other pitch that gets away. See [Wild Pitches and Passed Balls]({{< relref "/docs/runners/wild-pitches" >}}) for the rules of thumb.

### K 2-3 — Catcher Throws to First for the Out

The catcher recovers the dropped strike and throws to first in time to retire the batter. Record it as **K 2-3**: strikeout, catcher (2) to first baseman (3). It's an out, recorded with both the K notation and the fielding sequence.

The pitcher gets the strikeout. The catcher gets an assist. The first baseman gets the putout.

### K 2T — Catcher Tags the Batter for the Out

If the batter doesn't make it far before the catcher recovers, the catcher can simply tag the batter for the out. Record it as **K 2T**: strikeout, with the "T" indicating a tag rather than a throw.

The pitcher gets the strikeout. The catcher gets the putout (no assist — there was no throw).

### K E2 — Catcher's Error on the Throw

The catcher recovers the dropped strike and throws to first, but the throw is wild — pulled off the bag, in the dirt, into the runner. The batter reaches safely on the error. Record it as **K E2**: strikeout with an error on the catcher (position 2).

The pitcher gets the strikeout. The catcher is charged with an error. No passed ball — the dropped catch wasn't the play; the bad throw was.

### K E3 — First Baseman's Error

The catcher's throw is on target, but the first baseman drops it or pulls off the bag. Record it as **K E3**: strikeout with an error on the first baseman (position 3).

The pitcher gets the strikeout. The first baseman is charged with an error.

## How Each Variant Affects the Pitcher's Line

In every variant above, the pitcher's K column ticks up. That's important: a strikeout always counts for the pitcher, regardless of whether the batter ultimately reached base. The K stat is about the pitch sequence — three strikes — not about what happened after.

What differs is the **out**. Three of the six variants (K, K 2-3, K 2T) retire the batter and credit the pitcher with an out (one-third of an inning). The other three (K-WP, K-PB, K E2, K E3) place the batter on first; no out is credited to the pitcher's IP.

This is occasionally confusing to scorers used to the simpler "strikeout = out" rule, but the official scoring rules are explicit: a strikeout is recorded regardless of whether the batter reached base.

## Earned Runs and the Reconstructed-Outs Algorithm

If a D3K leads to runs scoring later in the inning, those runs may be unearned. The rule: when the official scorer is determining earned runs, they reconstruct the inning *as if the defense had recorded every out it should have*. Each strikeout — including K-WP, K-PB, and K E2/E3 — counts as a "would-be out" in that reconstruction.

So if a pitcher allows a K-WP that should have been the third out, and then gives up two more hits and a run, the run is unearned. The pitcher had three "would-be outs" before the run scored; the run only happened because of the dropped strike (which is a defensive failure, not the pitcher's fault for stats purposes).

This logic is the same as the more familiar "errors extend the inning" earned-run rule — D3K errors and dropped catches are just one specific case of defensive failures contributing to runs that wouldn't have scored otherwise.

## Common Scenarios

**Two outs, runner on first, strikeout in the dirt.** The catcher must throw to first — the batter can run because there are two outs. If the throw is in time, K 2-3 (third out, inning over). If the throw beats the batter but pulls the first baseman off the bag, K E3 (batter safe, inning continues). If the catcher doesn't even attempt the throw, K-WP or K-PB.

**Two outs, bases empty, strikeout in the dirt.** Same rule applies. The catcher must retire the batter. K-WP or K-PB if the batter reaches; K 2-3 / K 2T if the catcher recovers in time.

**One out, bases empty, strikeout in the dirt.** The batter can still run — first base is unoccupied. Same six variants apply.

**One out, runner on first, strikeout in the dirt.** The batter is automatically out, regardless of what the catcher does. Just a straight K. The runner on first cannot advance on the dropped strike unless the catcher's throw goes wild (then it's a separate WP advancement).

## In BaseballScorer

BaseballScorer supports all six variants directly through the K and Kc buttons.

**With pitch tracking on**, after recording two strikes, long-press the Called Strike or Swinging Strike button to open the dropped-third-strike menu. Pick the variant that matches the play; BaseballScorer records the third-strike pitch and the variant in one shot.

**Without pitch tracking**, long-press the K or Kc button in the outcome panel for the same menu.

**To fix a strikeout you already recorded** (it turns out the catcher dropped the pitch, but you'd already tapped K), open the at-bat in review mode, choose "Edit Scoring," and long-press K again to switch into any variant. The inning's out count, the batter's position, the pitcher's IP, and the inning's error column all update automatically.

The scorecard notation appears as **K-WP**, **K-PB**, **K 2-3**, **K 2T**, **K E2**, or **K E3** depending on the variant — exactly matching the conventions described above. Backwards-K variants (called strikeouts) work the same way: **Kc-WP**, **Kc 2-3**, etc.

For the broader rules around strikeouts, see the [Strikeouts]({{< relref "strikeouts" >}}) page. For wild pitch and passed ball mechanics during regular at-bats (not on strike three), see [Wild Pitches and Passed Balls]({{< relref "/docs/runners/wild-pitches" >}}).
