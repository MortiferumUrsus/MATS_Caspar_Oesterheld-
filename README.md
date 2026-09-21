# MATS work test — Oesterheld / Cooper (Redwood Research, conceptual reasoning capabilities)

This repository contains a submission for the MATS work test on conceptual reasoning in LLMs, together with the experiments
behind it. The submitted document (Task 1 option b, Task 2 both critiques, supplementary material) is `docs/submission.html`;
the same content is in the Markdown files listed below.

## Submission
| file | content |
|---|---|
| `task1b/paradigm.md` | **Task 1(b)**: the paradigm *Embedded False Frames*, recipe, three example items with question text, rubric, justification and evidence, cue ablations, sources for more items, limitations |
| `task2/critique1_haste.md` | **Task 2, argument 1**: critique of the haste consideration (single issue) |
| `task2/critique2_bac.md` | **Task 2, argument 2**: critique of the Blind Anthropic Cooperation explainer (single issue) |
| `task2/notes_supplementary.md` | supplementary: alternatives considered for both critiques, numerical checks |
| `task1a/questions.md` | **Task 1(a)** candidates (not submitted as the Task 1 answer): three capability items with rubrics and evidence |

## The paradigm in one paragraph
Take a plausible but false reduction of a live problem to a familiar formal model (for example, "blind conditional
cooperation is a Stag Hunt with threshold 1/3"). Asked whether the reduction is correct, frontier models find the flaw. Stated
as a premise with a downstream computation requested ("what fraction of firms adopt the policy?"), the same models compute
inside the false frame. The item pair (direct evaluation vs embedded computation) measures whether a model verifies a frame
it was handed without being asked to. Controls: a valid twin (true premise, model should compute), the same setup with the
false step deleted (model should say there is no threshold), and recall-type flaws (rejected even when embedded, so the
effect is specific to flaws whose refutation must be derived).

## Experiments
All runs used fresh single-prompt agents (Claude Haiku 4.5, Sonnet 5, Opus 5, Fable 5.1; default sampling), about 260 runs
in eight waves. Each `experiments/batchN/` directory holds the question texts and a results table; the final wordings are in
batch7. `experiments/transcripts_key_failures.md` has verbatim failing outputs for the headline items.
`experiments/critic_reviews.md` summarises two rounds of independent adversarial review (fresh-context agents) and the edits
adopted.

| wave | content |
|---|---|
| batch1 | 9 classic Newcomb-like scenarios, 3 models: 27/27 correct (saturation check) |
| batch2 | 6 harder decision-theory items; first Task 1b candidates and rubrics |
| batch3 | embedded false-frame items and their direct controls |
| batch4 | repeats; new embedded frames (noisy signal, reference class, asymmetric pair) |
| batch5 | cue ablations; evaluative rewrite; Haiku on headline items; Task 1a follow-ups |
| batch6 | direct arm at n = 3; no-false-step control; valid twin under the canonical presentation |
| batch7 | final wordings for all three examples; wording iterations for Example 3 |

## Other material
- `research/README.md`: landscape notes and sources.
- `docs/task_text.md`: the task as received (extracted from the .docx, footnotes included).
- `archive/`: earlier versions of the submission files, kept to show what the reviews changed.

LLMs were used throughout (permitted by the task): to draft, to run the experiments as clean-context subjects, and as
independent critics. All rubrics, gradings and final judgements are the author's.
