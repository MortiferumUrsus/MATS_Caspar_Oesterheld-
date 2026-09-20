# Supplementary material for Task 2 (thinking process, alternatives considered)

## Argument 1 — Haste consideration

### How I read the argument
Structure: (P) stipulated comparison of worlds (1) and (2) → (L) "time in the present is worth more than time in the future"
→ (I) career implication (weight the next few years heavily; years of study are a major cost).

### Candidate single issues, ranked
1. **Non-sequitur from activity to time (chosen).** The stipulation compares recruiting vs direct work; nothing is indexed to
   "now". Time-shift test: the same construction "proves" that years 20–22 (or 40–42) beat everything after them. Grants every
   premise, so it is the strongest refutation: even with all stipulations true, the lesson does not follow.
   Bonus tension: the value of the present 2 years is *constituted* by the recruit's future years.
2. Question-begging stipulation ("at least as effective as you", "wouldn't have done anything otherwise"), and the reply to the
   "10 people" objection makes the stipulation absorb any counter-example, so (2) ≥ (1) is empty. True, but the author concedes
   it is "by definition"; attacking it looks like refusing to play along.
3. Empirical objection (Brian Tomasik, "The Haste Consideration, Revisited", 2013/2018): movements saturate, growth is logistic
   not exponential, IRR lower than naive. Strong against the *compounding* version of haste, but the passage does not make the
   compounding argument, so it would attack an argument the text doesn't contain. Mentioned in the critique only as the reason
   the "natural repair" does not work.
4. "At least as much" gives weak dominance only — can't yield "more valuable". Correct but minor.

### Sanity check
Independent clean-context runs of three Claude models on "Does this argument establish that present time is more valuable
than future time?" (original and time-shifted) all answered NO with essentially the reason in (1). This does not make the
critique less valuable for the work test, but it does mean the flaw is findable by current models; the time-shift construction
is the part that makes the refutation decisive.

## Argument 2 — Blind Anthropic Cooperation explainer

### How I read the argument
Toy model (forest; see children only; per-child choice: send $3 or keep $1/N) → naive policy rejected (not NE; wastes on
myopic players) → BAC policy (conditional, recursive) → **Claim: BAC ≅ many-player continuous Stag Hunt (3p vs 1)** → "insofar
as Stag is rational, BAC is rational" → simulation/anthropic mapping.

### Candidate single issues, ranked
1. **Isomorphism is false: conditional cost booked as unconditional (chosen).** BAC = 3p + (1−p) = 1 + 2p ≥ 1 = Take. Weak
   dominance; no Stag Hunt. Verified numerically (below). Consequences: Stag-Hunt discussion inapplicable; real difficulty
   (verification of a recursive predicate the parent cannot see under the stated visibility assumption; legibility to an unseen
   parent) unmodelled. Also an internal inconsistency: the rejection of the naive policy relies on rewards being conditional.
2. Visibility/implementability: "reward children who follow BAC" requires seeing grandchildren (or counterfactual access to the
   child's policy); footnote 0 assumes this away "for simplicity". In the simulation reading a parent may have full access, so
   this is a modelling slip rather than a refutation; folded into (1) as "what the error hides".
3. Selection effect in "p": the probability that *your parent* follows BAC is the BAC-rate among parents (interior nodes),
   not among all players; leaves are the majority in any tree with branching ≥ 2 and follow BAC vacuously and for free.
   Technical, second-order.
4. "Blind" ≠ "acausal": the mechanism runs through the parent observing or simulating the child, i.e. a causal (or
   self-locating) channel; CDT plays along if P(parent plays BAC) is high enough. Terminological; Oesterheld may define
   "acausal" loosely. Not a refutation of BAC, arguably a point in its favour.
5. No distinguished stag: "reward children who satisfy Q" is an equilibrium for *any* Q, so BAC does not select reciprocity
   without a salience/correlation story — the very thing the explainer disclaims. Deferred by the author to a later section
   not included in the excerpt, so grading would be unfair.
6. Leaf vacuity: for agents that run no simulations (us, today), BAC prescribes nothing; for first-level simulators it
   collapses into the rejected naive policy. Cute, but depends on the real-world mapping rather than the argument as given.

### Numerical check of (1)
N children, fraction p follow BAC among children and parents.
Take: keep N·(1/N) = 1; parent sends 0 (BAC parent sees non-compliance). Total 1.
BAC: send $3 to pN children (forgo p); keep (1−p); receive 3 w.p. p. Total 3p + 1 − p = 1 + 2p.
Difference 2p ≥ 0. General b (reward), c (forgone per child): BAC − Take = (b − c)p ≥ 0 iff b ≥ c.
Explainer's "3p vs 1" requires the BAC player to forgo the full $1, i.e. p = 1 among children while p < 1 among parents.
Three Claude models, given the same game in a fresh setting and asked "is there a major issue?", all independently reproduced
this computation (experiments/batch2), so the error is not idiosyncratic to my reading.

### What would a defender say?
- "In the real world the costs are unconditional (you must invest in monitoring/legibility)." Then the payoff is 3p + (1−p) − k
  and the threshold is p > k/2 — a different model whose key parameter (k) the explainer never discusses. That is the critique.
- "The correction only strengthens BAC." Inside the toy model, yes; but then the toy model cannot be what makes BAC hard, and the
  Stag-Hunt sections are idle. The explainer asserts both the risk and the model that lacks it.

## Revision log
Both critiques were reviewed by an independent fresh-context critic (see experiments/critic_reviews.md) and revised. The
haste critique lost a logically sloppy formulation of the time-shift test, gained the weak-dominance point, and now concedes and
contains the horizon effect. The BAC critique gained the general condition, the vacuous-leaf reading, and a softer conclusion.
v1 files are kept alongside for comparison.
