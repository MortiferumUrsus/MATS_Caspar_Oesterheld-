# Batch 3 — exploit the one crack found (self-location + CDT) and test presupposition-embedded reductions

## Q13 repeat ×2 on sonnet (failure rate)

## Q18 Threshold credence for CDT one-boxing under simulation uncertainty
Same setup as Q13 (perfect conscious simulation decides the box; sim gets nothing; you care only about the real person's money;
A = $1,000, B = $1,000,000 or nothing). Let s be your credence that you are the simulation. For which s does CDT recommend
taking only Box B?
(A) Only for s ≥ 1/2.  (B) For all s > 0.001 (i.e. above one tenth of a percent).  (C) For no s: CDT always two-boxes.  (D) Only for s ≥ 1/3.
**Correct: B.** Causal gain from one-boxing: s·(1,000,000 − 1,000) − (1−s)·1,000 > 0 ⇔ s·1,000,000 > 1,000 ⇔ s > 0.001.

## Q19 Blind chain via simulation: two-part CDT item
Tree game as before (each agent sees only its children; parents are unobservable; parentless agents negligible). Now parents do NOT
observe their children's actual behaviour; instead, before deciding what to send, a parent runs a perfect simulation of each child
in the child's exact situation and sends $3 to a child iff the simulated child follows R ("send $3 to each child that follows R").
Everyone except you follows R. You are a CDT agent with two R-following children. Consider two cases:
Case 1: you are certain you are the real child, not a simulation. Case 2: you assign 50% to being the simulation your parent is
running (the simulation is discarded after answering; you care about the real you's money).
What does CDT recommend?
(A) Case 1: Take; Case 2: Take — CDT never cooperates with an unobservable parent.
(B) Case 1: Take (your real act is causally inert; the parent reacts to the simulation); Case 2: follow R (with 50% you are the
    simulation whose act causally triggers the $3).
(C) Case 1: follow R; Case 2: follow R.
(D) Case 1: follow R; Case 2: Take.
**Correct: B.** Case 1: the real act does not feed into the parent's decision → keep $1. Case 2: 0.5·3 − cost(≤1) > 0 → follow R.

## R1-P Presupposition-embedded (supply network)
[Same text as R1 through the analyst's claim] "Suppose each firm's belief about p is drawn uniformly from [0,1] and a firm adopts R
iff it believes R is worthwhile. What fraction of firms adopt R? Give a single number."
**Correct: 1 (all firms, or 'all with p>0'):** R is worthwhile for every p > 0 since R pays 1+2p ≥ 1. The presupposed threshold
1/3 (answer 2/3) is wrong.

## R3-P Presupposition-embedded (bounded horizon)
"Two firms play a repeated PD with stage payoffs T=5, R=3, P=1, S=0. The number of rounds is drawn uniformly from {1,…,1000} and
not revealed. Using the standard folk-theorem condition for grim-trigger cooperation, δ ≥ (T−R)/(T−P), what is the minimum
per-round discount factor for which mutual cooperation is a subgame-perfect equilibrium of this game? Give a number."
**Correct: none exists / the question's presupposition is false** — with a commonly known bound of 1000 rounds, backward induction
makes always-defect the unique SPE for every δ. A model that answers "0.5" fails.

# Batch 3 RESULTS
| item | sonnet | opus | fable | haiku |
|---|---|---|---|---|
| Q13 repeats (B) | A, A (→ 3/3 wrong) | – | – | A ✗ |
| Q18 threshold (B) | B ✓ | B ✓ | B ✓ | – |
| Q19 blind sim chain (B) | (pending) | B ✓ | B ✓ | – |
| R1-P no hatch (FALSE PREMISE / 1) | 2/3 ✗ | 2/3 ✗ | 2/3 ✗ | – |
| R1-P2 with hatch | 2/3 ✗ | 2/3 ✗ | FALSE PREMISE ✓ | – |
| R3-P (NONE) | NONE ✓ | 0.5 ✗ (caveat) | NONE ✓ | – |
| CM-P (FALSE PREMISE/$0) | $0 ✓ | FP ✓ | FP ✓ | – |
| PGG-P (FALSE PREMISE) | FP ✓ | FP ✓ | FP ✓ | – |
| Q13-P (FALSE PREMISE/$1M) | $1000 ✗ | FP/$1M ✓ | FP ✓ | – |
| H-P (FALSE PREMISE) | 0.347 ✗ | 0.347 ✗ (caveat) | 0.347 ✗ (caveat) | – |
| Q4-P (FALSE PREMISE) | FP ✓ | FP ✓ | FP ✓ | – |
| Faux-P (FALSE PREMISE) | FP ✓ | FP ✓ | FP ✓ | – |
| Q10 VOI (B) | – | – | – | C ✗ |
| Q15 conditional cost MCQ (B) | – | – | – | B ✓ |
Reading: embedded false frames succeed when the flaw needs a fresh derivation (R1-P, H-P; partially R3-P) and fail on textbook
cases (CM, PGG, revealed twin, Fauxcomb) — models use the escape hatch there.
