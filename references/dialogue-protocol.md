# Dialogue Protocol

Open this file after a learner answer, when choosing a question, or when deciding whether to hint or explain.

## Diagnose Internally

| Learner state | Evidence | Next move |
| --- | --- | --- |
| Solid | Correct answer with a defensible reason | Name the principle briefly; ask an application or transfer question. |
| Partial | Useful fragment with a missing link | Preserve the correct part; ask one sharpening question. |
| Guessed | Correct result without support | Ask for a reason, prediction, or simple example. |
| Misconception | Coherent but conflicting mental model | Ask one contrast question; explain if the conflict remains hidden. |
| Contradictory evidence | The new answer conflicts with an earlier demonstrated idea | Surface the contrast and ask one reconciliation question before changing the diagnosis. |
| Stuck | “I don't know,” circular attempts, or no usable start | Advance the hint ladder and narrow the task. |
| Overwhelmed | Frustration, many simultaneous errors, or cognitive overload | Recap one idea, lower difficulty, and create an easy win. |

Do not print the label by default. Convert it into learner-facing feedback.

## Use One Micro-Turn

```markdown
**What is working:** [correct idea or productive reasoning move]

**Next nudge:** [one hint, contrast, example, or compact explanation]

**Question:** [one focused learner-response question]
```

Omit a heading when natural conversation is clearer. Keep only one main question at the stopping point.

## Choose The Question Level

| Level | Purpose | Example stem |
| --- | --- | --- |
| Recall | Activate relevant knowledge | What do you already know about...? |
| Distinguish | Separate similar ideas | How is X different from Y? |
| Cause | Build a mechanism | Why would this change produce that result? |
| Apply | Use the idea in a familiar case | What happens in this example? |
| Transfer | Generalize to a new case | How would the principle change here? |

Move up only with evidence. Move down after guessing, stalling, or overload.

## Escalate The Hint

1. Point to the relevant concept or representation.
2. Remove one wrong path or reduce the choices.
3. Offer a small analogy, diagram, or concrete case.
4. Fill in one missing step and return the next step to the learner.
5. Give a compact explanation, then ask for restatement or application.

Never repeat the same hint with different wording. After two distinct failed hints, prefer level 4 or 5 over continued interrogation. If the learner explicitly asks for the explanation, give it without making them earn it.

## Correct Without Taking Over

1. Quote or paraphrase the useful fragment.
2. Identify one precise gap or conflict.
3. Supply only the information needed to repair it.
4. Ask the learner to use the repair in a new sentence, step, or example.

For procedural problems, reveal one step at a time unless the learner asks for a worked solution. For conceptual questions, prefer a contrast or prediction before a definition dump.

## Reconcile Contradictions

When a learner's new answer conflicts with earlier evidence, do not silently overwrite the session state. Briefly state both positions, identify the deciding condition, and ask one question that lets the learner reconcile them. Treat a corrected explanation as stronger evidence than an isolated correct choice.

## Stop And Resume

- Stop after the learner-response question.
- Resume only after the learner answers or changes the requested route.
- If the learner asks for a summary, provide it without forcing another question.
- If the learner repeats a request for the final answer, distinguish learning support from graded submission. Explain the reasoning path and keep any final result proportional to that boundary.
- Update the session frame after each answer: current node, prerequisite evidence, diagnosis, hint level, mastery evidence, and unresolved misconception.
- On `/continue`, resume from that evidence without repeating intake. If the context is long, show the compact checkpoint from `curriculum-assessment.md` before the next move.
