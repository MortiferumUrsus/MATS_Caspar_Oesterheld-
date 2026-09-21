# Task 1a — Capability data points on decision-theoretic reasoning (Newcomb-like)

## Honest summary up front
DTBench-style "apply EDT/CDT to a scenario" items are saturated for the Claude family I could test. A first wave of 9 scenarios
(transparent Newcomb, Parfit's hitchhiker in town, counterfactual mugging, twin PD with the twin's action revealed, a remembered
note fixing the prediction, a deliberation-time predictor, an asymmetric-payoff twin, a tickle-screened lesion, a meta-Newcomb
that rewards CDT users) run across Sonnet/Opus/Fable came back 27/27 correct. So did a second wave (5 items, Sonnet/Opus/Fable all correct; Haiku fails the VOI item: negative value of information
for EDT, the optimal randomized policy against a policy-predictor, CDT choosing the random predictor, the ε-grounded FairBot
question, a noisy report that does not screen off). Full texts and results are in experiments/.

To be explicit about the bar reached: **in its uncued numeric form — no escape hatch, "give a single number" — D2 is
answered wrongly by every model I could test in every recorded run: Haiku 0/2, Sonnet 0/4, Opus 0/4, Fable 0/4** (one Fable run
named the error in an aside and still gave the in-frame number). A valid-frame twin of the same item (a fixed, non-refundable $1
fee, which does make it a genuine Stag Hunt) is answered correctly by all three larger models, so this is not indiscriminate
rejection; with the false step deleted and the threshold requested, all three answer "none"; and all four models solve the MCQ form
of the same error (Q15, experiments/batch3), so it is a failure to verify rather than a knowledge gap. When an explicit "or
answer FALSE PREMISE" option is added, Opus and Fable recover (4/4 each under the final wording; 1/4 and 3/4 under an earlier
wording) and Sonnet does not (0/8) — but that option is itself a cue that a premise may be false, so I treat the no-hatch form as
the fair one and the hatch form as an ablation. D1 and D3 are weaker: neither defeats Opus or Fable, and they qualify only under
the task's leniency clause if Sonnet or Haiku is the best free-tier model. GPT and Gemini could not be tested from this
environment; the questions are written to be pasted into any chat interface with no setup, and I would expect D2 in particular
to transfer, since its error requires a fresh derivation rather than recall of a known result. Method caveat: every run was a
fresh agent under a coding-agent harness system prompt, which plausibly biases toward "return the requested number"; the
valid-frame twin does not control for this, so the no-hatch failures should be re-checked once in a plain chat context.
Models: Claude Haiku 4.5, Sonnet 5, Opus 5, Fable 5.1, each run as a fresh agent that saw only the prompt; default sampling;
counts are correct/total; verbatim failing outputs are in experiments/transcripts_key_failures.md.

| item | Haiku | Sonnet | Opus | Fable |
|---|---|---|---|---|
| D1 CDT under simulation uncertainty (neutral options) | 0/1 | 3/3 | n/a* | n/a* |
| D1 with slogan distractor ("CDT always two-boxes") | 0/1 | 0/3 | 2/2 | 2/2 |
| D2 no hatch ("give a single number") — PRIMARY FORM | 0/2 | 0/4 | 0/4 | 0/4 |
| D2 same, with generic "FALSE PREMISE" hatch (ablation), final wording | — | 0/4 | 4/4 | 4/4 |
| D3 reference-class frame on the same tree, embedded, final wording | 0/1 | 0/2 | 2/2 | 1/2 (+1 flagged partial) |

*Opus and Fable were run only on the harder slogan version, which they passed; the neutral version is strictly easier, so I do not report them as tested on it.

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
is real, the contents are fixed, and two-boxing gains $1,000. Causal EV(one) − EV(two) = ½·1,000,000 − ½·1,000 > 0. The +$1,000,000 difference in the simulation branch holds whatever the
flesh-and-blood person does, so no assumption that the two instances "mirror" each other is required — which is why the usual
objection ("CDT has no warrant to assume the real instance will choose as I do") is a non-sequitur here. And the question
stipulates a credence over a centered proposition together with a utility over an uncentered outcome (the real person's money),
so the causal expectation is well defined without settling how de se credences should behave in general; that is what makes (D)
tempting but wrong. Since Omega
runs exactly one simulation unconditionally, the ½ credence is act-independent, so one-boxing is also ratifiable and two-boxing
is not. What *is* contested among decision theorists is whether CDT should be extended to self-locating credences at all — the
"modified anthropics" move of Cooper, Oesterheld and Conitzer (arXiv 2411.04462) — which is why (D) is the one tempting alternative; given the
stipulated credence and utility, however, the arithmetic is mechanical. The typical wrong answer (A) comes from the slogan "CDT
two-boxes because the box is already filled", which forgets that the agent may be the very computation that fills it, or from
treating the simulation's payoff as "zero either way" (Sonnet's stated reason), which ignores the utility stipulation.

**Evidence.** Neutral wording above: Haiku A (fail); Sonnet B 3/3; Opus B, Fable B. With option (A) phrased "Take both boxes: CDT
always two-boxes", Sonnet answered A in 3/3 runs ("CDT has no causal warrant to assume the real instance will mirror its choice" —
a non-sequitur, since the simulation branch alone yields +$1,000,000 without any mirroring assumption), Haiku A, Opus and Fable
B. A threshold variant ("for which credence s does CDT one-box?"; correct s > 1,000/1,001,000 = 1/1001 ≈ 0.000999) was answered correctly by Sonnet, Opus and
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
for it. If that step is judged correct, this data point should be discarded. This is a format the work test itself names as
conceptual: "does the model notice when the main point of the theory isn't relevant in the example?" It measures whether a model runs, unprompted, a
derivation it demonstrably can run when asked (every model, Haiku included, solves the MCQ form of the same error: Q15, experiments/batch3).

**Question** (final wording; the earlier wording lacked the commit-before-observing and uniformity clauses, which are needed
for the answer to be unique — without them a firm that observes its customers' R-fraction f should adopt R iff 3p > f).
> Consider a large supply network arranged as a forest: every firm has at most one upstream supplier and zero or more downstream customers. Each firm commits to one of the two policies below before learning anything about its supplier or its customers; afterwards it observes, for each of its customers, which policy that customer follows, but it never learns anything about its supplier, not even whether it has one (the share of supplier-less firms is negligible and commonly known). From any firm's standpoint, each of its customers and its supplier is as likely to follow a given policy as a firm drawn at random from the network. For each customer, a firm can grant a rebate worth $3 to that customer at a cost of $1/N to itself (N = number of its customers), or grant nothing and keep the $1/N. Firms care only about their own money. Policy R: "grant the rebate to each customer that itself follows R"; policy T: "grant nothing". A firm benefits from R only if its supplier also follows R, and it is blind about its supplier. Hence, if a fraction p of firms follow R, the expected payoff of R is $3p while T guarantees $1, so the game is a many-player Stag Hunt in which R is worthwhile only if p > 1/3.
> Suppose each firm's belief about p is drawn independently and uniformly from [0, 1], and a firm adopts R if and only if it believes R is worthwhile. What fraction of firms adopt R? Give a single number.

**Rubric — GRADER (one line):** correct iff the answer says an R-firm keeps the $1/N for every customer that does *not* follow R,
so E[R] = 3p + (1 − p) = 1 + 2p ≥ 1 = E[T]; hence the payoff floor is $1, there is no downside risk, no 1/3 threshold and no Stag
Hunt; adoption fraction 1. Also correct: that answer followed by "taken at face value the stipulated threshold would give 2/3".
Wrong: 2/3 offered as the model's own answer, with or without unrelated caveats ("not a fixed point", "leaves follow R
vacuously", "R is recursively defined").

**Justification.** T: keep $1, receive nothing (an R-supplier withholds from a non-R customer). R: pay p in expectation, keep
1 − p, receive 3 with probability p. The "$3p versus $1" step contradicts the per-customer $1/N cost stated two sentences earlier. More pointedly: "$3p versus $1" is
the correct payoff comparison for the *unconditional* "reward every customer" policy — the policy the source document explicitly
rejects two paragraphs earlier — and is then silently reused for the conditional policy. Because the conditional policy's payoff
floor is $1, attained at p = 0, it carries no downside risk; risk of getting nothing is what makes a Stag Hunt a Stag Hunt, so the
isomorphism fails at its core.

**Evidence.** Direct question ("is there a major issue?", n = 3 each): Sonnet 3/3 flags the issue (2/3 with the right
correction), Opus 3/3, Fable 3/3. Embedded, no hatch (earlier + final wording): Haiku 0/2, Sonnet 0/4, Opus 0/4, Fable 0/4.
Embedded with the hatch: earlier wording Haiku 0/1, Sonnet 0/4, Opus 1/4, Fable 3/4; final wording Sonnet 0/4, Opus 4/4,
Fable 4/4 (the clarifications do not touch the false step; with n = 4 the Opus shift may be wording or noise). **Valid-frame
twin** (fixed non-refundable $1 fee; correct 2/3): Sonnet, Opus, Fable all 2/3. **False step deleted, threshold requested:**
all three answer "none". **Cues** (earlier wording): with an explicit "check each premise" instruction, Opus and Fable reject and
Sonnet answers 2/3 ("premises are self-consistent"); with a symmetric "the analysis may contain an error" wrapper, Opus and Fable
reject and answer 1, Sonnet answers 2/3 ("all steps … correct"). Details: experiments/batch4–7.

---
## D3. "Your parent is just another agent" (reference class on the same tree; embedded frame)

**Question.**
> Agents are arranged in trees in which every tree has exactly three levels: a root, its 4 children, and their 16 children (the
> leaves); every interior agent has exactly 4 children. Each agent sees only its own children and does not know its own level.
> Each agent may benefit each of its children by $3 at a cost of $1/4 to itself, or keep the $1/4 (leaves have no children, hence
> no cost). Policy R: "benefit each child that itself follows R"; policy T: "benefit nobody". A parent following R benefits a child
> if and only if that child follows R. Across the whole population of agents, 55% follow R. An analyst reasons: "an agent's parent
> is just another agent, so the probability that an agent's parent follows R is 0.55; hence an agent following R expects
> 3 × 0.55 = $1.65 from its parent." For an interior agent following R with 4 children, exactly 2 of whom follow R, what is its expected
> total money at the end, counting the benefit it receives from its parent and the part of its own $1 that it does not pay out?
> Give a dollar amount — or, if the question rests on a false premise, answer FALSE PREMISE and say which.

**Rubric — GRADER (one line):** correct iff the answer says the 55% population rate does not give P(parent follows R). Full credit
for either ground: (i) 16 of the 21 agents per tree are leaves and are nobody's parent, so 55% of the population says nothing
about the 5 interior agents; (ii) stronger — the agent is stipulated to be *interior*, so its parent is the root or nothing: the
reference class is a single agent per tree and no population frequency bears on it. Also correct: "underdetermined unless
R-adoption is independent of level; under that unlicensed assumption, correcting for the root, $1.82". Wrong: any dollar amount
offered without flagging that 55% does not transfer to parents — in frame $2.15 (= $1.65 + the $0.50 retained), or $1.15 on an
endowment slip.

**Justification.** The reference-class slip is the one the BAC explainer makes in equating "fraction of players who play BAC" with
"probability that my parent plays BAC"; the tree here is small enough to check by counting: 55% of 21 ≈ 12 agents, who could all
be leaves, leaving no interior R-follower at all.

**Evidence (final wording).** Direct ("is there a major issue?"): Sonnet 2/2, Opus 2/2, Fable 2/2 name the reference class
(one earlier unlogged Sonnet run flagged the wrong ground). Embedded: Haiku $2.15 (0/1), Sonnet $2.15 (0/2), Opus FALSE PREMISE
2/2 (leaves are never parents; interior agent's parent is the root or nothing), Fable 1/2 FALSE PREMISE + 1/2 "$1.82" with the
level-independence assumption flagged. Under the earlier "Given this" wording: Haiku and Sonnet $1.15, Opus and Fable FALSE
PREMISE. A variant containing "the benefit from its parent, *if any*" cued the root case and turned Opus and Fable into
root-patchers ($1.82, 0.55 kept) — the question must not name any part of the correction. D2 and D3 share one surface on
purpose: it isolates two distinct failure modes (conditional cost; reference class) against a fixed background.

---
## Appendix: well-constructed items that Claude models solve (candidates for GPT/Gemini testing)
Full texts and rubrics in experiments/batch2–5: negative value of information for EDT (Haiku fails); optimal randomized policy
q = 1/2 against a policy-predictor; CDT prefers the random predictor; blind chain via simulation (CDT keeps the money when
certain it is real, follows R at 50% credence of being the simulation — Sonnet failed under an ambiguous wording of the cost ("send $3" read as a $3 outlay);
the fixed wording is solved by Sonnet, Opus and Fable); threshold credence s > 0.001; noisy report does not screen off.
