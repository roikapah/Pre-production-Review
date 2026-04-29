# Phase 1 — Discovery, Requirements & Functional Specification

Before changing any code, before refactoring, and before adding tests, analyze the existing application.

Your goal in Phase 1 is to create a clear functional specification of the application and a baseline engineering assessment.

## 1. Understand the application

Inspect the full codebase structure.

Identify:
- Frontend
- Backend
- Database
- Infrastructure
- Scripts
- Tests
- Documentation
- Configuration
- Deployment-related files
- Technology stack
- Main user flows
- Main business objects/entities
- External integrations
- APIs
- Payment providers
- Authentication providers
- Storage
- Emails
- Notifications
- Analytics
- Third-party services

Clearly mark each major area as:
- Fully implemented
- Partially implemented
- Missing
- Unclear

## 2. Locate existing requirements first

Before generating any new requirements, search for existing requirements or specification sources.

Search for:
- README files
- Docs
- Tickets
- User stories
- Comments
- API specs
- OpenAPI/Swagger files
- Trello/Jira references
- Markdown files
- Design docs
- TODO files
- Test files that describe expected behavior
- Any other requirements

Create:

`docs/requirements-source-map.md`

Use this table:

| Source | Type | What it describes | Is it current? | Confidence | Notes |
|--------|------|-------------------|----------------|------------|-------|

## 3. If requirements exist

If requirements exist, use them as the source of truth.

Do not invent a replacement specification unless the requirements are incomplete.

Create a mapping:

| Requirement | Source | Current implementation | Status | Gap | Notes |
|------------|--------|------------------------|--------|-----|-------|

Status values:
- Fully implemented
- Partially implemented
- Missing
- Conflicting
- Unclear

If requirements conflict with implementation, document the conflict.

If different requirement sources conflict with each other, document the conflict.

Create:

`docs/conflicts-and-missing-items.md`

Use this table:

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

## 4. If requirements do not exist

If requirements do not exist, generate inferred requirements based on the current application behavior and code.

Important:
- Mark all generated requirements as “DRAFT — inferred by the agent”.
- Do not treat inferred requirements as final.
- The user/product owner must approve them before Phase 2.
- If something is unclear, document it as a question.
- If there are multiple possible interpretations, document the options.

## 5. Create a functional specification

Create:

`docs/functional-spec.md`

At the top of the file, clearly state one of:

- “This specification is based on existing requirements.”
- “This specification is DRAFT — inferred by the agent and requires user approval.”

For each major feature/functionality, document:

- Feature name
- Business purpose
- Requirement source:
  - Existing requirement / inferred / unclear
- Who uses it
- Preconditions
- User flow / happy path
- Alternative flows
- Error cases
- Permissions / roles involved
- Data created, updated, deleted, or displayed
- APIs / services involved
- Expected UI behavior
- Expected backend behavior
- Important validations
- Security considerations
- Current implementation status:
  - Fully implemented
  - Partially implemented
  - Missing
  - Unclear
  - Conflicting
- Risks
- Gaps or questions

## 6. Explain functionality in simple language

Do not only describe individual code functions.

Explain at the functional/business-logic level.

Example:

Instead of:
“submitDeleteRequest() writes to DynamoDB”

Write:
“When a user requests account deletion, the system should verify that the email belongs to the user, create a pending deletion request, send a confirmation email, and only after confirmation mark the request for processing.”

## 7. Identify missing product-level requirements

Check whether the application has clear behavior for:

- Authentication and login
- Authorization and roles
- User registration / onboarding
- User profile management
- Main business flows
- Input validation
- Error handling
- Empty states
- Loading states
- Permissions
- Data retention
- Account deletion
- Audit logs
- Notifications
- Admin operations
- Reporting / dashboards, if relevant
- Payment / billing, if relevant
- Multi-tenant separation, if relevant
- Localization / languages, if relevant
- Mobile responsiveness, if relevant

## 8. Identify missing engineering practices

Do not assume best practices exist.

Actively check whether the project has:

- Automated tests
- Unit tests
- Integration tests
- API tests
- End-to-end tests
- Security tests
- Linting
- Formatting
- Type checking
- Build scripts
- Deployment scripts
- Environment separation:
  - local
  - dev
  - test
  - validation/staging
  - production
- Environment variable documentation
- Secret management
- Logging
- Monitoring
- Error handling strategy
- Backup/restore process, if relevant
- Rollback process
- Dependency vulnerability scanning
- Database migration strategy
- API documentation
- README/setup instructions
- Architecture documentation

## 9. Create engineering baseline assessment

Create:

`docs/engineering-baseline-assessment.md`

Use this table:

| Area | Exists? | Evidence | Current Gap | Risk | Recommended Fix |
|------|---------|----------|-------------|------|-----------------|

Use values:
- Exists
- Partially exists
- Missing
- Unclear

## 10. Create feature-to-test matrix

Create:

`docs/feature-test-matrix.md`

Use this table:

| Feature | Expected behavior | Requirement source | Current implementation | Existing tests | Missing tests | Risk level | Notes |
|---------|-------------------|--------------------|------------------------|----------------|---------------|------------|-------|

## 11. Create repair instructions

Create:

`docs/repair-instructions.md`

This must be useful both to a non-technical owner and to a developer.

Every issue must include:
- Plain-language explanation
- Business impact
- Risk if not fixed
- Recommended decision
- Technical explanation
- Files/modules likely involved
- Required fix
- Implementation steps
- Acceptance criteria
- Tests required
- Manual verification steps
- Definition of done

## 12. Stop after Phase 1

Do not continue to code changes.
Do not add tests yet.
Do not refactor.
Do not fix issues yet.

Use this exact message:

“Phase 1 completed. I created the functional specification, requirements source map, engineering baseline assessment, feature-test matrix, conflicts/missing-items list, and repair instructions. Please review and approve docs/functional-spec.md and docs/repair-instructions.md before I continue to implementation review, testing, security review, and gap fixing. If anything is missing, incorrect, or conflicting, send me clarifications and I will update the documents before continuing.”
