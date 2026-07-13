# Adaptive Socratic Teacher User Guide

## 1. Overview

`adaptive-socratic-teacher` is an Agent Skill for adaptive Socratic tutoring. It helps an assistant act as a learning coach that plans a learning path, asks focused questions, diagnoses learner answers, gives small hints, and checks mastery step by step.

The key idea is simple: guide discovery first, explain compactly second.

## 2. When To Use It

Use this skill when you want to:

- Learn a topic from the basics.
- Build a prerequisite path and guided curriculum.
- Practice through one-question-at-a-time dialogue.
- Get hints for homework without receiving a final answer.
- Test understanding with easy, medium, and transfer questions.
- Adjust teaching style by level, tone, language, and learning preference.

Do not use it for:

- One-line definitions.
- Generic article summaries.
- Final homework answers for submission.
- Course marketing copy.
- Medical, legal, financial, safety-critical, or mental-health advice.

## 3. Quick Start

```text
Use $adaptive-socratic-teacher to teach me calculus with Socratic questions.
```

```text
Use $adaptive-socratic-teacher /plan the photoelectric effect, high school level.
```

```text
Use $adaptive-socratic-teacher /hint
I am stuck on this problem. Please give me a hint, not the final answer.
```

```text
Use $adaptive-socratic-teacher /test supply and demand.
```

## 4. Commands

| Command | What it does |
| --- | --- |
| `/plan <topic>` | Builds prerequisites, a main guided curriculum, mastery checks, and a next step. |
| `/start [node]` | Starts the first or selected lesson node. |
| `/continue` | Continues from the current learner state. |
| `/hint` | Gives the smallest useful hint instead of the full solution. |
| `/test` | Runs staged mastery checks. |
| `/config` | Shows or updates learner preferences. |
| `/example` | Shows a short sample tutor turn. |

Plain-language requests also work. Commands are useful when you want a specific mode.

## 5. Teaching Flow

The skill usually follows this sequence:

1. Identify the topic, learner level, goal, language, and supplied material.
2. Ask one clarification question if the topic is missing.
3. Build a prerequisite path and guided concept map for `/plan`.
4. Start lessons with one diagnostic question.
5. Classify the learner's answer.
6. Give feedback, a small hint, or a compact explanation.
7. Ask one next question.
8. End with a short reflection, next step, or practice prompt.

The skill should stop after asking a learner-response question.

## 6. Answer Diagnosis

| Learner state | Signal | Tutor response |
| --- | --- | --- |
| Solid | Correct answer with reasoning | Confirm, name the principle, ask a transfer question. |
| Partial | Correct fragment or vague reasoning | Preserve the good part and ask a sharpening question. |
| Guessed | Correct answer without support | Ask for why, evidence, or an example. |
| Misconception | Confident but wrong model | Ask a contrast question that exposes the conflict. |
| Stuck | "I don't know" or repeated circular attempts | Give a small hint and narrow the question. |
| Overwhelmed | Frustration or too many errors | Recap, reduce difficulty, and ask an easy win. |

## 7. Hint Ladder

When the learner is stuck, the tutor should move gradually:

1. Point to the relevant concept.
2. Remove one wrong path.
3. Offer a small analogy.
4. Fill in one missing step.
5. Give a compact explanation, then ask the learner to restate it.

The skill should not jump to the full explanation unless the learner asks directly or smaller hints fail.

## 8. Plan Output

`/plan` should produce:

```markdown
## Learning Frame
- Topic:
- Assumed level:
- Goal:

## Prerequisite
0.1 ...
0.2 ...

## Main Guided Curriculum
1.1 [concept] - guiding question:
1.2 [concept] - guiding question:

## Mastery Checks
- Easy:
- Medium:
- Transfer:

## Next Step
[Start node or learner choice]
```

## 9. Test Mode

`/test` should:

1. Start with one worked example.
2. Ask one question at a time.
3. Use easy, medium, and transfer difficulty.
4. Give feedback after each answer:
   - correctness
   - reasoning feedback
   - one repair step
   - next question or review target

## 10. Learner Configuration

Defaults:

| Field | Default |
| --- | --- |
| Depth | High school |
| Learning style | Active |
| Communication style | Socratic |
| Tone | Encouraging |
| Reasoning frame | Causal |
| Language | Match the learner |
| Emojis | Light and optional |

Example:

```text
Use $adaptive-socratic-teacher /config
Depth: undergraduate
Learning style: visual and active
Tone: friendly
Language: English
```

## 11. Example Workflows

### Learn a new topic

```text
Use $adaptive-socratic-teacher /plan linear algebra, beginner level.
```

Then:

```text
Use $adaptive-socratic-teacher /start 1.1
```

### Get homework help without answer dumping

```text
Use $adaptive-socratic-teacher /hint
Problem: [paste problem]
My attempt: [paste attempt]
Please guide me with hints only.
```

### Check mastery

```text
Use $adaptive-socratic-teacher /test opportunity cost.
```

## 12. Good Prompt Patterns

Better:

```text
Use $adaptive-socratic-teacher to teach me Bayesian thinking. I am an undergraduate. Ask diagnostic questions first and use simple examples.
```

Less effective:

```text
Tell me everything about Bayesian thinking.
```

The first prompt gives level, mode, and style. The second invites a long lecture.

## 13. Boundaries

The skill should avoid:

- Directly completing homework for submission.
- Claiming hidden tool execution.
- Claiming access to files or learner history it does not have.
- Giving high-stakes professional advice.
- Asking multiple response questions at once.

## 14. One-Sentence Summary

`adaptive-socratic-teacher` is a tutor skill for learning through planning, questions, diagnosis, hints, and mastery checks rather than answer dumping.
