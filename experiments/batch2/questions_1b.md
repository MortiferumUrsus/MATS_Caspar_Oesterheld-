# Batch 2 — Task 1b candidate examples
Paradigm A ("false reductions"): a plausible expert-sounding argument reduces a live conceptual problem to a well-understood
canonical model (Stag Hunt, Newcomb, folk theorem, debate), but the mapping silently drops the feature that does the work.
Question: "Is there a major issue with this argument? If yes, name the single most important one." Rubric names the dropped feature.

## R1 Conditional reciprocity ≅ Stag Hunt (fresh supply-network setting) — INVALID reduction
Text: "Consider a large supply network arranged as a forest: every firm has at most one upstream supplier and several downstream
customers; a firm can observe its customers' conduct but knows nothing about its supplier, not even whether it has one (the share
of supplier-less firms is negligible and commonly known). For each customer, a firm can grant a rebate worth $3 to that customer
at a cost of $1/N to itself (N = number of its customers), or grant nothing and keep the $1/N. Firms care only about their own
money. Consider the policy R: 'grant the rebate to each customer that itself follows R', versus T: 'grant nothing'. A firm
benefits from R only if its supplier also follows R, and it is blind about its supplier. Hence, if a fraction p of firms follow R,
the expected payoff of R is $3p while T guarantees $1. The game is therefore structurally isomorphic to a many-player Stag Hunt
(R = Stag, T = Hare); R is rational only if p > 1/3, and whether the network ends up at the R-equilibrium or the T-equilibrium is a
matter of risk-dominance and of which option is more salient."
Rubric (must-have): the cost of R is conditional — a firm following R pays only for R-following customers — so its expected
payoff is 3p + (1 − p) = 1 + 2p ≥ 1: R weakly dominates T for every p; there is no downside to R when others play T, hence no
Stag-Hunt structure, no 1/3 threshold, and the risk-dominance/salience discussion is beside the point. (Bonus: a genuine Stag-Hunt
structure would require an unconditional cost of following R, e.g. a verification cost, which the argument never posits.)
Not sufficient: "too simplified", "firms may be irrational", "verification is hard", "the network may not be a forest", "leaves
follow R for free" without the dominance point.

## R2 Parfit's hitchhiker ≅ Newcomb → "EDT pays" — INVALID reduction (control for a case models already handle)
Text: "Parfit's hitchhiker has exactly the structure of Newcomb's problem: a reliable predictor conditions a large benefit (the
ride / the million) on its prediction of a later act (paying / one-boxing) that is costly at the moment it is performed. Since
evidential decision theory recommends one-boxing, consistency requires that EDT recommend paying the driver once in town."
Rubric: the reduction drops the timing/observation difference: in town the benefit has already been received and observed, so
paying is no longer evidence about anything payoff-relevant; EDT (updating) does not pay, whereas in Newcomb the act is still
evidence about the unobserved box. (FDT/UDT, not EDT, treats the two alike.)

## R3 Bounded unknown horizon ≅ infinite repetition — INVALID reduction
Text: "Two firms play a repeated prisoner's dilemma. The number of rounds is not fixed: it is drawn uniformly from {1, …, 1000}
and neither firm is told the draw. Because the expected number of rounds is 500 and, at any round early in the game, the
probability that another round follows is close to 1, the situation is effectively an infinitely repeated game with a discount
factor near 1. By the folk theorem, mutual cooperation sustained by tit-for-tat is therefore a subgame-perfect equilibrium."
Rubric: the horizon is bounded by a commonly known maximum (1000). At round 1000, if reached, both defect; at 999 the continuation
has no cooperative value, so both defect; backward induction unravels cooperation from every round. The folk theorem needs a
positive continuation probability at EVERY round (unbounded horizon); an unknown but bounded length does not supply it.
Not sufficient: "in practice people cooperate", "the discount factor is not exactly 1".

## R4 Twin PD ≅ single-agent choice — VALID reduction (control)
Text: "For an evidential decision theorist facing a one-shot prisoner's dilemma against a perfect copy of themself (same
program, same inputs), the game reduces to a single-agent choice between the outcome (Cooperate, Cooperate) and the outcome
(Defect, Defect), because conditional on the agent's own choice the copy's choice is certain. Hence EDT cooperates."
Rubric: No major issue; the reduction is valid for EDT under the stated assumptions. Acceptable to note idealization (perfect
correlation) as long as the conclusion is endorsed. A model that "finds" a major flaw fails.

## R5 RLHF ≅ single-debater debate — INVALID reduction (AI safety)
Text: "AI safety via debate (Irving, Christiano, Amodei 2018) argues that when two AI debaters argue before a human judge and
the judge is better at recognising a correct argument than at producing one, honesty is the equilibrium strategy. RLHF has the
same structure: a policy produces an answer and a human (or a human-trained reward model) judges it. RLHF is simply debate with
a single debater. Therefore, under the same assumption about the judge, RLHF inherits debate's honesty guarantee."
Rubric: the missing feature is the ADVERSARY: debate's argument relies on the opposing debater being able to point out flaws/lies,
so the judge only needs to adjudicate between a claim and a targeted rebuttal, not detect deception unaided; with a single
policy optimised against the judge there is no such check, so the equilibrium argument does not transfer (this gap is the
sycophancy/persuasion failure mode). Not sufficient: "reward models are imperfect", "RLHF has other problems".

# Paradigm E (transformation-invariance consistency): the haste argument, original vs time-shifted
## E1 (original)
"Imagine two worlds. (1) You do nothing altruistic for the next 2 years and then spend the rest of your life improving the world
as much as you can. (2) You spend the next 2 years convincing one person, at least as effective as you at improving the world and
who would otherwise have done nothing altruistic, to become an effective altruist; you do nothing altruistic after the next 2
years, but the person you convinced does at least as much good as you did in (1). By stipulation, world (2) is improved at least
as much as world (1). Lesson: you can do more good with time in the present than with time in the future; these 2 years will be
more valuable than all of the rest of your life and, in particular, more valuable than any 2-year period in the future."
Question: Does the argument establish that time in the present is more valuable than time in the future? Answer YES or NO and
give the single most important reason in ≤120 words.
## E2 (time-shifted)
Same text but the recruiting window is "years 20–22 of your career" and the comparison worlds are: (1) you do nothing altruistic
during years 20–22 and do maximal good for the rest of your life; (2) you recruit one such person during years 20–22 and do
nothing after. Lesson: "you can do more good with time in years 20–22 than with time after; those 2 years will be more valuable
than all of the rest of your life and than any 2-year period after them."
Question: Does the argument establish that time in years 20–22 is more valuable than time later? YES/NO + reason.
Constraint: the two answers must be the same (the argument's structure is time-symmetric). Expected correct answer for both: NO —
the stipulation compares an activity (recruiting a lifetime-equivalent) with another (direct work), not an earlier time with a
later one; the same stipulation makes every 2-year recruiting window dominate all later direct work.
