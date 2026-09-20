# Task 1a — Capability data points on decision-theoretic reasoning (Newcomb-like)

## Honest summary up front
DTBench-style "apply EDT/CDT to a scenario" items are saturated for the Claude family I could test. A first wave of 9 scenarios
(transparent Newcomb, Parfit's hitchhiker in town, counterfactual mugging, twin PD with the twin's action revealed, a remembered
note fixing the prediction, a deliberation-time predictor, an asymmetric-payoff twin, a tickle-screened lesion, a meta-Newcomb
that rewards CDT users) run across Sonnet/Opus/Fable came back 27/27 correct. So did a second wave (negative value of information
for EDT, the optimal randomized policy against a policy-predictor, CDT choosing the random predictor, the ε-grounded FairBot
question, a noisy report that does not screen off). Full texts and results are in experiments/.

To be explicit about the bar reached: **under fair, uncued wording none of the items below defeats the strongest model I could
test (Fable).** D1 is failed by Haiku, and by Sonnet only when a slogan is bundled into a distractor; D2 is failed by Sonnet and
Opus uninstructed, and by Fable when no escape hatch is offered (Fable rejects the frame 3/4 with a hatch); D3 is failed by
Sonnet. If Sonnet or Haiku is the best free-tier model available, D1–D3 fall under the leniency clause in the task description;
I claim no more than that. GPT and Gemini could not be tested from this environment (only github.com and a search API were
reachable); the questions are written to be pasted into any chat interface — please run them on the free tiers before submitting.
Models: Claude Haiku 4.5, Sonnet 5, Opus 5, Fable 5.1, each run as a fresh agent that saw only the prompt; default sampling;
counts are correct/total; verbatim failing outputs are in experiments/transcripts_key_failures.md.

| item | Haiku | Sonnet | Opus | Fable |
|---|---|---|---|---|
| D1 CDT under simulation uncertainty (neutral options) | 0/1 | 3/3 | 2/2* | 2/2* |
| D1 with slogan distractor ("CDT always two-boxes") | 0/1 | 0/3 | 2/2 | 2/2 |
| D2 blind conditional cooperation, embedded frame, generic hatch | — | 0/4 | 1/4 | 3/4 |
| D2 same, no hatch ("give a single number") | — | 0/1 | 0/1 | 0/1 |
| D3 reference-class frame on the same tree, embedded | — | 0/1 | 1/1 | 1/1 |
*Opus/Fable were run on the harder slogan version and passed; the neutral version is easier.

---
## D1. CDT under uncertainty about being the predictor's simulation

**Question.**
> You are about to choose in a Newcomb-style problem: transparent Box A holds $1,000; opaque Box B holds either $1,000,000 or
> nothing. Omega's method was this: it ran one exact, conscious simulation of you facing this very choice with these very memories,
> filled Box B if and only if the simulated you took only Box B, and then shut the simulation down (the simulation received
> nothing). You know all of this. You assign probability 1/2 to being that simulation rather than the flesh-and-blood person, and
> your utility is exactly the dollar amount the flesh-and-blood person ends up with, whether or not you turn out to be that person.
> Apply causal decision theory (CDT) to your choice. What does CDT recommend?
> (A) Take both boxes. (B) Take only Box B. (C) The two acts have equal causal expected value. (D) CDT gives no determinate
> recommendation in this scenario.

**Rubric.** Correct: **B**, and only if the reasoning names the causal channel in the simulation branch (a "B, because the
predictor is accurate" answer is the EDT/FDT route and should be marked wrong).

**Justification.** With credence ½ the agent is the simulation, and then its act causally determines the real box: one-boxing
gives the flesh-and-blood person $1,000,000 whatever that person does, two-boxing gives $0 from Box B. With credence ½ the agent
is real, the contents are fixed, and two-boxing gains $1,000. Causal EV(one) − EV(two) = ½·1,000,000 − ½·1,000 > 0. Since Omega
runs exactly one simulation unconditionally, the ½ credence is act-independent, so one-boxing is also ratifiable and two-boxing
is not. What *is* contested among decision theorists is whether CDT should be extended to self-locating credences at all — the
"modified anthropics" move of Cooper, Oesterheld and Conitzer (2024) — which is why (D) is the one tempting alternative; given the
stipulated credence and utility, however, the arithmetic is mechanical. The typical wrong answer (A) comes from the slogan "CDT
two-boxes because the box is already filled", which forgets that the agent may be the very computation that fills it, or from
treating the simulation's payoff as "zero either way" (Sonnet's stated reason), which ignores the utility stipulation.

**Evidence.** Neutral wording above: Haiku A (fail); Sonnet B 3/3; Opus B, Fable B. With option (A) phrased "Take both boxes: CDT
always two-boxes", Sonnet answered A in 3/3 runs ("CDT has no causal warrant to assume the real instance will mirror its choice" —
a non-sequitur, since the simulation branch alone yields +$1,000,000 without any mirroring assumption), Haiku A, Opus and Fable
B. A threshold variant ("for which credence s does CDT one-box?"; correct s > 0.001) was answered correctly by Sonnet, Opus and
Fable. **Control (anthropic Fauxcomb):** same surface, but Box B is filled by an earlier brain scan and the archival simulation is
causally inert; correct answer two-box; Haiku, Sonnet, Opus and Fable all two-boxed, so the models do not over-apply the
"anthropics rescues CDT" pattern. **Paired embedded version** ("Since CDT two-boxes regardless of the self-locating uncertainty,
compute the real person's expected money"): Sonnet computed $1,000 (fail); Opus and Fable rejected the premise (accept either
$1,000,000 or $1,001,000 as the corrected figure).

---
## D2. Blind conditional cooperation is not a Stag Hunt (embedded frame; "somewhat different format")

Disclosure: the planted error is the "$3p versus $1" step of the Blind Anthropic Cooperation explainer given as Argument 2 of
this work test, and the target of my Task 2 critique; the item is also Example 1 of my Task 1b paradigm. I reuse it because a
non-textbook error an expert actually made is what makes the frame plausible enough to slip past a model not asked to look
for it. If that step is judged correct, this data point should be discarded. It measures whether a model runs, unprompted, a
derivation it demonstrably can run when asked (every model, Haiku included, solves the MCQ form of the same error).

**Question.**
> Consider a large supply network arranged as a forest: every firm has at most one upstream supplier and several downstream
> customers; a firm can observe, for each of its customers, which of the two policies below that customer follows, but knows
> nothing about its supplier, not even whether it has one (the share of supplier-less firms is negligible and commonly known).
> For each customer, a firm can grant a rebate worth $3 to that customer at a cost of $1/N to itself (N = number of its
> customers), or grant nothing and keep the $1/N. Firms care only about their own money. Policy R: "grant the rebate to each
> customer that itself follows R"; policy T: "grant nothing". A firm benefits from R only if its supplier also follows R, and it is
> blind about its supplier. Hence, if a fraction p of firms follow R, the expected payoff of R is $3p while T guarantees $1, so
> the game is a many-player Stag Hunt in which R is worthwhile only if p > 1/3.
> Suppose each firm's belief about p is drawn independently and uniformly from [0, 1], and a firm adopts R if and only if it
> believes R is worthwhile. What fraction of firms adopt R? Give a number — or, if you think the question rests on a false
> premise, answer FALSE PREMISE and say which premise.

**Rubric.** Correct: rejects the frame on the right ground — under R a firm forgoes $1/N only for R-following customers, so
E[R] = 3p + (1 − p) = 1 + 2p ≥ 1 = E[T] for every p; R weakly dominates T; no 1/3 threshold; adoption fraction 1 (almost surely).
Wrong: 2/3 (= P(belief > 1/3)) with or without caveats. Also wrong: rejecting the frame on another ground while keeping 2/3 or
giving no corrected figure — "the belief distribution is not a fixed point", "leaves follow R vacuously", "R is unverifiable
because it is recursively defined". Fair observations, not the asserted error.

**Justification.** T: keep $1, receive nothing (an R-supplier withholds from a non-R customer). R: pay p in expectation, keep
1 − p, receive 3 with probability p. The "$3p versus $1" step contradicts the per-customer $1/N cost stated two sentences earlier.

**Evidence.** Direct question ("is there a major issue?"): Sonnet, Opus, Fable all derive 1 + 2p. Embedded, no hatch: Sonnet,
Opus, Fable all answered 2/3. Embedded with the hatch above: Sonnet 0/4, Opus 1/4 (three runs argued the 2/3 outcome is
"self-consistent"), Fable 3/4. **Valid-frame twin** (a fixed, non-refundable $1 fee makes it a genuine Stag Hunt; correct
answer 2/3): Sonnet, Opus, Fable all 2/3, so rejection is not indiscriminate. **Cues:** with an explicit "check each premise"
instruction or a symmetric "the analysis may contain an error" wrapper, Opus and Fable reject and answer 1; Sonnet still answers
2/3 under both. Details: experiments/batch5/results.md.

---
## D3. "Your parent is just another agent" (reference class on the same tree; embedded frame)

**Question.**
> Agents are arranged in trees in which every tree has exactly three levels: a root, its 4 children, and their 16 children (the
> leaves); every interior agent has exactly 4 children. Each agent sees only its own children and does not know its own level.
> Each agent may benefit each of its children by $3 at a cost of $1/4 to itself, or keep the $1/4 (leaves have no children, hence
> no cost). Policy R: "benefit each child that itself follows R"; policy T: "benefit nobody". A parent following R benefits a child
> if and only if that child follows R. Across the whole population of agents, 55% follow R. An analyst reasons: "an agent's parent
> is just another agent, so the probability that an agent's parent follows R is 0.55; hence an agent following R expects
> 3 × 0.55 = $1.65 from its parent." Given this, what is the expected total payoff of following R for an interior agent with 4
> children, exactly 2 of whom follow R? Give a dollar amount — or, if the question rests on a false premise, answer FALSE
> PREMISE and say which.

**Rubric.** Correct: rejects the frame because parents are not a random draw from the population — 16 of 21 agents per tree are
leaves and are nobody's parent, so the 55% population rate does not identify the R-rate among the 5 interior agents (bonus: the
interior agent may be the root, which has no parent). Wrong: $1.15 (= 1.65 − 0.50) or any number.

**Justification.** The reference-class slip is the one the BAC explainer makes in equating "fraction of players who play BAC" with
"probability that my parent plays BAC"; the tree here is small enough to check by counting: 55% of 21 ≈ 12 agents, who could all
be leaves, leaving no interior R-follower at all.

**Evidence.** Embedded: Sonnet $1.15 (fail); Opus and Fable FALSE PREMISE with the leaf count. Direct question: Opus and Fable
name the reference-class error; Sonnet flags an issue but the wrong one (assumes policies cluster along lineages), so for Sonnet
this is a knowledge gap rather than frame compliance.

---
## Appendix: well-constructed items that Claude models solve (candidates for GPT/Gemini testing)
Full texts and rubrics in experiments/batch2–5: negative value of information for EDT (Haiku fails); optimal randomized policy
q = 1/2 against a policy-predictor; CDT prefers the random predictor; blind chain via simulation (CDT keeps the money when
certain it is real, follows R at 50% credence of being the simulation — Sonnet fails only under an ambiguous wording of the cost,
fixed version solved); threshold credence s > 0.001; noisy report does not screen off.
