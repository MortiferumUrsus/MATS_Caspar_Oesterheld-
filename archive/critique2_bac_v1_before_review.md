# Critique of Argument 2: "Blind Anthropic Cooperation: an intuitive explainer"

**The single issue.** The explainer's central claim — that, in expectation, the BAC game "becomes structurally isomorphic to
the many-player continuous-payoff Stag Hunt" — is false under the explainer's own payoffs. The proof charges a BAC-follower the
full $1 as if the cost of BAC were unconditional, but BAC is by definition a *conditional* policy: you send $3 only to children
who themselves follow BAC, and keep $1/N for every child who does not. Once the cost is booked correctly, BAC weakly dominates
"take the $1" for every value of p, so there is no risk, no coordination problem and no Stag Hunt. Since the isomorphism is what
the whole explainer builds toward ("Insofar as we think it's rational to play Stag …, it seems we should also think it's rational
to play BAC"), and what motivates the long preamble on salience, risk-dominance, the 100-hunter version and multiple stags, the
argument as presented does not go through.

**The accounting.** Let a fraction p of players follow BAC, uniformly among parents and among children (the explainer's own
assumption), and let parentless players be negligible.

- *Take the $1.* You keep $1 from your children. A BAC-following parent observes that you do not follow BAC and keeps its
  $1/N; a Take parent sends nothing anyway. Payoff: **1**.
- *Follow BAC.* Among your N children, about pN follow BAC and receive $3 each (you forgo $1/N for each of them, total $p); the
  other (1−p)N do not, and you keep $1/N for each of them, total $(1−p). With probability p your parent follows BAC, sees you
  follow BAC, and sends you $3. Payoff: **3p + (1 − p) = 1 + 2p**.

So BAC − Take = 2p ≥ 0, with equality only at p = 0. Following BAC never costs anything relative to Take when nobody else
follows it, and strictly gains whenever anyone does. The explainer's "$3p versus $1" is obtained only by assuming that a
BAC-follower rewards *all* of its children (so that p = 1 among children) while its parent follows BAC with probability p < 1 —
two incompatible values of p in one calculation. With a single consistent p, the threshold p > 1/3 disappears, "Take" is not a
safe option but a weakly dominated one, and the all-Take profile is at best a non-strict equilibrium that any player abandons at
zero cost. (The same holds for general numbers: with per-child forgone amount c and reward b > c, BAC − Take = (b − c)·p ≥ 0.)

**Why this is not a nitpick.** The defining feature of a Stag Hunt — the feature the explainer spends its first two sections
explaining — is that the cooperative action is *worse* than the safe action when others do not cooperate. That feature is exactly
what a conditional-reward policy removes: conditionality is what makes "reward your children no matter what" (which the explainer
rightly rejects) differ from BAC, and it is also what makes BAC costless to try. Hence every conclusion the explainer imports from
Stag Hunt — that BAC is risky, that its adoption turns on salience or on "how seriously other players are considering" it, that
the 100-player version should make us nervous, that risk-dominance matters — is simply inapplicable to the model as specified.
In the toy model the correct verdict is not "it's a Stag Hunt, so it is rational only if you are confident enough in others"
but "it is a no-brainer".

**What the error hides.** A Stag-Hunt structure can be restored only by adding an *unconditional* cost k of being a BAC-follower:
then BAC pays 3p + (1−p) − k and Take pays 1, and BAC is worth it only if p > k/2. But the explainer posits no such cost, and
identifying it is where the real analysis of BAC would have to begin. In the intended application the candidates are obvious and
severe: the cost of determining which children "follow BAC" — a predicate defined recursively over the child's own children, whom,
by the explainer's own visibility assumption, the parent cannot see (the footnote that waves this away "for simplicity" waves away
the mechanism); the cost of counterfactually testing a child whose children all happen to Take, and who therefore behaves exactly
like a Take player; and the cost of being *legibly* a BAC-follower to a parent one cannot see. None of this is analysed, because
the Stag-Hunt framing locates the difficulty in the wrong place — in the reward, which is cheap and conditional, rather than in
verification and legibility, which are expensive and unconditional. The "nice insight" therefore transfers nothing: it is not
merely unproven but points away from the actual question, and the sentence "insofar as it is rational to play Stag, it is rational
to play BAC" is a non sequitur in both directions — BAC-as-modelled is not a Stag Hunt, and BAC-in-the-world is not the model.

**Anticipated reply.** "Fine, correct the numbers; the conclusion that one should play BAC only gets stronger." Inside the toy
model, yes — which is precisely the problem: a model in which the cooperative policy is weakly dominant explains nothing about
why blind cooperation among simulators would be hard, fragile or worth an elaborate anthropic argument. The explainer's own
motivation ("Do you still choose S in the 100-hunter case?", "H may have a privileged default status") presupposes a risk that
its formal model does not contain. Either the model is right and the Stag-Hunt discussion is idle, or the discussion is right and
the model is missing the cost that would make it relevant. The explainer cannot have both, and as written it asserts both.

**Conclusion.** The isomorphism claim rests on charging a conditional cost unconditionally. Corrected, the toy game is
dominance-solvable in favour of BAC, so nothing about Stag Hunts — risk, salience, equilibrium selection among stags — carries
over to it, and the real obstacles to BAC (verification of a recursively defined policy, legibility to an unseen parent) are left
unmodelled. The explainer's argument for the rationality of BAC therefore fails as stated.
