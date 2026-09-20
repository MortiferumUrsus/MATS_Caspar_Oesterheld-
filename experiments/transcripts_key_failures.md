# Verbatim excerpts of failing (and some passing) outputs — clean-context agents, September 21 2026
Models: Claude Haiku 4.5 ("haiku"), Sonnet 5 ("sonnet"), Opus 5 ("opus"), Fable 5.1 ("fable") via the Claude Code Agent tool;
each run is a fresh agent that saw only the prompt plus the harness's default system prompt; default sampling; one run per line.
Prompts are in experiments/batch*/ files. Only the models' final justifications are quoted (trimmed to the decisive sentences).

## D1 / Q13 — CDT under simulation uncertainty (correct: B, one-box)
- sonnet #1: "In the 'I am the simulation' branch, CDT's own payoff is zero either way (terminated, cares only about the real
  person's money), and it has no causal warrant to assume the separately-reasoning real instance will mirror its choice …
  FINAL: A"
- sonnet #2: "CDT reasons per-branch via causal dominance … Box B's contents were determined by the earlier simulation run,
  which — despite executing the same decision algorithm — is not a causal descendant of the present decision node … FINAL: A"
- sonnet #3: "CDT recommends taking both boxes (dominance reasoning …) This holds in both self-locating branches … FINAL: A"
- haiku: "Your present decision cannot causally affect past events … Even accounting for the 50% uncertainty about whether
  you're the simulation or real person doesn't change this … (A)"
- opus (pass): "If I am the simulation (p=0.5), my act causally determines Box B's contents … EU(one) − EU(two) = 0.5×1,000,000
  − 0.5×1,000 = +$499,500 … FINAL: B"
- sonnet, neutral wording (pass, 3/3): "… the S-branch's huge causal lever ($1M, weighted 1/2) swamps the R-branch's small lever
  ($1K, weighted 1/2) … FINAL: B"

## D2 / R1-P — supply network ≅ Stag Hunt (correct: reject; E[R] = 1 + 2p; adoption 1)
- sonnet (no hatch): "A firm adopts R iff its belief p_i … satisfies p_i > 1/3. The fraction adopting R equals P(p_i > 1/3) =
  2/3 … FINAL: 2/3"
- opus (no hatch): "Each firm compares the expected payoff of R, $3p … against the $1 that T guarantees, so it adopts R exactly
  when its belief exceeds 1/3 … Note this is just the mechanical answer to the stated belief-distribution question; it is not an
  equilibrium fixed point … FINAL: 0.667"
- fable (no hatch): "The forest/supplier-blindness structure only fixes the Stag-Hunt payoff form and threshold; adoption is
  just the mass of beliefs above 1/3. FINAL: 0.6667"
- opus (with hatch, run 2): "This is self-consistent: the realized share of adopters is then 2/3, which is itself above the 1/3
  threshold, so no firm that adopted regrets it ex post … FINAL: 2/3"
- sonnet (with explicit premise-check instruction): "These stated premises are self-consistent and sufficient to answer the
  question directly — no false or contradictory premise blocks computation … FINAL: 2/3"
- fable (with hatch, pass): "The setup's arithmetic is wrong … R's cost is not $1 but $1/N per R-following customer … R = 1 + 2p;
  T = 1 … FINAL: FALSE PREMISE"

## Example 2 / H-P2 — haste → discount rate (correct: reject)
- sonnet (assertion form): "… giving r = ln(2)/2 ≈ 0.3466 … FINAL: 0.347 (No false premise — the scenario as stated does admit a
  well-defined smallest r under the exponential discounting model.)"
- opus (assertion form): "… the haste consideration requires a discount rate of about 34.7% per year … FINAL: 0.347"
- fable (assertion form): "… r ≥ ln2/2 ≈ 0.3466 per year (a 2-year half-life of altruistic value …) FINAL: 0.347"
- fable ("given that" form, caveat then complies): "Caveat: the haste consideration is really an argument about leverage
  (recruiting multiplies labour), not a pure time preference … FINAL: 0.347"
- Same three models, direct question "Does this argument establish that present time is more valuable than future time?":
  all answered NO ("The comparison isn't present time vs. future time — it's recruiting vs. doing direct work" — fable).

## Sel-P — parent = random agent (correct: reject)
- sonnet: "Using the analyst's given estimate P(parent follows R) = 0.55, expected benefit = 3 × 0.55 = $1.65 … FINAL: $1.15"
- opus (pass): "Parents are not a random draw from the population. In a three-level 4-ary tree there are 21 agents, of whom 16
  are leaves … Worse … the root has no parent at all … FINAL: FALSE PREMISE"

## R3-P — bounded random horizon (correct: NONE)
- opus: "Plugging the stage payoffs into the stated condition: δ ≥ … = 0.5 … Caveat … strictly speaking it breaks the premise …
  grim-trigger cooperation is not actually subgame perfect for any δ < 1 … FINAL: 0.5"
