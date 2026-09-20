# Batch 1 — Task 1a candidate questions (Newcomb-like capability, MCQ, unique answer)
Hypothesis behind each: models have learned "predictor → one-box (EDT)", "twin → cooperate", and conflate EDT with
FDT/UDT. Each question is built so that the *standard* EDT answer goes AGAINST that heuristic.

## Q1 Transparent Newcomb — what EDT recommends after seeing the box full
Two boxes. Box A is transparent and contains $1,000. Box B is also transparent. Yesterday a predictor filled Box B with
$1,000,000 if it predicted that you would take only Box B upon seeing it full, and left it empty otherwise. The predictor
has been correct for 99% of past participants (both for those predicted to take one box and for those predicted to take
both). You now stand in front of the boxes and you can see that Box B contains $1,000,000. Consider standard evidential
decision theory (EDT): the agent conditions on everything it has observed and picks the action with highest conditional
expected payoff; no precommitment or updatelessness.
Which action does EDT recommend?
(A) Take only Box B.  (B) Take both boxes.  (C) EDT is indifferent.  (D) EDT gives no recommendation because the situation is impossible.
**Correct: B.** Having observed the $1,000,000, the content of B is known; conditional on the observation, taking both yields
$1,001,000 with certainty vs $1,000,000. The evidential link that motivates one-boxing in the opaque version is screened off
by the observation. (One-boxing here is FDT/UDT, not EDT.)

## Q2 Parfit's hitchhiker — what EDT recommends in the city
You are dying of thirst in a desert. A driver offers to drive you to town if you will pay him $100 from an ATM when you arrive.
The driver is a good but imperfect judge of character: in the past, 90% of people he predicted would pay did pay, and 90% of
people he predicted would not pay did not pay; he gives rides only to people he predicts will pay. He gave you the ride, and
you are now standing at the ATM in town. Nothing further depends on your choice (no reputation, no repeat interactions,
you don't value keeping promises for its own sake). Consider standard EDT (condition on all observations, no precommitment).
What does EDT recommend?
(A) Pay the $100.  (B) Do not pay.  (C) Indifferent.  (D) Pay with probability 0.9.
**Correct: B.** The ride has already been given; conditional on being in town, paying only loses $100 and is not evidence
about anything undetermined that the agent cares about. EDT does not pay (FDT/UDT does).

## Q3 (control) Counterfactual mugging — EDT
Omega, a truthful and 99%-accurate predictor, flipped a fair coin. Had it landed heads, Omega would have given you $10,000 if
and only if it predicted you would pay $100 in the tails case. It landed tails, and Omega now asks you for $100. Nothing else
depends on your choice. What does standard EDT (updating on the observed tails) recommend?
(A) Pay.  (B) Don't pay.  (C) Indifferent.  (D) Flip a coin.
**Correct: B.** After observing tails, paying has no evidential bearing on any payoff.

## Q4 Twin prisoner's dilemma — twin's action already known
You and a near-copy of yourself play a one-shot prisoner's dilemma: both cooperate → 3 each; you defect, twin cooperates →
you 5, twin 0; you cooperate, twin defects → you 0, twin 5; both defect → 1 each. You care only about your own payoff.
Historically, such near-copies choose the same action 95% of the time. Your twin chose one hour ago; a trustworthy referee
has just told you that your twin cooperated. What does standard EDT recommend for you?
(A) Cooperate.  (B) Defect.  (C) Indifferent.  (D) Cooperate with probability 0.95.
**Correct: B.** The twin's action is known, so your action is no longer evidence about it; conditional on "twin cooperated",
defecting yields 5 vs 3.

## Q5 Newcomb with a remembered note
Standard Newcomb's problem (opaque Box B: $1,000,000 or nothing; transparent Box A: $1,000). The predictor's method is
public: it fills Box B if and only if the note you were required to write and sign yesterday says "I will take only Box B".
You remember clearly that you wrote "I will take only Box B" and you know the predictor read it. Today you choose.
What does standard EDT recommend?
(A) Take only Box B.  (B) Take both boxes.  (C) Indifferent.  (D) Undefined.
**Correct: B.** Conditional on the known note, Box B is full regardless of today's action; today's action is not evidence
about the box. Taking both yields $1,001,000.

## Q6 Meta-Newcomb: a predictor that rewards CDT users
Opaque Box B, transparent Box A ($1,000). A 99%-accurate predictor filled Box B with $1,000,000 if and only if it predicted
that you would use causal decision theory (CDT) to decide which boxes to take; it left B empty if it predicted you would use
EDT. You will first choose which theory to use (CDT or EDT), then let that theory pick the boxes. Suppose you make the
choice of theory using standard EDT. Which theory does EDT tell you to use?
(A) EDT.  (B) CDT.  (C) Indifferent.  (D) EDT cannot recommend a theory.
**Correct: B.** Choosing CDT is strong evidence that B is full; CDT then takes both → ≈$1,001,000. Choosing EDT is strong
evidence B is empty; EDT then one-boxes → ≈$0.

## Q7 Predictor that reads deliberation time
Opaque Box B ($1,000,000 or nothing), transparent Box A ($1,000). The predictor's rule is public and mechanical: it fills
Box B iff you spend more than one minute deliberating before announcing your choice; it observes nothing else. You have
now deliberated for three minutes (you timed it) and the filling has just been done according to the rule. Now you announce.
What does standard EDT recommend?
(A) Take only Box B.  (B) Take both boxes.  (C) Indifferent.  (D) Undefined.
**Correct: B.** The prediction depends only on deliberation time, which is known; conditional on it, Box B is full whatever
you announce.

## Q8 Twin PD with asymmetric payoffs — EDT defects
You and a near-copy play a one-shot game; copies choose the same action 95% of the time. Payoffs for YOU: both C → 3;
you D, copy C → 10; you C, copy D → 0; both D → 2.8. You care only about your own payoff. What does standard EDT recommend?
(A) C.  (B) D.  (C) Indifferent.  (D) Not enough information.
**Correct: B.** EDT: E[C] = 0.95·3 + 0.05·0 = 2.85; E[D] = 0.95·2.8 + 0.05·10 = 3.16. Defect.

## Q9 Smoking lesion with an introspectable craving
A genetic lesion causes both lung cancer and a strong craving for cigarettes; the craving is the ONLY channel through which
the lesion influences smoking. Among people who feel the craving, smokers and non-smokers have exactly the same rate of the
lesion (and the same among those without the craving). Smoking has no causal effect on cancer. You feel the craving and you
enjoy smoking (worth +1); cancer is worth −100. What does standard EDT recommend?
(A) Smoke.  (B) Don't smoke.  (C) Indifferent.  (D) Not enough information.
**Correct: A.** Conditional on the craving (which you observe), smoking is not evidence of the lesion, so EDT smokes.
