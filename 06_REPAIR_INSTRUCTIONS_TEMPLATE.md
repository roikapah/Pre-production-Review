# Repair Instructions Template

Use this exact structure for every finding in `docs/repair-instructions.md`.

---

## FINDING-[NUMBER] — [Short title]

### Priority

MUST FIX / SHOULD FIX / NICE TO HAVE / FUTURE

### Area

Functional / Testing / Security / UX / Performance / Reliability / Documentation / Configuration / Deployment / Code Quality / Architecture / Requirements

### Status

Missing / Partially implemented / Implemented incorrectly / Unclear / Needs improvement / Conflicting

### Requirement source

Existing requirement / Inferred requirement / No requirement found / Conflicting sources

### Plain-language explanation

Explain the issue in simple words for someone without programming experience.

Avoid jargon.

Explain what the user or business impact is.

Example:
“The login screen exists, but there are no automatic checks that prove it keeps working. This means a developer could accidentally break login in the future and nobody would know until a real user complains.”

### Business impact

Explain why this matters to the business, users, support, sales, operations, or release readiness.

### Risk if not fixed

Explain what could go wrong.

### Recommended decision

Explain what the owner should decide.

Examples:
- Do not release before fixing this.
- Can be released to internal testers, but should be fixed before public launch.
- Can wait until after launch.
- Product owner must clarify the expected behavior before implementation.
- Only needed if the application grows or gets more users.

### Technical explanation for developer

Explain the technical reason for the issue.

### Likely files/modules involved

List the relevant files, folders, APIs, components, tests, configuration files, or infrastructure files.

### Required fix

Describe exactly what needs to be changed.

### Implementation steps

1. Step one
2. Step two
3. Step three

### Acceptance criteria

- Clear condition 1
- Clear condition 2
- Clear condition 3

### Tests required

- Unit tests:
- Integration/API tests:
- UI/E2E tests:
- Security/authorization tests:
- Manual verification:

### Manual verification steps

1. Open/use this screen/API.
2. Perform this action.
3. Confirm this expected result.

### Definition of done

The issue is considered fixed only when:

- The requirement/expected behavior is approved if it was unclear or inferred.
- The implementation is complete.
- Relevant tests were added or updated.
- Tests pass.
- Manual verification passes.
- Documentation was updated if needed.

---
