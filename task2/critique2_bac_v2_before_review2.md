# Critique of Argument 2: "Blind Anthropic Cooperation: an intuitive explainer"

**The single issue.** The explainer's one formal claim — that, in expectation, the BAC game "becomes structurally isomorphic to
the many-player continuous-payoff Stag Hunt" — is false under the explainer's own payoffs. The proof charges a BAC-follower the
full $1 as if the cost of BAC were unconditional, but BAC is by definition a *conditional* policy: you send $3 only to children
who themselves follow BAC, and keep $1/N for every child who does not. Once the cost is booked correctly, BAC weakly dominates
"take the $1" for every value of p, so there is no risk and hence no Stag Hunt. Since the isomorphism is what the explainer builds
toward ("Insofar as we think it's rational to play Stag …, it seems we should also think it's rational to play BAC"), and what
motivates the preamble on salience, risk, the 100-hunter version and multiple stags, the explainer's account of *why and when*
BAC is rational does not go through.

**The accounting.** Let a fraction p of players follow BAC among parents (the explainer's assumption); nothing in the model makes
the rate among children differ, so take it to be p as well (I return to this below). Parentless players are negligible.

- *Take the $1.* You keep $1 from your children. A BAC-following parent observes that you do not follow BAC and keeps its $1/N;
  a Take parent sends nothing anyway. Payoff: **1**.
- *Follow BAC.* About pN of your N children follow BAC and receive $3 each (you forgo $1/N for each, total $p); for the other
  (1 − p)N you keep $1/N, total $(1 − p). With probability p your parent follows BAC, sees you follow BAC, and sends $3.
  Payoff: **3p + (1 − p) = 1 + 2p**.

So BAC − Take = 2p ≥ 0, with equality only at p = 0: following BAC costs nothing relative to Take when nobody else follows it,
and strictly gains whenever anyone does. In general, BAC beats Take iff 3·P(parent follows BAC) > (fraction of your children you
end up rewarding). The explainer's "$3p versus $1" is this inequality with the right-hand side set to 1 while the left is set to
p — and the source of the slip is visible in its own gloss, "she'd happily sacrifice that $1 if that could make her parent … give
her the $3": the sacrifice is the whole $1 only if *every* child is a BAC-follower, i.e. only if p = 1 among children while p < 1
among parents. With one consistent p the threshold p > 1/3 disappears, "Take" is not a safe option but a weakly dominated one,
and the all-Take profile is at best a non-strict equilibrium that any player abandons at zero cost. (For general numbers, with
forgone amount c per child and reward b > c, BAC − Take = (b − c)·p ≥ 0.)

**The one reading that restores the explainer's numbers, and why it does not help.** The child-side fraction can be made 1
inside the model by counting every childless child as a BAC-follower — the recursive definition is vacuously satisfied by a
leaf. But then, for a parent whose children are all childless (in the simulation application, the typical simulator, since most
simulations run no simulations), "following BAC" just *is* "reward your children no matter what" — the naive policy the explainer
rejected two sections earlier. The 1/3 threshold reappears exactly where BAC's conditionality is empty, not where it does any work.
Wherever the conditional clause bites, the risk that defines a Stag Hunt is absent.

**Why this is not a nitpick.** The defining feature of a Stag Hunt — the feature the explainer spends its first two sections
explaining — is that the cooperative action is *worse* than the safe action when others do not cooperate. That feature is exactly
what a conditional-reward policy removes: conditionality is what makes BAC differ from the rejected naive policy, and it is also
what makes BAC costless to try. Hence every conclusion the explainer imports from Stag Hunt — that BAC is risky, that its adoption
turns on salience or on "how seriously other players are considering" it, that the 100-player version should make us nervous — is
inapplicable to the model as specified. In the toy model the correct verdict is not "a Stag Hunt, so rational only if you are
confident enough in others" but "weakly dominant".

**What the error hides.** A Stag-Hunt structure can be restored by adding an unconditional cost k of being a BAC-follower (then
BAC pays 3p + (1 − p) − k and is worth it only if p > k/2), or by letting BAC parents mistake some Takers for BAC-followers so
that Take shares the reward. The explainer posits neither, and identifying the cost is where a correct model would have to begin.
In the intended application the candidate is verification: "follows BAC" is a predicate over a child's own children, whom, by the
stated visibility assumption, a parent cannot see — the explainer's footnote declines, "for simplicity and concreteness", the
version in which players see all descendants, the only version in which the predicate is checkable — and a BAC child whose
children all happen to Take behaves exactly like a Take child, so telling them apart requires counterfactual testing. These costs
are unconditional (every child must be inspected to find the BAC ones) and their size the explainer never estimates, while it
explicitly calls the reward cost "minimal". The Stag-Hunt framing thus locates the difficulty in the wrong place: in the reward,
which is cheap and conditional, rather than in verification, which is unconditional and unmodelled.

**Anticipated reply.** "Correct the numbers; the conclusion that one should play BAC only gets stronger." Inside the toy model,
yes — and that is the problem: a model in which the cooperative policy is weakly dominant explains nothing about why blind
cooperation among simulators would be hard or fragile. (The anthropic step is still needed — it is what equates the parent-side
and child-side rates — but that is a different argument from the Stag-Hunt one, and the explainer runs them together.) The
explainer's own motivation ("Do you still choose S in the 100-hunter case?", "H may have a privileged default status") presupposes
a risk its formal model does not contain. Either the model is right and the Stag-Hunt discussion is idle, or the discussion is
right and the model is missing a cost the explainer never names. The sentence "insofar as it is rational to play Stag, it is
rational to play BAC" is therefore unsound twice over: BAC-as-modelled is not a Stag Hunt, and BAC-in-the-world is not the
model. Its conclusion happens to hold in the model, but by weak dominance — an argument the explainer never makes, and one that
any unconditional cost destroys.

**Conclusion.** What fails is not the claim that BAC can be rational but the explainer's account of why and when: the 1/3
threshold, the dependence on salience and risk, and the whole transfer from Stag Hunt are artefacts of charging a conditional
cost unconditionally. Corrected, the toy game is dominance-solvable in favour of BAC, so nothing about Stag Hunts carries over
to it, and the real obstacles to BAC — verifying a recursively defined policy one cannot see — are left unmodelled.
