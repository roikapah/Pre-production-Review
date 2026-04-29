# Phase 2 — Implementation Review, Testing & Quality

Only after the functional specification and repair instructions are approved, continue to Phase 2.

Do not start Phase 2 if:
- The functional specification is still draft and not approved.
- There are unresolved conflicts that block understanding of expected behavior.
- The user/product owner said something is missing or incorrect and the documents were not updated yet.

Your goal in Phase 2 is to verify that the application implementation matches the approved functional specification and to help fix approved gaps.

## 1. Functional coverage review

For every feature in `docs/functional-spec.md`:

- Check whether it is implemented.
- Check whether the implementation matches the expected behavior.
- Check whether edge cases are handled.
- Check whether error states are handled.
- Check whether permissions are enforced.
- Check whether the UI and backend behavior are aligned.
- Check whether APIs validate inputs correctly.
- Check whether database updates are correct and safe.

## 2. Test coverage review

Review all existing tests.

Check for:
- Unit tests
- Integration tests
- API tests
- UI tests
- End-to-end tests
- Security tests
- Regression tests
- Negative/error tests
- Permission/authorization tests
- Edge-case tests

For every feature, determine:
- Is there a test?
- Is the test meaningful?
- Does it test only the happy path?
- Does it test failure scenarios?
- Does it test authorization/security?
- Does it test important validations?
- Are mocks used correctly?
- Are tests stable or flaky?

## 3. Add or improve tests if approved

If tests are missing or weak, add tests only when implementation work is approved.

Tests should cover:
- Happy path
- Invalid inputs
- Unauthorized access
- Forbidden access
- Missing data
- Duplicate data
- External API failure
- Database failure where practical
- Empty state
- Boundary cases
- Important business rules

Do not write shallow tests only to increase coverage.
Tests must prove that the functionality works correctly.

## 4. Security review

Review the application for security issues.

Check at least:
- Authentication correctness
- Authorization / role-based access
- User can access only their own data
- Tenant isolation, if relevant
- Input validation
- Injection risks
- XSS risks
- CSRF risks, if relevant
- Insecure direct object references
- Secrets in code or logs
- Unsafe environment variables
- Overly permissive CORS
- Exposed admin APIs
- Missing rate limits
- File upload security, if relevant
- Payment security, if relevant
- Token handling
- Password handling, if relevant
- Sensitive data in logs
- Data deletion and retention
- Dependency vulnerabilities

## 5. UX and usability review

Review:
- Clear navigation
- Clear labels
- Error messages users can understand
- Loading indicators
- Empty states
- Confirmation dialogs for destructive actions
- Mobile responsiveness
- Accessibility basics
- Keyboard navigation where relevant
- Consistent design
- Forms validation messages
- Success messages
- Prevention of accidental actions

## 6. Performance and efficiency review

Check:
- Unnecessary API calls
- Slow queries
- Missing indexes
- Large payloads
- Inefficient loops
- Repeated database reads
- Frontend rendering problems
- Bundle size issues
- Caching opportunities
- Pagination where needed
- Background jobs where needed
- Timeout and retry handling

## 7. Reliability and error handling

Check:
- Proper try/catch or equivalent error handling
- User-friendly error messages
- Backend logs include enough context
- External API failures are handled
- Retries are safe and do not duplicate actions
- Idempotency for important operations
- Partial failure behavior
- Rollback or compensation logic, if relevant

## 8. Code quality review

Check:
- Clear structure
- Separation of concerns
- Reusable components/services
- Avoid duplicated logic
- Avoid hardcoded values
- Clear naming
- Maintainable files
- No dead code
- No unused dependencies
- No debug code left behind
- No console logs leaking sensitive data
- Clear configuration handling

## 9. Deployment and release-readiness review

Check whether the project has a clear and repeatable release process.

Review:
- How the application is built.
- How tests are run before release.
- How configuration and environment variables are handled.
- How secrets are protected.
- How deployment is performed.
- Whether production deployment is manual, automatic, or unclear.
- Whether there is a rollback plan.
- Whether there is a validation/staging environment, if relevant.
- Whether release steps are documented.
- Whether a non-developer can understand the release risk.

If the deployment process is missing or unclear:
- Document it as a missing engineering capability.
- Recommend a minimal release checklist appropriate for the stack.
- Add clear implementation instructions to `docs/repair-instructions.md`.

Minimum recommended release checklist should usually include:
- Install dependencies.
- Run lint or formatting checks, if relevant.
- Run type checks, if relevant.
- Run unit tests.
- Run integration tests where practical.
- Build the application.
- Check required environment variables.
- Confirm secrets are not committed.
- Deploy to validation/staging first, if relevant.
- Manually approve production deployment.
- Document rollback steps.

## 10. Documentation review

Check whether the project has:
- README
- Setup instructions
- Local development instructions
- Environment variable documentation
- Test instructions
- Deployment instructions
- API documentation
- Architecture overview
- Troubleshooting section

If missing, create clear repair instructions.

## 11. Update reports

Create or update:

- `docs/implementation-gap-report.md`
- `docs/test-coverage-report.md`
- `docs/security-review.md`
- `docs/ux-review.md`
- `docs/performance-review.md`
- `docs/recommended-roadmap.md`
- `docs/repair-instructions.md`

## 12. Implement only approved fixes

If the developer/product owner explicitly asks you to fix issues:

- Start with MUST FIX items.
- Make small focused changes.
- Do not rewrite large parts without approval.
- Update or add tests for every fix.
- Run the relevant test suite.
- Document what changed.

## 13. Final recommendation

At the end, provide a clear recommendation:

- Ready for release
- Not ready for release
- Ready for internal testing only
- Ready after MUST FIX items are resolved
- Ready after MUST FIX + SHOULD FIX items are resolved
