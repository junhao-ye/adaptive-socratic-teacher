# Sources And Decisions

## Source Inventory

| Source | Trust | Contribution | Usage |
| --- | --- | --- | --- |
| `outputs/ai-teacher-skill` | local generated package | Production package shape, interface, eval/report habit, broad AI teacher workflow. | Adopted structure and validation discipline. |
| `outputs/socratic-ai-teacher-skill` | local generated package | Socratic diagnosis, hint ladder, examples, maintenance docs. | Adopted dialogue behavior and examples. |
| `C:\Users\mai_k\Downloads\Mr_Ranedeer.txt` | user-provided prompt | Original tutor configuration, commands, curriculum/test behaviors. | Adapted behavior; did not preserve brand, external links, or hidden execution claims. |
| `C:\Users\mai_k\.codex\skills\skill-writer\SKILL.md` | local skill | Authoring workflow and output expectations. | Used for synthesis, authoring, and validation. |

## Synthesis Decisions

| Decision | Status | Reason |
| --- | --- | --- |
| Use `adaptive-socratic-teacher` as the final name | adopted | Names the integrated behavior and matches the directory. |
| Keep `reference-backed-expert` layout | adopted | Most runs need compact routing; deeper rules are branch-specific. |
| Add `agents/interface.yaml` and `manifest.json` | adopted | Carries over production package readiness from the first version. |
| Add `SPEC.md` and `SOURCES.md` | adopted | Carries over maintainability from the second version. |
| Add `/hint` | adopted | Makes Socratic support explicit and prevents answer-dumping. |
| Keep `/example` | adopted | Preserves the first version's configuration/sample affordance. |
| Omit scripts | adopted | No deterministic automation is required yet. |

## Description Optimization

Should trigger:
- "Be my Socratic AI teacher for calculus."
- "Teach me photosynthesis with a plan and questions."
- "Help me with this homework by giving hints, not the answer."
- "/plan quantum mechanics for an undergraduate learner."
- "/test my understanding of supply and demand."

Should not trigger:
- "Give me a one-sentence definition of photosynthesis."
- "Write my homework answer for submission."
- "Summarize this article."
- "Create marketing copy for an online course."
- "Give medical advice for this symptom."

Final description combines broad AI teacher triggers with Socratic-specific terms like guided questions, hint ladders, homework helper that teaches, and mastery tester.

## Precision Pass

| Item | Decision |
| --- | --- |
| Behavior changed | Combined full tutor workflow with Socratic answer diagnosis and hint-first support. |
| Existing rule replaced | First version's generic teach loop was narrowed with answer-state classification. |
| Content moved out of runtime | Source provenance and design decisions moved to `SOURCES.md`; maintenance contract moved to `SPEC.md`. |
| New artifacts justified | References support branch-specific dialogue, curriculum, learner profile, and examples. |

## Gaps

- No real learner transcript holdout set yet.
- No deterministic numbering validator yet.
- No subject-specific references yet.
