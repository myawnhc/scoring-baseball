---
title: "Fielder Position Numbers"
weight: 30
description: "The standard baseball position numbering system — which number is which fielder, and why it matters for scoring."
---

# Fielder Position Numbers

Every position on the baseball field has a number. These numbers are the backbone of scoring notation — when you write "6-3" on a scorecard, you're saying the shortstop (6) threw the ball to the first baseman (3) for the out. If you don't know the numbers, the notation is just hieroglyphics. So let's fix that.

## The Nine Positions

Here's the standard numbering, starting from the pitcher and working outward:

![Baseball fielder position numbers — each position labeled 1 through 9 on the field](/images/diagrams/fielder-positions.svg)

| Number | Position | Abbreviation |
|--------|----------|-------------|
| 1 | Pitcher | P |
| 2 | Catcher | C |
| 3 | First Base | 1B |
| 4 | Second Base | 2B |
| 5 | Third Base | 3B |
| 6 | Shortstop | SS |
| 7 | Left Field | LF |
| 8 | Center Field | CF |
| 9 | Right Field | RF |

Some leagues (softball, certain youth formats) add a 10th position — the short fielder (SF), who plays a shallow outfield role.

## Why These Numbers?

The numbering follows a rough path around the diamond. The battery (pitcher and catcher) are 1 and 2. Then the infield goes around the bases: first base (3), second base (4), third base (5), shortstop (6). The outfield goes left to right: left field (7), center field (8), right field (9).

The only one that feels out of order is shortstop at 6 — you'd expect the infield to go 3, 4, 5, 6 around the bases, putting shortstop between second and third. The reason is historical: the shortstop position didn't exist when the original numbering was assigned. It was added later, and got the next available number.

## How the Numbers Show Up in Scoring

These numbers are used everywhere in scoring notation:

- **"6-3"** — Shortstop fielded the ball and threw to first base. Ground out.
- **"F8"** — Fly out caught by center fielder.
- **"E5"** — Error committed by the third baseman.
- **"6-4-3 DP"** — Double play: shortstop to second baseman to first baseman.
- **"3U"** — Unassisted out by the first baseman (he fielded it and stepped on the bag himself).

The numbers always describe the order in which fielders handled the ball. On a groundout, the first number is who fielded it, and the last number is who caught the throw for the out. On a double play, you'll see three numbers — the fielder, the pivot man, and the first baseman.

## Memorizing the Numbers

Most scorers internalize these within a game or two. A few tricks:

- **1-2** is easy — pitcher and catcher, the battery.
- **3-4-5** goes around the infield bases: first, second, third.
- **6** is the odd one out — shortstop, between second and third.
- **7-8-9** goes left to right across the outfield, matching how you'd read them from behind home plate.

Once you've scored a few innings, writing "6-3" for a routine grounder to short becomes as natural as typing your name.

## In BaseballScorer

When you record an out in the app, fielder position numbers appear directly on the interactive diamond. Tap the fielders in the order they handled the ball — tap 6 (shortstop), then 3 (first base) — and the app builds the notation for you.

![Fielding sequence view with fielder position numbers on the diamond](/images/screenshots/fielding-sequence.jpg)

The same numbers appear in the completed notation on batter cards, the scorecard grid, and everywhere else a fielding play is displayed.
