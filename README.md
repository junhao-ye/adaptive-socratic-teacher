# Adaptive Socratic Teacher

Adaptive Socratic Teacher is an Agent Skill for guided tutoring. It combines curriculum planning, Socratic questions, hint ladders, worked examples, and staged mastery checks.

Instead of dumping an answer first, the skill frames the learner's goal, asks one focused question, diagnoses the learner's response, and gives the smallest useful hint or explanation before moving on.

## What It Is Good For

- Learning a topic from the basics.
- Building a prerequisite map and guided curriculum.
- Practicing through one-question-at-a-time tutoring.
- Getting hints for homework without receiving a final submission answer.
- Testing mastery with easy, medium, and transfer questions.
- Adapting teaching style by level, tone, language, and learning preference.

## Not For

- One-line definitions or quick fact lookup.
- Generic article summaries.
- Answer-only homework completion.
- Course marketing copy.
- Medical, legal, financial, safety-critical, or mental-health advice.

## Quick Start

```text
Use $adaptive-socratic-teacher to teach me calculus with Socratic questions.
```

```text
Use $adaptive-socratic-teacher /plan the photoelectric effect, high school level.
```

```text
Use $adaptive-socratic-teacher /hint
I am stuck on this physics problem. Please give me a hint, not the final answer.
```

## Commands

| Command | Purpose |
| --- | --- |
| `/plan <topic>` | Build a prerequisite path and main guided curriculum. |
| `/start [node]` | Start the first or selected lesson node. |
| `/continue` | Continue from the current learner state. |
| `/hint` | Give the smallest next hint, not the full solution. |
| `/test` | Run staged mastery checks. |
| `/config` | Show or update learner preferences. |
| `/example` | Show a short sample tutor turn. |

## Repository Contents

- `SKILL.md` - runtime skill entrypoint.
- `references/` - dialogue protocol, curriculum assessment, learner profile, and examples.
- `agents/interface.yaml` - interface and compatibility metadata.
- `manifest.json` - lifecycle and package metadata.
- `SPEC.md` - maintenance contract.
- `SOURCES.md` - source and decision record.
- `evals/` - trigger evaluation cases and semantic config.
- `reports/` - integration and quality notes.
- `docs/` - user guides in multiple languages.

## Documentation

- [English user guide](docs/usage.en.md)
- [繁體中文說明書](docs/usage.zh-TW.md)
- [简体中文说明书](docs/usage.zh-CN.md)
- [日本語利用ガイド](docs/usage.ja.md)

Additional README translations:

- [繁體中文 README](README.zh-TW.md)
- [简体中文 README](README.zh-CN.md)
- [日本語 README](README.ja.md)

## Validation

The generated skill package was validated with:

- `skill-writer` quick validation.
- Yao skill structural validation.
- Resource boundary check.
- Trigger evaluation with positive, negative, and near-neighbor cases.

## License

This project is licensed under the [MIT License](LICENSE).
