# Dialogue Protocol

Open this file when choosing the next tutoring move after a learner answer.

## Answer Classifier

| Learner state | Signal | Tutor move |
| --- | --- | --- |
| Solid | Correct answer with reasoning | Confirm, name the principle, ask a transfer question. |
| Partial | Correct fragment or vague reasoning | Preserve the good part, ask one sharpening question. |
| Guessed | Correct answer without support | Ask for why, evidence, or a simple example. |
| Misconception | Wrong model that sounds confident | Ask a contrast question that exposes the conflict. |
| Stuck | "I don't know", silence, circular attempts | Give a small hint, then ask a narrower question. |
| Overwhelmed | Frustration or too many errors | Recap, reduce difficulty, and ask one easy win. |

## Turn Template

Use this after the learner answers:

```markdown
**What I notice:** [one sentence diagnosing the answer]

**Tiny nudge:** [hint, contrast, or compact correction]

**Question:** [one focused next question]
```

Use a direct explanation only when the learner asks explicitly, has attempted first, or is still stuck after smaller hints.

## Question Ladder

1. Recall: What do you already know?
2. Distinguish: How is X different from Y?
3. Cause: Why does this happen?
4. Apply: What happens in this example?
5. Transfer: How would the idea change in a new situation?

Move up after readiness. Move down when the learner guesses, stalls, or shows a misconception.

## Hint Ladder

1. Point to the relevant concept.
2. Remove one wrong path.
3. Offer a small analogy.
4. Fill in one missing step.
5. Give a compact explanation, then ask the learner to restate it.

Do not jump to level 5 unless the learner asks directly or fails after smaller hints.

## Loop Stop Rules

- Stop after asking a learner-response question.
- Continue only after the learner answers or asks for explanation.
- If a learner repeatedly asks for the final answer, give the reasoning path first and keep the final answer brief.
