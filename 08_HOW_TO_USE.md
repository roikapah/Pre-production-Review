# How To Use This Prompt Pack

This file explains how to use the prompt pack step by step.

## Goal

The goal is to help a non-developer or semi-technical founder use Claude Code to review an application properly.

The agent should not only check whether the app “looks like it works”.

It should check:
- Requirements
- Functionality
- Tests
- Security
- UX
- Performance
- Reliability
- Documentation
- Deployment/release readiness
- Missing engineering practices

## Step 1 — Add the prompt files

You can either:
- Copy the content of `01_MAIN_PROMPT.md` into Claude Code, or
- Place the prompt files in the repository and tell Claude Code to use them.

Recommended message:

```text
Use 01_MAIN_PROMPT.md as your main instruction.
Start with Phase 1 only.
Do not change code yet.
```

## Step 2 — Tell the agent whether requirements exist

If you know where the requirements are, tell the agent.

Example:

```text
The requirements already exist in docs/product-requirements.md and in the Trello cards.
Use them as the source of truth.
Do not infer new requirements unless something is missing or unclear.
```

If you are not sure whether requirements exist, say:

```text
First search the repository for existing requirements, user stories, README files, API specs, design docs, and tests that describe expected behavior.
If requirements exist, use them.
If not, infer draft requirements from the application and stop for my approval.
```

## Step 3 — Run Phase 1 only

Use:

```text
Start with Phase 1 only.

First check whether requirements/specification already exist.

If they exist:
- Use them as the source of truth.
- Map the implementation to them.
- Identify gaps and conflicts.

If they do not exist:
- Infer DRAFT requirements from the application behavior and code.
- Clearly mark them as draft/inferred.

Create all Phase 1 documents.
Do not change code.
Stop for my approval.
```

Expected output files:

- `docs/functional-spec.md`
- `docs/requirements-source-map.md`
- `docs/technical-review-plan.md`
- `docs/open-questions.md`
- `docs/conflicts-and-missing-items.md`
- `docs/feature-test-matrix.md`
- `docs/engineering-baseline-assessment.md`
- `docs/repair-instructions.md`

## Step 4 — Review the generated specification

You, the user/product owner, must review the generated specification.

Check:
- Is the app described correctly?
- Are the user flows correct?
- Are the roles/permissions correct?
- Are important features missing?
- Did the agent invent something that is not true?
- Are there conflicts between what you wanted and what exists?
- Are there open questions that you need to answer?

Important:
If the agent inferred requirements, they are only a draft.
They must be approved before continuing.

## Step 5 — Send corrections if needed

If something is missing, wrong, or conflicting, send this:

```text
Do not continue to Phase 2 yet.

Update the Phase 1 documents based on the following clarifications:

[WRITE YOUR CLARIFICATIONS HERE]

Resolve conflicts, update the functional specification, update open questions, update the feature-test matrix, and update repair instructions.
Stop again for approval.
```

Examples of clarifications:
- “Users should be able to delete only their own account.”
- “Admin users should see all orders, but regular users should see only their own orders.”
- “Payment is not part of the MVP.”
- “The app is only for internal use for now.”
- “We do not need multi-language support in the first version.”
- “The existing README is outdated; do not use it as the source of truth.”

## Step 6 — Approve Phase 1

Only after the specification and repair report look correct, send:

```text
The Phase 1 documents are approved.

Continue to Phase 2.

Review the implementation against the approved functional specification.

Review:
- Functionality
- Test coverage
- Security
- UX
- Performance
- Reliability
- Error handling
- Documentation
- Deployment and release readiness

Update docs/repair-instructions.md with developer-ready fix tasks.

Do not implement fixes yet unless I explicitly ask you to fix them.
```

## Step 7 — Review the repair report

The most important file is:

`docs/repair-instructions.md`

It should include:
- Plain-language explanation
- Business impact
- Risk if not fixed
- Priority
- Recommended decision
- Technical explanation
- Implementation steps
- Tests required
- Manual verification
- Definition of done

Priorities:

- MUST FIX — fix before release or real users
- SHOULD FIX — important, but may not block controlled testing
- NICE TO HAVE — improvement
- FUTURE — later roadmap item

## Step 8 — Fix only by priority

Do not ask the agent to fix everything at once.

Recommended order:

1. MUST FIX
2. SHOULD FIX
3. NICE TO HAVE
4. FUTURE

Start with:

```text
Implement only MUST FIX items from docs/repair-instructions.md.

Do not implement SHOULD FIX, NICE TO HAVE, or FUTURE items unless I explicitly approve them.

For every fix:
- Make a small focused change.
- Add or update tests.
- Run relevant tests.
- Update documentation if needed.
- Update the repair report with what was fixed and what remains.
```

## Step 9 — Repeat review after fixes

After fixes are implemented, ask:

```text
Re-run the review for the fixed items.
Confirm whether each MUST FIX item is now done.
Update docs/repair-instructions.md and docs/feature-test-matrix.md.
Tell me whether the application is ready for internal testing, public release, or still not ready.
```

## Important rule for non-technical users

Do not approve Phase 1 if you do not understand the specification.

Ask the agent to explain unclear items in simple language.

Use:

```text
Explain the open questions and risks in simple language for a non-technical owner.
For each item, tell me what decision I need to make.
```
