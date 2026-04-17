---
title: "Notation Cheat Sheet"
weight: 10
description: "The complete baseball scorecard notation reference — every symbol, what it means, and how it appears in BaseballScorer. Bookmark this page."
---

# Notation Cheat Sheet

This is the page to bookmark. Every notation used in baseball scoring, organized by category, with the color each one appears in BaseballScorer. Print it, screenshot it, or just keep this tab open while you score.

If you want deeper explanations of any category, the links below each section point to the full documentation.

---

## Hits

Hits are recorded in **green** — the batter reached base safely.

| Notation | Meaning |
|---|---|
| `1B` | Single |
| `2B` | Double |
| `3B` | Triple |
| `HR` | Home run |

A home run with runners on base gets additional runner notation. A solo shot is just `HR`. See [recording hits]({{< relref "/docs/at-bats/hits" >}}) for how to handle each type.

---

## Walks and Free Passes

Also **green** — the batter reaches base.

| Notation | Meaning |
|---|---|
| `BB` | Base on balls (walk) |
| `IBB` | Intentional walk |
| `HBP` | Hit by pitch |

`HBP` appears in **purple** in BaseballScorer to distinguish it from other green outcomes. See [walks and HBP]({{< relref "/docs/at-bats/walks-hbp" >}}).

---

## Outs: Strikeouts

Strikeouts appear in **red**.

| Notation | Meaning |
|---|---|
| `K` | Strikeout swinging |
| Backwards K | Strikeout looking (called third strike) |

The traditional paper convention for a called strikeout is a backwards K — the letter K mirrored horizontally. BaseballScorer renders it the same way, flipping the K on screen just like you'd see on paper or on the K-count signs fans hang at the ballpark. See [strikeouts]({{< relref "/docs/at-bats/strikeouts" >}}).

---

## Outs: Ground Outs

Ground outs appear in the **default** color (no special color — these are the most common outs).

| Notation | Meaning | Example |
|---|---|---|
| `N-N` | Fielder to fielder | `6-3` = shortstop to first base |
| `NU` | Unassisted | `3U` = first baseman unassisted |

The numbers refer to fielder positions. See [fielder numbers](#fielder-position-numbers) below.

A 6-3 groundout means: shortstop fielded it, threw to first base for the out. A 3U means the first baseman fielded and touched the bag himself.

---

## Outs: Fly Outs and Line Drives

Also **default** color.

| Notation | Meaning | Example |
|---|---|---|
| `FN` | Fly out | `F8` = fly out to center field |
| `LN` | Line drive out | `L6` = line drive caught by shortstop |
| `FFN` | Foul fly out | `FF2` = foul pop-up caught by catcher |

The `F` prefix indicates a fly ball caught in the air. `L` indicates a line drive caught before it hits the ground. `FF` is specifically a foul fly.

---

## Errors

Errors are **green** — the batter reached base (even though it was the fielder's fault).

| Notation | Meaning |
|---|---|
| `EN` | Error by fielder N | `E6` = error by the shortstop |

The batter's scorecard box gets the `E` notation. The error is also tracked against the fielder in question. See [errors and fielder's choice]({{< relref "/docs/at-bats/errors" >}}).

---

## Fielder's Choice

**Green** — batter reached base (though a preceding runner may have been put out).

| Notation | Meaning |
|---|---|
| `FC N-N` | Fielder's choice with fielding sequence | `FC 6-4` = fielder chose to retire runner at second |

Fielder's choice means the fielder had a choice of who to retire and chose a base other than first. The batter is credited with reaching base, not with a hit. See [errors and fielder's choice]({{< relref "/docs/at-bats/errors" >}}).

---

## Sacrifices

Sacrifices appear in the **default** color — the batter is out, but it's a productive out.

| Notation | Meaning | Example |
|---|---|---|
| `SAC N-N` | Sacrifice bunt | `SAC 1-3` = pitcher to first, runner advances |
| `SFN` | Sacrifice fly | `SF8` = sacrifice fly to center field |

A sacrifice bunt advances a runner intentionally; the batter isn't charged with an at-bat. A sacrifice fly scores a runner from third on a caught fly ball; also not charged as an at-bat. See [sacrifices and bunts]({{< relref "/docs/at-bats/sacrifices" >}}).

---

## Double Plays

Double play notation is added to the base out notation. **Default** color.

| Notation | Meaning |
|---|---|
| `N-N DP` | Double play, any fielding sequence | `6-4-3 DP` = classic around the horn |
| `F N DP` | Line drive double play | `L6 DP` = lined to short, doubled off first |

The `DP` suffix can be appended to any out notation when two outs result from the same play. See [double and triple plays]({{< relref "/docs/at-bats/double-plays" >}}).

---

## Unknown / Unscored

**Orange** — something happened but it wasn't recorded.

| Notation | Meaning |
|---|---|
| `?` | Outcome unknown or not yet scored |

The `?` notation marks an at-bat that was skipped or couldn't be determined. It's better than leaving the box blank — it signals that the gap is intentional.

---

## Baserunner Events

These appear on the baserunner's path between bases, not in the at-bat box.

| Notation | Meaning | Color |
|---|---|---|
| `SB` | Stolen base | Green |
| `CS` | Caught stealing | Red |
| `WP` | Wild pitch advanced | Brown |
| `PB` | Passed ball advanced | Brown |
| `BK` | Balk | Brown |
| `E` | Advanced on error | Green |

See the Baserunning section for how to record runner movements.

---

## Fielder Position Numbers

Every fielding notation uses these standard position numbers:

| Number | Position | Abbreviation |
|---|---|---|
| 1 | Pitcher | P |
| 2 | Catcher | C |
| 3 | First baseman | 1B |
| 4 | Second baseman | 2B |
| 5 | Third baseman | 3B |
| 6 | Shortstop | SS |
| 7 | Left fielder | LF |
| 8 | Center fielder | CF |
| 9 | Right fielder | RF |

These numbers are universal — you'll see them in box scores, broadcast graphics, and every scoring system ever used.

In BaseballScorer, fielder numbers appear on the diamond during fielding sequences. Tap the fielders who touched the ball, in order, to record the play. See [ground outs]({{< relref "/docs/at-bats/ground-outs" >}}) for the full fielding sequence flow.

<!-- TODO: Screenshot of the diamond with fielder numbers visible during a fielding sequence -->

---

## Quick Reference: Colors

| Color | Used for |
|---|---|
| Green | Hits, walks, errors, FC, stolen bases, safe outcomes |
| Red | Strikeouts (K and backwards K), caught stealing |
| Orange | Called strikes, fouls, unknown (`?`) |
| Purple | HBP |
| Blue | In play, auto-filled plays, MLB sync |
| Brown | WP, PB, balk |
| Default | Ground outs, fly outs, sacrifices, double plays |

For the full color guide, see [BaseballScorer Color Guide]({{< relref "color-guide" >}}).
