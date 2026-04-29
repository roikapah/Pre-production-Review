# Claude Code Quality Review Prompt Pack — No CI/CD Version

This prompt pack is designed for companies, founders, or non-developers who build software with Claude Code / coding agents but do not have strong software-development experience.

The goal is to force the agent to:
1. First understand and document the application.
2. Use existing requirements/specification if they already exist.
3. If requirements do not exist, infer draft requirements from the current application.
4. Clearly mark generated/inferred requirements as draft only.
5. Require user approval before continuing.
6. Produce a clear functional specification.
7. Produce a non-technical + technical repair report.
8. Stop for approval.
9. Only after approval, review implementation, tests, security, UX, performance, documentation, deployment/release process, and gaps.

## Important concept

There are two possible starting points:

### Option A — Requirements/specification already exist

If the project already has requirements, product docs, user stories, tickets, API specs, or an existing functional specification, the agent must use them as the source of truth.

The agent should:
- Locate the existing requirements.
- Summarize them.
- Map them to the current implementation.
- Identify missing functionality.
- Identify conflicts between requirements and implementation.
- Identify unclear requirements.
- Create a findings/questions list for the user to approve or clarify.

### Option B — Requirements/specification do not exist

If there are no formal requirements, the agent should infer draft requirements from the application behavior and code.

Important:
- Inferred requirements are not final.
- They must be clearly marked as “draft / inferred”.
- The user/product owner must review and approve them before Phase 2 starts.
- If something is missing, unclear, or conflicting, the agent must document it as a finding/question.

## Recommended usage

Start with:

```text
Use 01_MAIN_PROMPT.md as your main instruction.
Execute Phase 1 only.
If requirements/specification already exist, use them as the source of truth.
If they do not exist, infer draft requirements from the application.
Do not change code yet.
Stop after creating the required documentation.
```

After reviewing the generated documents, do one of the following:

### If the specification is approved

```text
The Phase 1 documents are approved.
Continue to Phase 2.
Review implementation, tests, security, UX, performance, reliability, documentation, deployment/release process, and update repair instructions.
Do not implement fixes unless explicitly instructed.
```

### If something is missing or incorrect

```text
Do not continue to Phase 2 yet.

Update the Phase 1 documents based on the following clarifications:

[PASTE USER CLARIFICATIONS HERE]

Resolve conflicts, update the functional specification, update open questions, and update the repair instructions.
Stop again for approval.
```

## Files

- `01_MAIN_PROMPT.md` — main prompt to paste into Claude Code.
- `02_PHASE_1_DISCOVERY_AND_SPEC.md` — detailed Phase 1 instructions.
- `03_PHASE_2_REVIEW_AND_QUALITY.md` — detailed Phase 2 instructions.
- `04_REPORT_FORMATS.md` — required report structures.
- `05_PRIORITY_LEVELS.md` — MUST / SHOULD / NICE TO HAVE / FUTURE definitions.
- `06_REPAIR_INSTRUCTIONS_TEMPLATE.md` — reusable template for each finding.
- `07_SHORT_START_PROMPTS.md` — short prompts for starting Phase 1 and Phase 2.
- `08_HOW_TO_USE.md` — detailed usage workflow for non-technical users.
