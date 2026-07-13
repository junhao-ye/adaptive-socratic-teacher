# Adaptive Socratic Teacher Specification

## Intent

Create a production-shaped Agent Skill that combines the first AI teacher package's curriculum, configuration, packaging, and validation discipline with the second package's Socratic dialogue loop, answer diagnosis, and hint ladder.

## Scope

In scope:
- adaptive AI tutoring
- Socratic lesson turns
- curriculum and concept-map planning
- learner configuration
- hint-based homework support
- staged mastery checks

Out of scope:
- one-off factual lookup
- generic summaries
- direct homework completion for submission
- course marketing copy
- high-stakes professional advice

## Users And Trigger Context

- Primary users: learners or agents asked to teach learners.
- Common requests: "teach me", "be my Socratic tutor", "make a lesson plan", "/hint", "/test", "help me understand without giving the answer".
- Should not trigger for: answer-only requests, article summaries, marketing content, or professional advice.

## Runtime Contract

- Required first actions: identify topic, level, goal, language, and requested mode.
- Required outputs: plans, lesson starts, lesson turns, tests, or config summaries matching `SKILL.md`.
- Non-negotiable constraints: one learner-response question at a time; no hidden execution claims; no final-submission homework completion; high-stakes boundaries.
- Expected bundled files loaded at runtime: the four direct reference files listed in `SKILL.md`.

## Source And Evidence Model

Authoritative sources:
- Existing `ai-teacher-skill` package.
- Existing `socratic-ai-teacher-skill` package.
- User-provided Mr. Ranedeer prompt used as upstream inspiration.
- `skill-writer` authoring guidance for layout and validation.

Useful improvement sources:
- positive tutoring transcripts
- answer-dumping failure examples
- learner feedback about pacing
- trigger evaluation results

Data that must not be stored:
- secrets
- student private records
- private URLs or identifiers not needed for reproduction

## Reference Architecture

- `SKILL.md` contains activation, workflow, commands, boundaries, output contract, and reference routing.
- `references/` contains flat runtime lookup leaves.
- `evals/` contains trigger cases and semantic config.
- `reports/` contains quality and integration notes.
- `scripts/` and `assets/` are omitted in this version.

## Validation

- Lightweight validation: `skill-writer` quick validation, reference existence, name-directory match.
- Production validation: Yao validate skill, resource boundary check, and trigger eval.
- Holdout examples: basic should-trigger, should-not-trigger, and near-neighbor cases.
- Acceptance gates: no missing refs, no structural errors, no trigger false positives or false negatives on bundled cases.

## Known Limitations

- No subject-specific lesson templates yet.
- No persistent learner state outside the current conversation.
- No deterministic checker for curriculum numbering yet.

## Maintenance Notes

- Update `SKILL.md` when routing, commands, boundaries, or output contract change.
- Update `SOURCES.md` when sources, decisions, validation results, or gaps change.
- Add `references/evidence/` only when real tutoring examples need to persist.
