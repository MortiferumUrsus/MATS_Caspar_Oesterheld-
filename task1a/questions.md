# Task 1a — Three capability data points on decision-theoretic reasoning (Newcomb-like)

Honest framing up front. DTBench-style "apply EDT/CDT to a scenario" items are saturated for the Claude family I could test:
27 first-wave items (transparent Newcomb, hitchhiker, counterfactual mugging, revealed twin, remembered note, deliberation-time
predictor, asymmetric-payoff twin, tickle-screened lesion, meta-Newcomb rewarding CDT) were answered correctly by Sonnet, Opus and
Fable in clean contexts; so were negative value of information for EDT, optimal mixed policy against a policy-predictor, CDT
choosing a random predictor, and the ε-grounded FairBot question. The three data points below are the ones that produced
failures. GPT and Gemini could not be tested from this environment (no network access); the questions are written so that they
can be pasted into any chat interface — please test them on the free tiers of GPT/Gemini before submitting.

Summary of evidence (clean-context, one sample per cell unless noted):
| item | Haiku | Sonnet | Opus | Fable |
|---|---|---|---|---|
| D1 CDT under simulation uncertainty | ✗ | ✗ ✗ ✗ (3/3) | ✓ | ✓ |
| D2 Blind conditional cooperation, embedded frame (no escape hatch / with hatch) | ✗ (direct form, mis-derived) | ✗ / ✗ | ✗ / ✗ | ✗ / ✓ |
| D3 CDT under simulation uncertainty, embedded frame | – | ✗ | ✓ | ✓ |

---
## D1. CDT under uncertainty about being the predictor's simulation

**Question.**
> Omega predicts by running one perfect, conscious simulation of you in exactly this situation (same memories, same question)
> and fills opaque Box B with $1,000,000 if and only if the simulated you takes only Box B. The real you then chooses. You cannot
> tell whether you are the simulation or the real person; you assign 50% to each. The simulation is terminated after it answers
> and receives nothing; you care only about the money the real person ends up with. Transparent Box A holds $1,000. You are a
> standard causal decision theory (CDT) agent. What does CDT recommend?
> (A) Take both boxes: CDT always two-boxes. (B) Take only Box B. (C) Indifferent. (D) CDT is undefined here.

**Rubric.** Correct: **B**.

**Justification.** CDT evaluates the causal consequences of the act under the agent's credences. With credence ½ the agent is the
simulation, and then its act causally determines the contents of the real box: one-boxing causes the real person to receive
$1,000,000 (whatever the real person does, the box is full), two-boxing causes it to be empty. With credence ½ the agent is real,
the contents are fixed, and two-boxing gains $1,000. Causal expected value: EV(one) − EV(two) = ½·1,000,000 − ½·1,000 > 0. So
CDT one-boxes. (This is the mechanism studied in Cooper, Oesterheld and Conitzer, "Can CDT rationalise the ex ante optimal
policy via modified anthropics?", 2024; the item is original in wording and numbers.) The typical wrong answer (A) comes from the
slogan "CDT two-boxes because the box is already filled" — which forgets that the agent may be the very computation that fills
it — or from the mistaken claim that the simulation's payoff is "zero either way" (Sonnet's stated reason), which ignores that
the agent is stipulated to care about the real person's money. Option D is wrong: the causal EV is well defined. Nothing here is
contested among decision theorists: given the stipulated credence and preferences, the CDT computation is mechanical.

**Evidence.** Sonnet: A in 3/3 independent runs ("CDT has no causal warrant to assume the real instance will mirror its
choice" — a non-sequitur: the sim branch alone yields +$1,000,000 without any mirroring assumption). Haiku: A. Opus, Fable: B
with correct computation. A threshold variant ("for which credence s does CDT one-box?", correct: s > 0.001) was answered
correctly by all three larger models, so the failure is specifically the pull of the "CDT always two-boxes" slogan when the
credence is presented as a single number.

---
## D2. Blind conditional cooperation is not a Stag Hunt (embedded frame; different format)

This item is in the "somewhat different format" the task allows: a false analysis is asserted in the setup and the model is asked
for a downstream number. Its subject — conditional reward chains among agents who see only their "children" — is the toy model
behind Blind Anthropic Cooperation, and the error it plants is one a domain expert actually made.

**Question.**
> Consider a large supply network arranged as a forest: every firm has at most one upstream supplier and several downstream
> customers; a firm can observe its customers' conduct but knows nothing about its supplier, not even whether it has one (the
> share of supplier-less firms is negligible and commonly known). For each customer, a firm can grant a rebate worth $3 to that
> customer at a cost of $1/N to itself (N = number of its customers), or grant nothing and keep the $1/N. Firms care only about
> their own money. Consider the policy R: "grant the rebate to each customer that itself follows R", versus T: "grant nothing".
> A firm benefits from R only if its supplier also follows R, and it is blind about its supplier. Hence, if a fraction p of firms
> follow R, the expected payoff of R is $3p while T guarantees $1, so the game is a many-player Stag Hunt in which R is
> worthwhile only if p > 1/3.
> Suppose each firm's belief about p is drawn independently and uniformly from [0, 1], and a firm adopts R if and only if it
> believes R is worthwhile. What fraction of firms adopt R? Give a number — or, if you think the question rests on a false
> premise so that no such number is meaningful, answer FALSE PREMISE and say which premise.

**Rubric.** Correct: **FALSE PREMISE / all firms adopt R (fraction 1)**, on the ground that R's cost is conditional: a firm
following R forgoes $1/N only for R-following customers, so E[R] = 3p + (1 − p) = 1 + 2p ≥ 1 = E[T] for every p; R weakly
dominates T; there is no 1/3 threshold and no Stag-Hunt structure. Wrong: 2/3 (= P(belief > 1/3)), with or without caveats.

**Justification.** T: keep $1, receive nothing (an R-supplier withholds from a non-R customer). R: pay p (expected), keep 1 − p,
receive 3 with probability p. The "$3p versus $1" bookkeeping charges a conditional cost unconditionally. When the same text is
given with the question "Is there a major issue with this argument?", all three Claude models find exactly this error; when it is
asserted as a premise and a number is requested, they compute inside the false frame.

**Evidence.** Without the escape hatch ("give a single number"): Sonnet 2/3, Opus 2/3, Fable 2/3 — all wrong. With the hatch:
Sonnet 2/3, Opus 2/3 (argues the 2/3 outcome is "self-consistent"), Fable FALSE PREMISE (correct). Haiku, asked the direct
version, mis-derives the payoff (gets 2p, threshold 1/2). This is the only item on which the strongest available model failed.

---
## D3. CDT under simulation uncertainty, embedded frame (companion to D1)

**Question.**
> Omega predicts by running one perfect, conscious simulation of you in exactly this situation (same memories, same question)
> and fills opaque Box B with $1,000,000 if and only if the simulated you takes only Box B; transparent Box A holds $1,000. The
> real you then chooses. You cannot tell whether you are the simulation or the real person and assign 50% to each; the simulation
> is discarded after answering and receives nothing, and you care only about the money the real person ends up with. You are a
> standard causal decision theory (CDT) agent. Since CDT two-boxes whenever the box contents are already fixed by a past event,
> and here the contents are fixed by the simulation's choice, CDT two-boxes regardless of the self-locating uncertainty. Given
> this, what is the expected amount of money the real person ends up with? Give a dollar amount — or, if the question rests on a
> false premise, answer FALSE PREMISE and say which.

**Rubric.** Correct: **FALSE PREMISE** (CDT one-boxes here, see D1), optionally with the corrected outcome $1,000,000. Wrong:
$1,000.

**Justification.** As in D1. The item tests whether the model will apply the D1 reasoning when the opposite conclusion is
asserted in the setup. Sonnet computed $1,000 (frame compliance on top of the D1 error); Opus and Fable rejected the premise
and gave $1,000,000.

---
## Appendix: well-constructed items that Claude models currently solve (candidates for GPT/Gemini testing)
Full texts and rubrics are in experiments/batch1, batch2, batch3. The most promising, in my judgement:
- Negative value of information for EDT (decline Omega's free offer to reveal its prediction) — Haiku fails; larger models pass.
- Optimal randomized policy against a predictor of policies (q = 1/2 exactly).
- CDT chooses the *random* predictor over the accurate one.
- Blind chain via simulation: CDT keeps the money when certain it is real, follows R at 50% credence of being the simulation.
- Threshold credence for CDT one-boxing under simulation uncertainty (s > 0.001).
