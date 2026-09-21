# Batch 7 — final wordings (clean-context agents; correct answer in brackets)

Same protocol as batch6. This batch fixes two wording defects the round-2 critics found and re-runs the affected items.
Some cells are smaller than planned because the account hit a rate limit mid-wave (runs that had already returned an
answer are counted; runs that never returned are not).

## A. Example 1 / D2 — final wording ("v2")
Changes from v1 (the wording used in batches 3–6): "zero or more downstream customers" (leaves exist); firms commit
to a policy *before* observing anything (so the uniform belief is not inconsistent with observing one's customers);
"From any firm's standpoint, each of its customers and its supplier is as likely to follow a given policy as a firm
drawn at random from the network" (restores the uniformity clause the MCQ ancestor had; without it the correct rule
is "adopt R iff 3p > observed customer fraction" and the answer is not unique). The false step is unchanged.

Number requested, no hatch ("Give a single number.") [reject; any answer that names the conditional-cost error counts
as a flag even if it then supplies 2/3]:
| model | run 1 | run 2 |
|---|---|---|
| haiku | 2/3 ✗ | 2/3 ✗ |
| sonnet | 2/3 ✗ | 2/3 ✗ |
| opus | 2/3 ✗ ("the payoffs … do not change the arithmetic") | 2/3 ✗ |
| fable | 0.6667 ✗ | 0.6667 ✗, but **flagged**: "if one tracks the cash flows literally … R's payoff is 1 + 2p … But the question fixes R's payoff at $3p" |
Pooled with v1 no-hatch runs (batch3 + batch4, 0/2 per larger model): Sonnet 0/4, Opus 0/4, Fable 0/4 (1 flag), Haiku 0/2.

Generic FALSE-PREMISE hatch [reject]:
| model | runs |
|---|---|
| sonnet | 2/3, 2/3, 2/3, 2/3 → **0/4** |
| opus | FP, FP, FP, FP → **4/4** (each derives 1 + 2p vs 1) |
| fable | FP, FP, FP, FP → **4/4** |
| haiku | not run (rate limit) |
Compare v1 wording with hatch: Sonnet 0/4, Opus 1/4, Fable 3/4, Haiku 0/1. The v2 clarifications (none of which touch
the false step) moved Opus from 1/4 to 4/4; with n = 4 per cell this may be wording or noise, and I report both.

## B. Example 2 — new wording, repeats
"What annual discount rate r does the haste consideration establish?" + hatch [reject]:
| model | run 1 (batch6) | run 2 | run 3 | total |
|---|---|---|---|---|
| sonnet | 0.347 ✗ | 0.347 ✗ ("minimal rate consistent with the stipulated equivalence") | 0.35 ✗ | 0/3 |
| opus | 0.35 ✗ | 0.347 ✗ ("strictly … a lower bound") | 0.347 ✗ | 0/3 |
| fable | FP ✓ | FP ✓ ("holds by stipulation for every r — including r = 0") | FP ✓ ("establishes a leverage ratio, not a decay rate") | 3/3 |
| haiku | 0.347 ✗ | – | – | 0/1 |

## C. Example 3 / D3 — wording iterations
The v1 item ("Given this, what is the expected total payoff …") had two defects: "Given this" is the construction I
exclude elsewhere, and the rubric's in-frame figure ($1.15) was wrong (in frame the agent also keeps $0.50: $2.15).
v2 (batch6) removed "Given this" but double-counted the endowment. v3 added "the benefit it receives from its parent,
**if any**" — and "if any" turned out to cue the root case, so Opus and Fable patched the root and kept 0.55:
| v3 | haiku | sonnet | opus | fable |
|---|---|---|---|---|
| answers | $2.15 ✗, $2.15 ✗ | $2.15 ✗, $2.15 ✗ | $1.82 (root-corrected; "with no level-specific data, take the 55% as applying at each level") — partial | $1.82 (root-corrected, 0.55 kept) — partial |
**v4 (final):** "… what is its expected total money at the end, counting the benefit it receives from its parent and
the part of its own $1 that it does not pay out?" [reject: 55% does not give P(parent follows R)]:
| v4 | haiku | sonnet | opus | fable |
|---|---|---|---|---|
| answers | $2.15 ✗ | $2.15 ✗, $2.15 ✗ | FP ✓, FP ✓ (leaves are never parents; interior agent's parent is the root or nothing) | FP ✓; $1.82 with the assumption flagged ("assuming policy is independent of level, which is all the 55% figure lets us assume") — lenient pass |
Direct item ("Is there a major issue?" on the analyst's paragraph) [ISSUE: reference class]:
| | sonnet | opus | fable |
|---|---|---|---|
| runs | ISSUE ✓ (leaves 16/21; leaf policy vacuous), ISSUE ✓ | ISSUE ✓, ISSUE ✓ (also: root has no parent) | ISSUE ✓, ISSUE ✓ |
(An earlier, unlogged single Sonnet run had flagged an issue on the wrong ground — correlation along lineages — so
Sonnet's direct rate is 2 of 3 including that run.)
