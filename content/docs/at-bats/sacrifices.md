---
title: "Sacrifices"
weight: 85
description: "How to score sacrifice bunts and sacrifice flies in baseball. SAC and SF notation, when each applies, and how BaseballScorer detects them."
---

# Sacrifices

A sacrifice is an out that was worth making. The batter gave themselves up — intentionally or by circumstance — to advance a runner. In return, the rules reward them by not counting it as an at-bat, which protects their batting average.

There are two types: the sacrifice bunt and the sacrifice fly.

## SAC — Sacrifice Bunt

The batter bunts the ball, is retired at first base, but advances one or more runners. Write **SAC** (or **SH** for sacrifice hit — both are used) in the cell, followed by the fielding sequence.

Examples:
- **SAC 1-3** — batter bunts to the pitcher, who throws to first
- **SAC 5-3** — third baseman fields the bunt, throws to first

<!-- TODO: Screenshot of BaseballScorer showing a sacrifice bunt recorded in the scorecard -->

### When It Counts as a Sacrifice

The official rule: a sacrifice bunt requires that the batter was clearly trying to bunt *to advance a runner*, that they were retired, and that at least one runner advanced. If the batter bunts and the defense botches it — letting the batter reach safely — it's either a hit or a fielder's choice, not a sacrifice.

Intent matters, but scorers use outcome as their guide. If the batter is out and a runner moved up, call it a sacrifice.

### Not an At-Bat

A sacrifice bunt does not count as an at-bat. The batter's plate appearances increase, but their at-bats don't. This means their batting average is unaffected — the rules recognize they made a productive out on purpose.

## SF — Sacrifice Fly

The batter hits a fly ball that is caught for an out, but a runner from third base tags up and scores. Write **SF** followed by the fielder who made the catch.

Examples:
- **SF8** — sacrifice fly caught by the center fielder, runner scores from third
- **SF9** — caught by the right fielder, runner scores from third

### When It Counts as a Sacrifice Fly

Three conditions:
1. The fly ball is caught (it's an out)
2. A runner scores from third base on the tag-up
3. Fewer than two outs (with two outs, the inning would end on the catch — but if the runner scores before the third out is recorded, it still counts)

Unlike the sacrifice bunt, the defense has a choice on a sacrifice fly — they *could* let the ball drop to keep the runner from scoring. They don't, because catching it is usually the right play (especially to prevent extra-base damage). The batter exploited that.

### Not an At-Bat

Same protection as the sacrifice bunt — the SF doesn't count as an at-bat. The plate appearance counts; the at-bat doesn't.

<!-- TODO: Screenshot of BaseballScorer's sacrifice fly detection prompt -->

## In BaseballScorer

**Sacrifice bunt:** Record the at-bat as a ground out and select the fielding sequence. BaseballScorer will offer a context option to mark it as a sacrifice bunt, which removes the at-bat from the batter's totals and flags the notation as SAC.

**Sacrifice fly:** When a runner is on third with fewer than two outs and you record a fly out, BaseballScorer prompts you to confirm whether the runner scored on the play. If you confirm the run, BaseballScorer automatically classifies the out as a sacrifice fly (SF), credits the run, and removes the at-bat from the batter's totals.

If the runner on third did *not* score — the fly was too shallow, or the tag-up throw beat them — just record the fly out normally and resolve the runner as staying at third. It's a regular fly out, not a sacrifice fly.

BaseballScorer won't force a sacrifice fly classification on you. If the situation doesn't match (runner didn't actually score, or you decide it wasn't a true sac fly attempt), just record it as a standard fly out.
