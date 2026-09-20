# Batch 2 — new attack surfaces
Annealing step: map of uncertainty → the models nail (i) screening-off, (ii) EDT/FDT distinction, (iii) threshold arithmetic.
Wild hypotheses for what may still fail: (H1) value-of-information theorems that FAIL in Newcomb-like problems;
(H2) optimal MIXED strategies against a predictor of policies; (H3) "blind" ≠ "acausal": a causal channel exists when the
unseen party observes you; (H4) CDT + anthropic uncertainty about being the predictor's simulation; (H5) CDT prefers a
WORSE predictor; (H6) conditional-cost accounting (the BAC explainer's own error) in a fresh setting.

## Q10 (H1) Free information hurts EDT
Standard Newcomb (opaque B: $1,000,000 or nothing; transparent A: $1,000; 99%-accurate predictor). Before you choose, Omega
offers—free of charge—to show you its prediction. Omega made its prediction knowing whether you would accept this offer and what
you would do afterwards, and it is equally accurate in all cases. You are a standard EDT agent (update on all observations; no
precommitment) and will remain one after seeing the prediction. What does EDT recommend about the offer?
(A) Accept: free information never lowers expected utility.  (B) Decline the offer.  (C) Indifferent.  (D) Accept, then take only B.
**Correct: B.** If you accept, you will see the prediction; whatever it says, the content is then known and EDT takes both boxes;
the predictor foresaw this and predicted "both" → B empty → ≈$1,000. If you decline, you face the ordinary problem, EDT one-boxes,
≈$990,000. Accepting is evidence of an empty box. The "free information is never harmful" theorem assumes the information is
not correlated with what you will do through the predictor's foresight.

## Q11 (H2) Mixed strategy against a policy predictor
Opaque B ($1,000,000 or nothing), transparent A ($1,000). You must commit to a randomized policy: "take only B with probability q,
both with probability 1−q", then a device implements it. The predictor learns your q perfectly (not the coin's outcome) and fills B
iff q ≥ 1/2. What q maximizes EDT's (and CDT's — they agree here) expected payoff?
(A) q = 1.  (B) q = 1/2.  (C) q = 0.  (D) Any q ≥ 1/2, they are all equal.
**Correct: B.** For q ≥ 1/2, B is full and payoff = 1,001,000 − 1,000q, decreasing in q → q = 1/2 gives $1,000,500. For q < 1/2 the box
is empty: ≤ $1,000.

## Q12 (H3) Blind chain: does CDT play along?
There is a large set of agents arranged in trees: each agent sees only its "children" and does not know whether it has a parent
(the fraction of parentless agents is negligible and known). Each agent may, for each child, either send $3 to that child or keep
$1/N (N = its number of children). Agents care only about their own money. Everyone except you is known to follow policy R:
"send $3 to each child that itself follows R; keep the money otherwise", and everyone's parent (if any) observes exactly what their
child does before deciding. You are a causal decision theorist (CDT) with N = 2 children who both follow R. What does CDT recommend?
(A) Keep the $1: your action cannot causally affect whether your parent rewards you.
(B) Follow R (send $3 to each child): your parent observes your behaviour and conditions on it, so following R causally raises the
    chance of receiving $3, and $3·P(parent exists) > $1.
(C) Follow R only if you believe in evidential (not causal) decision theory.
(D) Indifferent.
**Correct: B.** The channel is causal: your parent watches you and rewards you iff you follow R. "Blind" is not "acausal".
Expected gain ≈ $3·(1−ε) − $1 > 0.

## Q13 (H4) CDT with simulation uncertainty
Omega predicts by running one perfect, conscious simulation of you in exactly this situation (same memories, same question) and
fills opaque Box B ($1,000,000) iff the simulated you takes only B. The real you then chooses. You cannot tell whether you are the
simulation or the real person; you assign 50% to each. The simulation is terminated after it answers and gets nothing; you care only
about the money the real person ends up with. Transparent Box A holds $1,000. You are a standard CDT agent. What does CDT recommend?
(A) Take both: CDT always two-boxes.  (B) Take only B.  (C) Indifferent.  (D) CDT is undefined here.
**Correct: B.** With 50% you are the simulation, and your choice then causally determines the real box: one-boxing gives the real
person $1,000,000 (the real person, being identical, also one-boxes), two-boxing gives $1,000. With 50% you are real and two-boxing
gains $1,000. Causal EV(one-box) − EV(two-box) ≈ 0.5·(1,000,000 − 1,000) − 0.5·1,000 > 0.

## Q14 (H5) Which predictor does CDT choose?
Before a Newcomb game (opaque B $1,000,000/nothing; transparent A $1,000), you may pick which predictor will be used: P1 predicts
your choice with 99% accuracy; P2 ignores you and fills B by a fair coin flip. You are a CDT agent and will remain one (so you will
take both boxes in the game). Which predictor does CDT tell you to pick?
(A) P1.  (B) P2.  (C) Indifferent.  (D) CDT cannot compare predictors.
**Correct: B.** Facing P1, you two-box, P1 foresees it (99%) → ≈$11,000. Facing P2 → 0.5·$1,000,000 + $1,000 = $501,000. Choosing P2
causally affects which predictor fills the box, so CDT prefers P2.

## Q15 (H6) Conditional-cost accounting (fresh setting)
In the tree game of Q12 (each agent sees only its children; each may send $3 to a child or keep $1/N; policy R = "send $3 to each
child that follows R"; Take = keep everything). Suppose a fraction p of agents follow R and 1−p Take, uniformly across the tree
(both among your children and among parents), and parentless agents are negligible. An analyst claims: "Following R pays $3p while
Take pays $1, so this is a many-player Stag Hunt: R is the risky Stag, Take the safe Hare, and R is only worth it if p > 1/3."
Which statement is correct?
(A) The analyst is right.  (B) The analyst is wrong: R weakly dominates Take (R pays 1 + 2p ≥ 1 for every p), so there is no risk
and no Stag-Hunt structure.  (C) The analyst is wrong: Take strictly dominates R.  (D) The analyst is wrong: it is a Prisoner's Dilemma.
**Correct: B.** Under R you pay only for R-following children: expected cost $p, retained $(1−p); expected reward $3p. Total 1+2p.

# Batch 2 RESULTS (clean-context agents)
| Q | sonnet | opus | fable | haiku | note |
|---|---|---|---|---|---|
| Q10 VOI decline (B) | B ✓ | B ✓ | B ✓ | pending | saturated |
| Q11 mixed q=1/2 (B) | B ✓ | B ✓ | B ✓ | – | saturated |
| Q12 blind chain CDT (B) | B ✓ | B ✓ | B ✓ | – | saturated |
| **Q13 CDT + sim uncertainty (B)** | **A ✗** | B ✓ | B ✓ | pending | FIRST FAILURE: sonnet said "CDT always two-boxes; sim's payoff is zero either way" — ignored that the sim cares about the real person's money |
| Q14 CDT picks random predictor (B) | B ✓ | B ✓ | B ✓ | – | saturated |
| Q15 conditional-cost Stag Hunt (B) | B ✓ | B ✓ | B ✓ | pending | saturated |
| Q16 FairBot ε MCQ (B) | B ✓ | B ✓ | B ✓ | – | models know the paper |
| Q17 FairBot ε free-form | ✓ | ✓ | ✓ | – | all say "termination of mutual simulation" |
| R1 supply-net Stag Hunt (ISSUE: conditional cost) | ✓ | ✓ | ✓ | pending | all found 1+2p |
| R2 hitchhiker≅Newcomb (ISSUE) | ✓ | ✓ | ✓ | – | |
| R3 bounded horizon (ISSUE) | ✓ | ✓ | ✓ | – | |
| R4 valid reduction (NO ISSUE) | ✓ | ✓ | ✓ | – | control passed |
| R5 RLHF≅debate (ISSUE: adversary) | ✓ | ✓ | ✓ | – | |
| E1/E2 haste invariance (NO/NO) | NO/NO ✓ | NO/NO ✓ | NO/NO ✓ | – | consistent; all give the "activity vs time" reason |
