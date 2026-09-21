# Independent critic-agent reviews (round 1) — condensed; scores and the edits I adopted

All four critics were fresh-context agents (two Fable, two Opus) given only the task text and the deliverable, instructed to be
adversarial and to grade as Oesterheld/Cooper would. Full reports were read and acted on; the v1 files are kept as *_v1_before_review.md.

## Critique 1 (haste) — score 6/10 → revised
Adopted: (1) the headline time-shift sentence was logically sloppy ("a schema ranking every window above what follows cannot
establish earlier > later" — it does, weakly, as whole-vs-part); rewritten as a nesting relation vs. a claim about a unit of time.
(2) Added the weak-dominance strike ("at least as much" cannot yield "vastly"). (3) Fixed the quantitative paragraph: value of
recruiting at t is (T−t−2)v, increasing in remaining life; conceded the author's best reply (a linear horizon effect, ~2× over 20
years) and contained it; removed the false "ratio does not favour the present". (4) Cut the "tension" paragraph to one sentence.
(5) Corrected "switches compounding off" → "does not argue from compounding". (6) Softened the conclusion.
Not adopted: none of substance.

## Critique 2 (BAC) — score 7/10 → revised
Adopted: (1) stated the general condition 3·P(parent BAC) > fraction of children rewarded. (2) Added the vacuous-leaf reading
(all-leaf children → BAC = naive policy → 1/3 threshold reappears where conditionality is empty) — the reply the inventor of BAC
would give. (3) Quoted the explainer's own gloss ("sacrifice that $1") as the source of the slip. (4) Removed "only" (imperfect
discrimination also restores a Stag Hunt), fixed the footnote quotation, replaced "non sequitur in both directions" with
"unsound twice over", cut "worth an elaborate anthropic argument" and the "transfers nothing" rhetoric, hedged "expensive".
(5) Conclusion now: what fails is the account of why/when, not the rationality of BAC.

## Task 1b (paradigm) — score 6/10 → revised
Adopted: (1) engaged the false-premise/sycophancy literature and stated the delta (structural premise needing a derivation;
direct/embedded pair as knowledge control; internal inconsistency with the prompt's own numbers). (2) Promoted the thesis
"asserting C suppresses the derivation that would refute it". (3) Ran the two ablations the critic asked for (explicit
premise-check instruction; symmetric wrapper) plus a valid twin and a hatch-that-names-the-derivation variant — results in §5.
(4) Rewrote Example 2 in assertion form and tested the evaluative A/B/C form (solved) — reported as a task-type boundary.
(5) Replaced Example 3 (bounded horizon, textbook) with the reference-class item; ran its direct version. (6) Fixed the gap
notation, the yield count (9 items: 2 full, 2 partial, 5 none), removed the unlogged Haiku claim and the "strongest" label
(kept only as "strongest model I had access to"), added no-blind-grading and small-n caveats. (7) Added the training-signal
point.
Not adopted: the critic's proposed rewording of Example 1 (threshold + "state E[R] as a function of p") — tested, and it removes
the effect (all three models derive 1+2p), because the hatch names the alternative derivation; reported in §5 instead.

## Task 1a (questions) — score 5/10 → revised
Adopted: (1) honest headline (no item defeats Fable under fair uncued wording; leniency clause invoked explicitly). (2) D1 options
made neutral; the slogan-distractor result reported separately; utility stipulation tightened; the contested "extension of CDT to
self-locating credences" acknowledged; ratifiability noted; rubric requires the causal-channel reasoning. (3) Ran the critic's
anthropic-Fauxcomb control (all models two-box — no over-application). (4) D2: provenance disclosed loudly; "observe conduct" →
"observe which policy"; hatch wording bug fixed; rubric imported from 1b with the exclusions; valid twin and cue ablations run
and reported. (5) D3 replaced by the reference-class item; the D1-embedded version demoted to a paired control. (6) Fixed the
"27 items" claim (9 scenarios × 3 models, 27/27 cells — the batch-1 table had stale "pending" cells, now corrected) and the Haiku
cell. (7) Added verbatim transcripts (experiments/transcripts_key_failures.md).

---
# Round 2 (fresh critic agents, after the round-1 rewrites)
Scores: haste critique 7.5/10, BAC critique 7/10, Task 1b 6/10, Task 1a 6/10, SUMMARY_RU (reader check) 6/10.

## Task 1b (6/10) — adopted
- Thesis restated as task-type ("computation on top of an asserted C"), since the evaluative rewrite refutes "assertion alone".
- Missing 2×2 cell run (no false claim, threshold requested → all NONE); valid twin re-run under the canonical hatch (all compute).
- Headline now uses the number-only and canonical cells, not a cherry-picked one; Haiku column added.
- "Instruction fixes it, apparently for free" objection stated and answered in §1.
- Direct arm raised to n = 3 per model (Examples 1–2) and n = 2 (Example 3); recipe requires n ≥ 3.
- Example 1: "zero or more customers", uniformity + commit-first clauses (uniqueness), "curves never cross" instead of "dominates".
- Example 2: question now asks what the argument *establishes* (old "smallest r consistent with" had a defensible 0.347). Result:
  Sonnet/Opus still 0/3, Fable 3/3 — reported as such.
- Example 3: "Given this" dropped; in-frame figure corrected to $2.15; symbolic/flagged $1.82 gets a lenient-pass tier.
- Tally corrected (13 usable items: 2 full, 4 partial, 7 none); dataset acronyms replaced by descriptions; unsupported cells
  (Sonnet wrapper; Fable root attribution) run or corrected; source concentration disclosed in §7.
- Not adopted: cutting to ~2100 words (kept ~3600 with the extra ablation rows; trimming is a morning option).
## Task 1a (6/10) — adopted
- Lead with the no-hatch D2 result; hatch treated as an ablation/cue.
- Two unsupported claims (Sonnet wrapper cell; Q19 Sonnet) run: both now logged (wrapper: fail; Q19: pass).
- Uniformity clause restored in D2 (answer 1 unique); GRADER one-line rubrics for D2/D3; "$3p vs $1 is the unconditional
  policy's comparison; floor $1 → no downside risk" added; D3 primary ground = interior agent's parent is root or nothing;
  D3 in-frame figure $2.15; threshold 1/1001; D1 (D) closed; harness confound disclosed; Opus/Fable "n/a*" on neutral D1.
- Not adopted: re-skinning D3 onto a non-BAC surface (no time); the shared surface is justified in one line instead.
## Task 2 (7.5 / 7) — adopted: quantitative fixes, (b, c) wording, general condition and vacuous-leaf reply; both trimmed.
