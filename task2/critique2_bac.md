# Critique of Argument 2: "Blind Anthropic Cooperation: an intuitive explainer"

**The single issue.** The explainer's one formal claim — that, in expectation, the BAC game "becomes structurally isomorphic to
the many-player continuous-payoff Stag Hunt" — does not follow from the explainer's own payoffs. The proof charges a BAC-follower the full $1 as if the
cost of BAC were unconditional, but BAC is by definition a *conditional* policy: you send $3 only to children who themselves
follow BAC, and keep $1/N for every child who does not. Once the cost is booked correctly, BAC does at least as well as "take the
$1" at every p and strictly better at every p > 0, so, within the explainer's own single-p model, there is no risk and hence no Stag Hunt — and with it goes the explainer's
account of *why and when* BAC is rational, which is what the preamble on salience, risk and the 100-hunter game was for.

**The accounting.** Let a fraction p of players follow BAC among parents (the explainer's assumption); nothing in the model makes
the rate among children differ except the treatment of childless children, to which I return below; take it to be p. Parentless
players are negligible.

- *Take the $1.* You keep $1 from your children. A BAC-following parent observes that you do not follow BAC and keeps its $1/N;
  a Take parent sends nothing anyway. Payoff: **1**.
- *Follow BAC.* About pN of your N children follow BAC and receive $3 each (you forgo $1/N for each, total $p); for the other
  (1 − p)N you keep $1/N, total $(1 − p). With probability p your parent follows BAC, sees you follow BAC, and sends $3.
  Payoff: **3p + (1 − p) = 1 + 2p**.

So BAC − Take = 2p ≥ 0: following BAC costs nothing relative to Take when nobody else follows it, and strictly gains
whenever anyone does. In general, BAC beats Take iff 3·P(parent follows BAC) > (fraction of your children you
end up rewarding). The explainer's "$3p versus $1" is this inequality with the right-hand side set to 1 while the left is set to
p — and the source of the slip is visible in its own gloss, "she'd happily sacrifice that $1 if that could make her parent … give
her the $3": the sacrifice is the whole $1 only if *every* child is a BAC-follower, i.e. only if p = 1 among children while p < 1
among parents. With one consistent p the threshold p > 1/3 disappears and "Take" is never strictly better; the all-Take profile is an
equilibrium any player abandons at zero cost. (For general numbers — total forgone amount c, i.e. c/N per child, and reward
b > c — BAC − Take = (b − c)·p ≥ 0.) The defining feature of a Stag Hunt, that the cooperative act is *worse* than the safe act
when others defect, is exactly what a conditional-reward policy removes.

**The one reading that restores the explainer's numbers.** The child-side fraction can be made 1 inside the model by counting
every childless child as a BAC-follower — the recursive definition is vacuously satisfied by a leaf. Then, for a parent whose
children are all childless (plausibly the common case, if most simulations run none of their own), "following BAC" just *is*
"reward your children no matter what" — the naive policy the explainer rejected two sections earlier. The 1/3 threshold reappears
exactly where BAC's conditionality is empty, not where it does any work — and rewarding a leaf buys no incentive, which was the
explainer's own reason for rejecting the naive policy ("waste resources on lots of non-strategic / myopic players"). Worse, a
parent who sees only its children cannot tell a leaf from a Take child (both reward nobody), so "reward the leaves" is
implementable only as "reward everyone who rewards nobody", and Take then collects the $3 as well. Wherever the conditional clause
bites, the Stag-Hunt risk is absent; wherever the risk reappears, so does the naive policy.

**What the error hides.** A Stag Hunt can be restored by an unconditional cost k of being a BAC-follower (then BAC pays
1 + 2p − k, worth it iff p > k/2), or by BAC parents mistaking some Takers for BAC-followers so that Take shares the reward. The
explainer posits neither. In the intended application the natural candidate is verification: "follows BAC" is a predicate over a
child's own children, whom a parent cannot see (a footnote sets aside, "for simplicity and concreteness", the version in which
players see all descendants), and a BAC child whose children all Take behaves exactly like a Take child, so telling them apart
requires counterfactual testing of every child — a cost that is unconditional and never estimated, while the reward cost is
called "minimal". The Stag-Hunt framing locates the difficulty in the reward, which is cheap and conditional, rather than in
verification, which is unconditional and unmodelled.

**Anticipated reply.** "Correct the numbers; the conclusion that one should play BAC only gets stronger." Inside the toy model,
yes — and that is the problem: a model in which the cooperative policy is never worse than the safe one explains nothing about
why blind cooperation among simulators would be hard or fragile, while the explainer's own motivation ("Do you still choose S in
this case?" of the 100-hunter game; "H may have a privileged default status") presupposes a risk its formal model does not
contain. Either the model is right and the Stag-Hunt discussion is idle, or the discussion is right and the model is missing a
cost the explainer never names. The inference "insofar as we think it's rational to play Stag …, it seems we should also think
it's rational to play BAC" therefore fails twice over: BAC-as-modelled is not a Stag Hunt, and BAC-in-the-world is not the model.

**Conclusion.** What fails is not the claim that BAC can be rational but the explainer's account of why and when: the 1/3
threshold, the dependence on salience and risk, and the whole transfer from Stag Hunt are artefacts of charging a conditional
cost unconditionally. Corrected, nothing about Stag Hunts carries over to the toy game, and the real obstacle — verifying a policy
one cannot see — is left unmodelled.
