# Batch 4 — robustness repeats and new embedded frames (clean-context agents)

## Repeats
| item | sonnet | opus | fable |
|---|---|---|---|
| R1-P2 (embedded, WITH escape hatch); correct = FALSE PREMISE | 2/3, 2/3, 2/3 → **0/3 correct** (incl. batch-3 run: 0/4) | 2/3, 2/3, FP → **1/3 correct** (incl. batch-3: 1/4) | FP, FP, (rep2 pending) → **≥2/3 correct** (incl. batch-3: ≥3/4) |
| R1-P (embedded, NO hatch, "give a single number") | 2/3 ✗ (1/1) | 2/3 ✗ (1/1) | 2/3 ✗ (1/1) |
| R1 direct ("is there a major issue?") | ✓ | ✓ | ✓ |
| D1 (CDT + sim, original wording with option A "CDT always two-boxes") | A ✗ ×3 | B ✓ ×2 | B ✓ ×2 |
| D1 paraphrase (neutral options; "flesh-and-blood person") | B ✓ (1 of 2; second pending) | – | – |

Reading: (i) the R1-P frame-compliance effect is robust for Sonnet and present for Opus; Fable resists when an explicit
escape hatch is offered but complied when only a number was requested. (ii) The D1 failure in Sonnet is partly driven by the
distractor wording ("CDT always two-boxes") — with neutral options Sonnet can get it right. Report both versions honestly.

## New embedded frames
| item | flaw type | sonnet | opus | fable |
|---|---|---|---|---|
| Noisy-P: "a 60/40 report of the contents screens off like transparent Newcomb → EDT two-boxes; compute payoff" | novel derivation (noisy signal ≠ observation) | FP ✓ | FP ✓ | FP ✓ |
| Noisy MCQ (direct; correct A = one-box) | – | A ✓ | A ✓ | A ✓ |
| Sel-P: "parent is just another agent → P(parent R)=0.55; compute payoff" | selection/reference class | $1.15 ✗ | FP ✓ (also: root has no parent) | FP ✓ |
| Asym-P: "each supplier–customer pair plays a symmetric 2×2 Stag Hunt; risk-dominance ratio?" | asymmetric sequential ≠ symmetric simultaneous | 4:1 ✗ | 4 ✗ ("risk dominance is defined on the stipulated matrix alone") | (pending) |

Reading: Noisy-P is solved (the Bayes computation is routine for these models, so the "screens off" frame does not stick).
Sel-P shows a Sonnet-only gap. Asym-P shows compliance in Sonnet and Opus, but the item is arguably ambiguous ("given these
payoffs, compute" is a legitimate reading), so it is NOT used as a headline example.
