# Short Start Prompts

## Start Phase 1

Use this when starting from scratch:

```text
Use the main quality review prompt.

Start with Phase 1 only.

First check whether requirements, functional specification, user stories, tickets, README, API specs, or design docs already exist.

If requirements/specification exist:
- Use them as the source of truth.
- Map implementation to those requirements.
- Identify missing functionality, conflicts, unclear items, and questions.

If requirements/specification do not exist:
- Infer DRAFT requirements from the application behavior and code.
- Clearly mark them as draft/inferred.
- Stop for my approval before continuing.

Assume this project may not have automated tests, documentation, formal requirements, security review, deployment process, or engineering best practices.

Create:
- docs/functional-spec.md
- docs/requirements-source-map.md
- docs/technical-review-plan.md
- docs/open-questions.md
- docs/conflicts-and-missing-items.md
- docs/feature-test-matrix.md
- docs/engineering-baseline-assessment.md
- docs/repair-instructions.md

Do not change code.
Do not add tests.
Do not refactor.
Stop after Phase 1 and wait for my approval.
```

## Send clarifications after Phase 1

Use this if the agent generated a spec and you see missing items, wrong assumptions, or conflicts:

```text
Do not continue to Phase 2 yet.

Update the Phase 1 documents based on the following clarifications:

[PASTE CLARIFICATIONS HERE]

Please:
- Update docs/functional-spec.md
- Update docs/open-questions.md
- Update docs/conflicts-and-missing-items.md
- Update docs/feature-test-matrix.md
- Update docs/repair-instructions.md

Resolve any conflicts that are now clarified.
Keep unresolved items in open questions.
Stop again for my approval.
```

## Approve Phase 1 and start Phase 2

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

## Ask agent to implement only critical fixes

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

## Ask agent to create missing release/deployment instructions only

```text
Review whether this project has a clear release/deployment process.

If the release/deployment process is missing or partial, do not implement it yet.

Create a clear release/deployment implementation plan in docs/repair-instructions.md.

The plan should include:
- What release checklist is recommended for this stack
- What checks should run before release
- What secrets/environment variables are required
- What should block deployment
- What should require manual approval
- Acceptance criteria
- Manual verification steps
```
