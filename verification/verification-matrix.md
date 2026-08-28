# Documentation verification matrix

Use this matrix to turn the documentation set into credible portfolio evidence. A page is portfolio-ready only when its procedure and claims have been checked against the deployed application or source.

| Documentation area | Current evidence | Verification needed | Portfolio status |
| --- | --- | --- | --- |
| Application routes | April 2026 application documentation | Open every documented public route and sample protected routes | Draft |
| Firebase sign-in | Function and context descriptions | Test email/password, Google redirect, sign-out and reset with a test account | Draft |
| Membership updates | Firestore listener description | Change a test user's tier and record the observed UI update | Draft |
| Infrastructure assessment | Flow and service documentation | Complete the assessment twice; record remote and fallback behaviour | Draft |
| Payment tool outputs | Tool catalogue and synthetic scenarios | Run each deployed tool with a controlled fictional input set | Draft |
| Export gating | `TierLockButton` description | Test one locked and one permitted export with test tiers | Draft |
| S3 persistence | `prescreenS3Service` description | Save, retrieve and inspect fictional pre-screen data in a test environment | Draft |
| Stripe journey | Hosted Payment Link description | Open test or live checkout without completing a charge; verify return/cancel behaviour | Draft |
| AI insights | Mock/planned implementation notes | Confirm deployed implementation and model invocation before documenting as live | Not verified |
| Public API | No supported implementation evidence | Build, secure and test the separate demonstration API | Not available |

## Required test record

For every completed verification, record:

- test date;
- environment and application version;
- fictional input data;
- procedure followed;
- expected result;
- actual result;
- screenshots or logs with sensitive values removed;
- issue raised or documentation correction made.

## Evidence standard

Use the following wording in applications only after the corresponding evidence exists:

- **Authored**: you researched and wrote the documentation.
- **Verified**: you performed every documented step and compared the result with the page.
- **Maintained through Git**: the public repository shows commits, branches and pull-request review.
- **Documented an API**: a working endpoint and validated OpenAPI specification exist.
- **Tested with Postman**: the published collection runs successfully against the documented environment.

