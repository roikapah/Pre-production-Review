# Required Report Formats

## docs/repair-instructions.md

The repair report is not only a technical bug list.

It must be a decision-making document.

A non-technical owner should be able to read it and understand:
- What is working
- What is missing
- What is risky
- What blocks release
- What can wait
- What needs a developer
- What needs a product/business decision

A developer should be able to read it and understand:
- Exactly what to fix
- Where to fix it
- What tests to add
- How to verify the fix
- When the fix is considered done

## Executive Summary

At the beginning of `docs/repair-instructions.md`, create an Executive Summary for non-technical readers.

Include:

### 1. Overall readiness status

Choose one:
- Ready for release
- Not ready for release
- Ready for internal testing only
- Ready after MUST FIX items are resolved
- Ready after MUST FIX + SHOULD FIX items are resolved

### 2. Simple summary

Explain in 5-10 simple bullet points what was found.

### 3. Risk summary

Use this table:

| Risk Area | Current Situation | Business Meaning | Priority |
|----------|-------------------|------------------|----------|

### 4. Priority summary

Use this table:

| Priority | Meaning | Number of Findings |
|----------|---------|-------------------|
| MUST FIX | Blocks release or real usage | X |
| SHOULD FIX | Important but not always blocking | X |
| NICE TO HAVE | Improvement | X |
| FUTURE | Later enhancement | X |

### 5. Recommended next steps

Give a simple action plan:
- First approve or correct the functional specification.
- Resolve open questions and conflicts.
- First fix all MUST FIX items.
- Then fix SHOULD FIX items.
- Then decide whether NICE TO HAVE items are worth doing now.
- Keep FUTURE items for roadmap planning.

### 6. Non-technical explanations

Use simple language.

Avoid unexplained technical terms.

If technical terms are necessary, explain them briefly.

Example:
“A release process means a clear set of steps for checking and publishing the application. If the project does not have a release process, every release depends more on memory and manual work, which increases the chance of mistakes.”

## docs/functional-spec.md

At the top, state one of:

- “This specification is based on existing requirements.”
- “This specification is DRAFT — inferred by the agent and requires user approval.”

For each feature:

| Field | Description |
|------|-------------|
| Feature name | Name of the functionality |
| Requirement source | Existing requirement / inferred / unclear |
| Business purpose | Why this feature exists |
| User | Who uses it |
| Happy path | Normal expected flow |
| Alternative flows | Other possible flows |
| Error cases | What can go wrong |
| Permissions | Who is allowed to use it |
| Data | What data is created/read/updated/deleted |
| UI behavior | What the user sees |
| Backend behavior | What the system does behind the scenes |
| Validations | Required checks |
| Security considerations | Security risks and rules |
| Status | Fully implemented / partially implemented / missing / unclear / conflicting |
| Gaps | Missing or unclear items |

## docs/requirements-source-map.md

Use:

| Source | Type | What it describes | Is it current? | Confidence | Notes |
|--------|------|-------------------|----------------|------------|-------|

## docs/conflicts-and-missing-items.md

Use:

| ID | Type | Description | Source(s) | Impact | Question for user | Recommended decision |
|----|------|-------------|-----------|--------|-------------------|----------------------|

Type values:
- Missing requirement
- Missing functionality
- Requirement/code conflict
- Requirement/requirement conflict
- Unclear behavior
- Product decision needed
- Technical decision needed

## docs/engineering-baseline-assessment.md

Use:

| Area | Exists? | Evidence | Current Gap | Risk | Recommended Fix |
|------|---------|----------|-------------|------|-----------------|

## docs/feature-test-matrix.md

Use:

| Feature | Expected behavior | Requirement source | Current implementation | Existing tests | Missing tests | Risk level | Notes |
|---------|-------------------|--------------------|------------------------|----------------|---------------|------------|-------|
