# Priority Levels

Use these exact priority levels in all reports.

## MUST FIX

Critical issue that should be fixed before release or before real users use this feature.

Examples:
- Broken core functionality
- Security issue
- Data loss risk
- Payment issue
- Authentication issue
- User cannot complete an important flow
- No tests for a critical flow
- Serious production stability risk
- Requirement/code conflict that blocks correct implementation

Recommended decision examples:
- Do not release before fixing this.
- Do not expose to real users before fixing this.
- Only test internally if the risk is understood.

## SHOULD FIX

Important issue that should be fixed soon, but may not block a limited internal test or controlled beta.

Examples:
- Weak error handling
- Missing edge-case tests
- Poor UX in important but non-critical flow
- Missing logging for important operations
- Partial validation gaps
- Incomplete documentation for developers
- Unclear requirement that affects important behavior but does not block basic testing

Recommended decision examples:
- Can be released to internal testers, but should be fixed before public launch.
- Should be fixed before scaling usage.
- Should be planned in the next sprint.

## NICE TO HAVE

Improvement that makes the application better, cleaner, easier to maintain, or more professional, but does not block release.

Examples:
- UI polish
- Code cleanup
- Better naming
- More detailed documentation
- Extra analytics
- Performance optimization for non-heavy flows
- Improved developer experience

Recommended decision examples:
- Can wait until after launch.
- Useful improvement, but not a release blocker.
- Consider if time/budget allows.

## FUTURE

Larger improvement or architectural enhancement that is useful later but not required now.

Examples:
- Advanced monitoring dashboards
- Advanced role management
- Multi-region deployment
- Advanced automation
- Complex scalability improvements
- More mature release automation later, if needed

Recommended decision examples:
- Add to roadmap.
- Revisit when the product grows.
- Not required for current release.
