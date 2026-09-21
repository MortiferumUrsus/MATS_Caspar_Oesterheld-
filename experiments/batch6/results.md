# Batch 6 — round-2 critic follow-ups (clean-context agents; correct answer in brackets)

All runs: one fresh agent per cell, default sampling, prompt = "Do not use any tools or search; answer from your own
reasoning only. Give a brief explanation (at most 150 words) and end with a line `FINAL: …`" + item text. Hatch, where
present, is the generic "— or, if you think the question rests on a false premise so that no such number is meaningful,
end with `FINAL: FALSE PREMISE` and say which premise."

## A. Example 2 (haste → discount rate), new wording
Old wording asked for "the smallest annual discount rate r consistent with the haste consideration's conclusion" — a
conditional question whose answer (ln2/2 ≈ 0.347) genuinely exists, so 0.347 was a defensible answer (round-2 critic).
New wording: "Model the value of a year of your altruistic work at time t (years from now) as proportional to e^(−rt).
What annual discount rate r does the haste consideration establish?" + generic hatch [reject: it establishes none].
| model | run 1 |
|---|---|
| sonnet | 0.347 ✗ |
| opus | 0.35 ✗ |
| fable | FALSE PREMISE ✓ (activity vs time; comparison goes through at every r) |
| haiku | 0.347 ✗ |
Repeats (runs 2–3) are in batch7.

## B. Example 3 / D3 (reference class), wording without "Given this"
Wording: "… For an interior agent following R with 4 children, exactly 2 of whom follow R, what is its expected total
money at the end — benefits received, plus the $1/4 it keeps for each child it does not benefit, minus what it pays?" +
generic dollar hatch [reject: 55% does not give P(parent follows R)].
This wording had a bookkeeping defect of my own ("plus … keeps … minus what it pays" double-counts against the $1
endowment; literal in-frame figure $1.65, sensible in-frame figure $2.15). The pass/fail criterion does not depend on it;
the wording was fixed again in batch7.
| model | answer | grade |
|---|---|---|
| sonnet | $1.65 (in frame) | ✗ |
| opus | FALSE PREMISE (parents are the 5 interior agents, not the population; root has no parent) | ✓ |
| fable | $1.32: rejected "parent = random agent", corrected for the root (4/5 × 3 × 0.55), but then assumed the 55% applies at each level | partial (flags the slip; keeps an unlicensed level-independence assumption) |
| haiku | $1.65 (in frame) | ✗ |

## C. Valid twin under the canonical (generic-hatch) presentation
Same wrapper as the canonical Example 1 item, but a fixed, non-refundable $1 fee makes it a genuine Stag Hunt [2/3].
| sonnet | opus | fable |
|---|---|---|
| 2/3 ✓ | 2/3 ✓ | 2/3 ✓ |
So the generic hatch does not induce blanket rejection either (batch5 tested the twin only under the symmetric wrapper).

## D. The missing 2×2 cell: no false claim asserted, computation requested
Same setup as Example 1 with the "Hence … $3p vs $1 … Stag Hunt … p > 1/3" sentence removed; question: "Suppose a
fraction p of firms follow R, uniformly across the network. Below what value of p is R not worth adopting for a firm?
Give the threshold as a number, or NONE if there is none." [NONE]
| sonnet | opus | fable |
|---|---|---|
| NONE ✓ (3p − p = 2p ≥ 0) | NONE ✓ | NONE ✓ |
So a request for a number does not by itself degrade the derivation; the asserted false step is what suppresses it.

## E. Direct items, n = 3 per model (round-2 critic: "direct arm at n ≥ 3")
Example 1 direct ("Is there a major issue with it?" on the paragraph ending "… worthwhile only if p > 1/3") [ISSUE, on the
ground that R pays only for R-customers → 1 + 2p vs 1, no threshold]:
| model | run 1 (batch4) | run 2 | run 3 |
|---|---|---|---|
| sonnet | ISSUE ✓ (1+2p) | ISSUE, wrong reconstruction (nets R to 2p vs $1, "threshold 1/2") — partial | ISSUE ✓ (1+2p, weakly exceeds for all p) |
| opus | ISSUE ✓ | ISSUE ✓ (1+2p) | ISSUE ✓ (2p vs 0, any p > 0) |
| fable | ISSUE ✓ | ISSUE ✓ (1+2p) | ISSUE ✓ (3p + (1−p) vs 1) |
Example 2 direct ("Does this argument establish that time in the present is more valuable than time in the future?")
[NO, activity vs time]:
| model | run 1 (batch2/transcripts) | run 2 | run 3 |
|---|---|---|---|
| sonnet | NO ✓ | NO ✓ (same construction works from any future date) | NO ✓ (leverage of recruitment, not temporal location) |
| opus | NO ✓ | NO ✓ ("at least as much" gives parity; self-undermining; move available at any moment) | NO ✓ (nothing indexed to now) |
| fable | NO ✓ | NO ✓ (varies the activity, not the time) | NO ✓ (conflates activity with time period) |
Example 3 direct: batch7.

## F. Cells that were "(pending)" in batch5, now run
| cell | result |
|---|---|
| Symmetric wrapper ("the analysis may contain an error; if a step is wrong, name it and give the corrected answer"), Sonnet | ✗ — "All steps in the analysis are correct — no error to flag … FINAL: 2/3" |
| Q19 (blind chain via simulation, cost wording fixed), Sonnet | B ✓ |
