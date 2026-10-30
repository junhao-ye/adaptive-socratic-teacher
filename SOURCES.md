# Sources And Decisions

## Source Inventory

| Source | Trust | Contribution | Usage |
| --- | --- | --- | --- |
| `ai-teacher-skill` predecessor package | local generated package | Curriculum, configuration, packaging, and evaluation structure. | Adapted. |
| `socratic-ai-teacher-skill` predecessor package | local generated package | Answer diagnosis, question ladder, hint ladder, and teaching examples. | Adapted. |
| User-provided Mr. Ranedeer prompt | user source | Tutor commands, learner configuration, curriculum, and test concepts. | Adapted; branding, external links, and hidden-execution claims omitted. |
| `skill-writer` | local canonical skill | Update workflow, precision pass, reference architecture, description optimization, and validation. | Applied for v0.2.0. |

## v0.2.0 Synthesis Decisions

| Decision | Status | Reason |
| --- | --- | --- |
| Keep `workflow-process` class | adopted | The skill controls a repeatable tutoring loop with failure handling and boundaries. |
| Keep `reference-backed-expert` as the primary shape | adopted | Optional teaching branches belong in focused references; scripts would not improve runtime tutoring. |
| Add a compact request router | adopted | Plan, lesson, hint, test, explanation, and config require different first moves. |
| Treat Socratic questioning as a means, not a refusal policy | adopted | Prevents endless questioning and supports explicit explanation requests. |
| Replace fixed learning-style defaults with observable preferences | adopted | Avoids treating learners as fixed types and improves practical adaptation. |
| Split `/test` into diagnostic, practice, and mastery modes | adopted | A worked example is useful for practice but contaminates a diagnostic test. |
| Add session-frame tracking | adopted | Keeps continuation, hint level, and mastery evidence coherent within one conversation. |
| Add scripts or subject-specific references | deferred | No deterministic runtime task or stable subject corpus currently justifies them. |

## v0.3.0 Synthesis Decisions

| Decision | Status | Reason |
| --- | --- | --- |
| Add prerequisite gates | adopted | Demonstrated knowledge should shorten the path instead of forcing review. |
| Add node entry and exit evidence | adopted | Progress now depends on observable explanation and application, not a single correct answer. |
| Add resumable checkpoints | adopted | `/continue` can recover the current node, evidence, open gap, support used, and next move without re-intake. |
| Calibrate test difficulty by dimensions | adopted | Familiarity, reasoning steps, scaffolding, representation, and transfer distance are more reliable than difficulty labels alone. |
| Add tool-use honesty rules | adopted | Keeps verification useful without hidden-execution or fabricated-output claims. |
| Add behavioral scenario contracts | adopted | Trigger accuracy does not establish tutoring quality; multi-turn failure modes need separate judges. |
| Add fixed subject packs | deferred | Real transcript evidence is still needed before maintaining subject-specific misconception libraries. |

## Description Optimization

Should trigger:

- “Teach me calculus from the basics and ask one question at a time.”
- “我想真正理解光電效應，先判斷我的程度再教我。”
- “Help me solve this problem with hints instead of dumping the answer.”
- “Quiz me on supply and demand and adapt to my mistakes.”
- “Make a two-week study path for introductory statistics.”
- “Explain recursion directly, then check whether I can apply it.”

Should not trigger:

- “Define recursion in one sentence.”
- “Summarize this article into five bullets.”
- “Generate Anki flashcards only.”
- “Write my graded essay for submission.”
- “Create a landing page for an AI tutor.”
- “Tell me whether I should buy this stock.”

The v0.2.0 description adds realistic tutoring, exam-prep, direct-explanation, quiz, and hint language while excluding content-only and high-stakes tasks.

## Precision Pass

| Action | Result |
| --- | --- |
| Replaced | Invalid escaped frontmatter and the generic linear workflow. |
| Narrowed | One-question rule now applies at the stopping point, not as a ban on explanation. |
| Moved | Detailed dialogue, assessment, adaptation, and examples remain in routed references. |
| Deleted | Fixed “high school” and learning-style defaults; unconditional worked example before every test. |
| Added with reason | Mode routing, session frame, hint escalation, test modes, and anti-interrogation examples. |

## Coverage And Gaps

| Dimension | Status | Note |
| --- | --- | --- |
| Happy path | covered | Lesson start and adaptive partial-answer example. |
| Edge behavior | covered | Time pressure, repeated stuck state, overload, graded work, and high-stakes boundary. |
| Negative behavior | covered | Answer dumping, endless interrogation, intake questionnaire, and empty praise. |
| Repair patterns | covered | Each anti-pattern has a corrected behavior. |
| Trigger precision | covered | Multilingual positive, negative, and near-neighbor cases. |
| Behavioral contracts | covered | Twelve judge-weighted scenarios cover progression, recovery, resumption, assessment, preferences, tools, and authorship boundaries. |
| Provider-backed behavior runs | gap | Scenario contracts are defined but have not yet been executed against a model holdout set. |
| Real learner evidence | gap | Add anonymized transcript holdouts after real use. |
| Subject misconceptions | gap | Add only when a maintained, evidence-backed corpus exists. |

Further source collection stopped because current high-impact gaps require real tutoring outcomes, not more generic guidance.

## Validation Record

2026-10-31, v0.3.0:

- `skill-writer` quick validation: pass, no warnings.
- Yao structural validation: pass, no warnings.
- Resource boundary: pass at 1274 / 1300 estimated initial-load tokens.
- Trigger evaluation: 28 / 28 cases passed; precision 1.0, recall 1.0.
- Behavioral scenario integrity: 12 / 12 valid JSON cases with normalized judge weights.
- Provider-backed behavioral execution: not run; do not treat scenario definitions as outcome evidence.

2026-10-31, v0.2.0:

- `skill-writer` quick validation: pass, no warnings.
- Yao structural validation: pass, no warnings.
- Resource boundary: pass at 1296 / 1300 estimated initial-load tokens.
- Trigger evaluation: 28 / 28 cases passed; precision 1.0, recall 1.0.
