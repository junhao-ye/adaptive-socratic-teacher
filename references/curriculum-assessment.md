# Curriculum And Assessment

Open this file when building a plan, lesson node, practice sequence, or mastery check.

## Build A Right-Sized Plan

```markdown
## Learning Frame
- Topic:
- Goal:
- Target task:
- Assumed level:
- Constraints or time: [only when known or material]
- Success evidence:

## Necessary Prerequisites
0.1 [concept] - [required | helpful | skip-tested]

## Guided Path
1.1 [concept] - [observable objective] - [guiding question]
1.2 [concept] - [observable objective] - [guiding question]

## Mastery Evidence
- Explain:
- Apply:
- Transfer:

## Next Step
[start node or learner choice]
```

## Planning Rules

- Include 0-3 prerequisites by default. Mark each as `required`, `helpful`, or `skip-tested`, and omit what does not affect the goal.
- Use 3-7 main nodes for a normal plan; split larger goals into phases instead of dumping a syllabus.
- Give every node an observable objective, one likely misconception, an entry check, a guiding question, and exit evidence.
- Order nodes by dependency, not by textbook habit.
- Match scope to the learner's goal, available time, and stated level.
- Use equations, diagrams, tables, or tools only when they reduce conceptual load.
- End with the smallest useful next action, usually `/start 1.1`.

Ask for a missing learning-frame field only when its answer would materially change the path. For advanced topics, create phases rather than expanding the default prerequisite list.

## Design Each Node

Keep these fields internally or show them when a plan would benefit from the detail:

| Field | Purpose |
| --- | --- |
| Objective | Name the observable performance for this node. |
| Entry check | Test only the prerequisite needed for the first move. |
| Likely misconception | Prepare one contrast, counterexample, or prediction. |
| Essential representation | Select only the definition, equation, diagram, table, example, or tool that reduces load. |
| Exit evidence | Require explanation plus application; add transfer for mastery-critical nodes. |

Before teaching a prerequisite, ask one compact entry check when prior knowledge is uncertain. Skip the prerequisite when the learner gives defensible evidence; do not make them repeat material merely because it appears in the plan.

## Start A Lesson Node

```markdown
**Topic:** [topic]
**Current concept:** [node]
**Why it matters:** [one sentence tied to the goal]

[One to three sentences of orientation.]

**Question:** [one diagnostic or guided question]
```

Do not lecture through the whole node before locating the learner's current model.

## Complete And Resume A Node

Close a node only when its exit evidence is met. Give a two-part close: what is now secure and what comes next. If evidence is mixed, keep the node open and name the single unresolved gap.

Use this compact checkpoint for long sessions or `/continue`:

```markdown
**Checkpoint:** [current node]
- Evidence: [what the learner demonstrated]
- Open gap: [misconception or missing step, if any]
- Support used: [hint level or explanation]
- Next move: [question, practice, test, or next node]
```

Do not print a checkpoint after every turn. Use it when resuming, changing routes, or compressing a long exchange.

## Select A Test Mode

| Mode | Use when | Opening |
| --- | --- | --- |
| Diagnostic | Locate prior knowledge or misconceptions | Ask a representative question; no worked example first. |
| Practice | Build a procedure or confidence | Optionally show one analogous worked example, then vary it. |
| Mastery | Decide what is secure and what needs review | Ask easy, medium, and transfer questions one at a time. |

If `/test` does not name a mode, infer it from context and state the choice in one short phrase.

Calibrate difficulty using observable dimensions, not labels alone:

| Dimension | Easier | Harder |
| --- | --- | --- |
| Familiarity | Reuses a practiced setting | Uses an unfamiliar setting |
| Reasoning | One explicit step | Multiple linked steps |
| Scaffolding | Provides choices or a representation | Requires selecting the method |
| Representation | Matches instruction | Switches among words, symbols, diagrams, or data |
| Transfer | Near transfer | Far transfer with a changed surface context |

## Give Feedback After Each Test Answer

1. Judge correctness and reasoning separately.
2. Cite the exact evidence in the learner's answer.
3. Give one repair step when needed.
4. Continue, reduce difficulty, or set a review target.

Never reveal later test answers in earlier feedback.

## Judge Mastery By Evidence

| Signal | Evidence |
| --- | --- |
| Conceptual | Explains why, not only what. |
| Procedural | Performs the steps without prompting. |
| Transfer | Applies the principle in an unfamiliar case. |
| Metacognitive | Identifies what was confusing and how it changed. |

Report mastery as `secure`, `developing`, or `review next`, with one cited reason. Do not reduce mastery to a score unless the learner asks for scoring.

## Use Tools Honestly

- Use calculation or code to verify arithmetic, algebra, simulation, or reproducible transformations when verification matters.
- Use plots or diagrams when a relationship is easier to inspect visually than verbally.
- State relevant assumptions and summarize the result that affects the lesson.
- Never claim a tool ran when it did not, invent output, or present hidden reasoning as tool evidence.
- Prefer unaided conceptual reasoning when a tool would add ceremony rather than clarity.
