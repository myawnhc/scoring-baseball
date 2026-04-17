---
title: "Scoring Along with Live MLB Games"
weight: 10
description: "How to use BaseballScorer's MLB live feed integration to score along with real games, catch up on missed plays, and verify your scoring against the official record."
---

# Scoring Along with Live MLB Games

One of the best ways to practice scorecard keeping is to score a real game as it happens. You follow along with the broadcast, record each pitch and play, and end up with a complete record of everything that happened. It's deeply satisfying — and it sharpens your eye for the game in ways that just watching never does.

BaseballScorer connects directly to MLB's live data feed, which opens up a few capabilities that paper scorecards can't offer: automatic catch-up when you fall behind, and reconciliation that checks your scoring against the official record.

## How the Connection Works

BaseballScorer polls `statsapi.mlb.com` every 30 seconds during an active game. This is MLB's own public data service — no API key required, no subscription, no third-party middleman. When you open a game you've already started scoring, the app checks the live feed in the background and flags anything it can fill in or verify.

The connection is read-only. BaseballScorer uses the feed to help you score more accurately, but your scorecard is always yours. You control what gets recorded.

<!-- TODO: Screenshot of the MLB live feed indicator in the scoring view header -->

## Catching Up When You Fall Behind

Real games don't pause while you're grabbing a snack, arguing about a call, or explaining to your kid why the infield fly rule exists. Falls behind happen. BaseballScorer gives you three ways to catch up:

**Next Play** — Fills in the very next unscored play from the live feed, one at a time. Good when you've only missed one or two batters and want to review each play before accepting it.

**Catch Me Up** — Fills in all plays from wherever your scoring left off up to the current moment in the game. If you stepped away for an inning, this gets you current instantly.

**All** — Fills in everything in the live feed, from the beginning of the game to the most recent completed play. Useful if you want to start a scorecard for a game already in progress, or if you're scoring a completed game after the fact.

All three options auto-fill only plays that haven't been scored yet. They won't touch anything you've already entered manually.

<!-- TODO: Screenshot of the Catch Me Up / Next Play / All buttons in the toolbar -->

## How Auto-Fill Works

When BaseballScorer fills a play from the live feed, it matches the at-bat by batter and inning, then populates the result: the outcome (hit, out, walk, etc.), the fielding sequence, any RBIs, and runner movements. The pitch sequence isn't auto-filled — the live feed doesn't include pitch-by-pitch data for every game.

Auto-filled at-bats are marked with a **blue arrow icon** on the scorecard card, so you can always tell at a glance which plays you scored yourself and which came from the feed. This matters if you want to go back and fill in pitch sequences manually, or if you just want to know how complete your manual scoring is.

For more on the auto-fill mechanics, see [Auto-Fill from the MLB Feed]({{< relref "auto-fill" >}}).

<!-- TODO: Screenshot of a scorecard card with the blue arrow auto-fill indicator -->

## Reconciliation: Checking Your Work

Here's where the MLB integration becomes genuinely useful for anyone who wants to score accurately: reconciliation.

After you've scored a play manually, BaseballScorer compares your entry against the official MLB feed data. If it finds a meaningful difference — wrong fielding sequence, missed RBI, incorrect base advancement — it flags the discrepancy and lets you correct it.

Reconciled at-bats get a **blue sync icon** instead of the blue arrow. This tells you: "This play was scored manually, then checked and confirmed (or corrected) against the official record."

Reconciliation only flags meaningful differences. If you recorded a 6-3 groundout and MLB shows the same thing, no flag. If you recorded a single but MLB shows an error, you'll be notified.

<!-- TODO: Screenshot of the blue sync reconciliation icon on a card -->

## Reset to Here

If you want to use the live feed to fill in only the plays you've missed — without touching anything you've already scored — use **Reset to Here**. This is different from "Catch Me Up" in one important way: it fills missing plays without overwriting any manual scoring you've done.

Use Reset to Here when you've been scoring along but got distracted for a few batters. Your existing work stays intact; only the gaps get filled.

## A Practical Workflow

If you're scoring a game from the start:

1. Start the game in BaseballScorer as you normally would.
2. Score each play manually as it happens.
3. If you fall behind, tap **Next Play** to fill in one play, or **Catch Me Up** to fill in everything.
4. Review auto-filled plays and add pitch sequences if you want them.
5. Watch the reconciliation icons appear as the feed confirms your scoring.

If you want to score a completed game:

1. Start the game in BaseballScorer.
2. Tap **All** to auto-fill the entire game from the feed.
3. You'll have a complete scorecard in seconds, with every at-bat marked with the blue arrow indicator.
4. Go back and add detail wherever you want.

## What the Feed Doesn't Cover

A few things are outside what the live feed provides:

- **Pitch sequences** — Ball/strike sequences for most games aren't available in the feed. You'll score those manually as you watch.
- **Pitch types and velocities** — Not in the public feed.
- **Pickoff attempts and mound visits** — These won't appear in auto-filled plays.

The live feed is excellent for outcomes, fielding, and baserunner events. For the pitch-by-pitch story of each at-bat, that's still your job as the scorer.

---

Scoring along with MLB games is one of the most rewarding uses of a scorecard. BaseballScorer's live feed integration means you don't have to choose between paying attention to the game and keeping an accurate record — if you fall behind, you can catch up, and the app will tell you where your scoring and the official record agree.
