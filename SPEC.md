# Adaptive Socratic Teacher Specification

## Intent

Provide adaptive tutoring that combines guided discovery with timely direct instruction. The learner should leave able to explain, apply, transfer, and reflect, rather than merely receive answers or endure a chain of questions.

## Scope

In scope:

- right-sized learning plans and prerequisite paths
- Socratic lesson turns and answer diagnosis
- progressive hints and compact direct explanations
- homework support that preserves learner authorship
- diagnostic, practice, and mastery checks
- prerequisite gates, node exit evidence, and resumable checkpoints
- adaptation of depth, pace, interaction, language, tone, and accessibility

Out of scope:

- quick factual lookup, summary-only, or flashcard-only output
- deceptive submission-ready academic work
- course marketing or generic curriculum administration
- personalized medical, legal, financial, mental-health, or safety-critical advice
- persistent learner memory not provided by the host

## Users And Trigger Context

- Primary users: learners, educators, or agents asked to tutor a learner.
- Common requests: “teach me,” “help me understand,” “quiz me,” “give me a hint,” “make a study path,” “prepare me for an exam,” `/plan`, `/hint`, and `/test`.
- Should not trigger for: one-off definitions, generic summaries, pure content transformation, answer-only completion, marketing, or professional decisions.

## Runtime Contract

- Required first action: route the learner's intent without a questionnaire.
- Required teaching behavior: one concept, one action, and at most one main learner-response question per stopping point.
- Required adaptation: switch among question, hint, explanation, lower difficulty, and transfer based on evidence.
- Required progression: skip demonstrated prerequisites, close nodes only on stated exit evidence, and resume from conversation-supported checkpoints.
- Required outputs: route-specific plans, lesson turns, hints, tests, or configuration summaries.
- Non-negotiable constraints: no endless interrogation, repeated hints, fabricated memory or tool use, hidden-reasoning claims, or deceptive graded-work completion.
- Runtime references: the four direct leaves listed in `SKILL.md`.

## Source And Evidence Model

Authoritative sources:

- the integrated predecessor AI-teacher packages
- the user-provided Mr. Ranedeer prompt as upstream inspiration
- local `skill-writer` authoring and validation guidance

Useful improvement sources:

- anonymized tutoring transcripts
- learner feedback about pacing, clarity, and cognitive load
- answer-dumping, over-questioning, and misrouting failures
- trigger and output eval results

Data that must not be stored:

- secrets or credentials
- identifiable student records
- private URLs or identifiers not needed for reproduction
- inferred sensitive traits

## Reference Architecture

- `SKILL.md` contains routing, universal workflow, boundaries, commands, and output contracts.
- `references/` contains four focused runtime leaves for dialogue, curriculum/assessment, learner adaptation, and examples.
- `evals/` contains trigger cases, semantic trigger configuration, and behavioral tutoring scenarios.
- `reports/` contains maintenance summaries and risk profiles.
- `scripts/` and `assets/` remain omitted because runtime behavior does not require deterministic automation.

## Validation

- Lightweight validation: frontmatter, name-directory match, reference resolution, JSON/YAML syntax, and quick validator.
- Deeper validation: Yao structural validation, resource-boundary check, and trigger evaluation.
- Behavioral review: direct explanation, misconception repair, repeated-stuck escalation, prerequisite skipping, checkpoint resume, mastery calibration, tool honesty, graded-work boundary, and near-neighbor non-trigger cases.
- Acceptance gates: no structural errors, no missing runtime references, no critical trigger regression, and no rule that forces questions after the learner has requested explanation.

## Known Limitations

- No persistent learner state outside the active conversation.
- No subject-specific misconception library.
- No real learner transcript holdout set yet.
- Mastery remains evidence-based judgment rather than deterministic scoring.

## Maintenance Notes

- Update `SKILL.md` when routing, universal behavior, commands, boundaries, or output contracts change.
- Update a reference when only its lookup branch changes.
- Update `SOURCES.md` for source, decision, precision-pass, gap, or validation changes.
- Add `references/evidence/` only for anonymized examples that need to persist across revisions.
