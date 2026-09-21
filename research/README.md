# Research notes: landscape and sources

Compiled overnight before the experiments. Network access from the working environment was limited to github.com and a
search API; arxiv, LessWrong, 80,000 Hours and Google Docs could not be opened directly, so entries below were reconstructed
from search summaries and prior knowledge. Links point to primary sources.

## 1. The mentors and their work
- **Caspar Oesterheld** (CMU, Foundations of Cooperative AI Lab; now Redwood Research, conceptual reasoning capabilities team).
  - *Multiverse-wide Cooperation via Correlated Decision Making* (2017): evidential cooperation in large worlds (ECL).
    https://longtermrisk.org/media/Multiverse-wide-Cooperation-via-Correlated-Decision-Making.pdf
  - *Robust program equilibrium* (Theory and Decision, 2019): ε-grounded FairBot, cited in the task text.
    https://link.springer.com/article/10.1007/s11238-018-9679-3
  - *Similarity-based cooperative equilibrium* (NeurIPS 2023).
  - *A typology of Newcomblike problems* (Treutlein and Oesterheld).
    https://johannestreutlein.com/wp-content/uploads/2024/10/a-typology-of-newcomblike-problems.pdf
  - *Can CDT rationalise the ex ante optimal policy via modified anthropics?* (Cooper, Oesterheld, Conitzer; arXiv 2411.04462):
    CDT plus uncertainty about being the predictor's simulation can one-box. Directly related to Blind Anthropic Cooperation.
  - *Recursive Joint Simulation in Games* (Kovařík, Oesterheld, Conitzer; arXiv 2402.08128).
  - Safe Pareto improvements (Oesterheld and Conitzer), mentioned in the task text.
- **Emery Cooper** (Redwood Research): co-author of the Newcomb-like-problems dataset and the rated-arguments dataset.
- Oesterheld's stated position: sympathetic to EDT-like theories and acausal cooperation, but the datasets separate
  "capability" questions (a unique correct answer: what EDT/CDT recommends) from "attitude" questions.

## 2. The team's existing datasets
- **Newcomb-like problems dataset**: hand-written multiple-choice questions (407 in the task text; 537 in the 2024 paper).
  *A dataset of questions on decision-theoretic reasoning in Newcomb-like problems* (arXiv 2411.10588;
  https://www.lesswrong.com/posts/d9amcRzns5pwg9Fcu/). Categories: scenario analysis, theory application (apply EDT / apply
  CDT), multi-agent (twin PD and similar), and **Fauxcomb** items that look like Newcomb problems but contain no correlation,
  as a control against heuristics. Finding: capability correlates with general model strength and with EDT-leaning attitudes;
  chain-of-thought matters. Per the task text the dataset is saturated as of mid-2026.
- **Rated conceptual arguments dataset** (arXiv 2607.27499; PDF: andrew.cmu.edu/user/coesterh/LMCA_dataset.pdf): 951
  critiques of 442 position texts, 1458 expert ratings (centrality, strength, correctness, clarity). Models reproduce expert
  ratings poorly; extended thinking does not systematically help.
- **Consistency dataset**: roughly 14k constraints of 18 types, e.g. p(A) ≥ p(A|B)·p(B).
- **Conceptual Reasoning Index** (Anthropic alignment blog with Redwood, August 2026): a weighted combination of the three.
  https://alignment.anthropic.com/2026/conceptual-reasoning-index/ ; https://conceptualreasoning.ai/

## 3. Argument 1: the haste consideration
- Original: 80,000 Hours, April 2012. https://80000hours.org/2012/04/the-haste-consideration/
- Known critique: Brian Tomasik, *The Haste Consideration, Revisited* (2013, updated 2018),
  https://reducing-suffering.org/the-haste-consideration-revisited/ : movements grow logistically, not exponentially;
  saturation; the internal rate of return is lower than the naive estimate. This is an empirical critique of the compounding
  version of the argument.
- Our critique (task2/) targets a structural gap in the argument as given: the thought experiment compares recruiting with
  direct work, not resources now with resources later.

## 4. Argument 2: Blind Anthropic Cooperation (BAC)
- Oesterheld's idea; publicly available only in his Google Doc and in the explainer supplied with the task. Relatives: ECL,
  Bostrom's simulation argument (https://simulation-argument.com/simulation.pdf), modified anthropics (arXiv 2411.04462),
  acausal trade.
- Our critique (task2/): the explainer's claim that BAC is structurally isomorphic to a many-player Stag Hunt does not follow
  from its own payoffs; the cost of BAC is conditional, so BAC = 1 + 2p ≥ 1 = Take under the explainer's single-p model.

## 5. Known LLM weaknesses in decision theory (used to generate Task 1 candidates)
- Conflating EDT with FDT/UDT (one-boxing in transparent Newcomb, paying in counterfactual mugging, Parfit's hitchhiker).
- Heuristics "predictor present → one-box", "copy present → cooperate", regardless of screening-off.
- Conflating predictor accuracy with the informativeness of a prediction (base rates).
- Level confusion: population fraction vs probability about a specific counterpart; conditional vs unconditional cost.
- LessWrong post "Kimi likes causal decision theory more after RL in twin PD": RL shifts attitude.

## 6. A previous applicant's public repository (for calibration only; nothing was copied)
- https://github.com/dani2442/MATS_application (Task 1: a summarization method with two Claude failures; Task 2: a BAC critique).
  Only the structure was inspected.
