# SyncYourCloud Documentation

This repository contains product and technical documentation for SyncYourCloud, a React-based platform for assessing and documenting payment infrastructure on AWS.

The documentation follows a docs-as-code workflow and separates four types of content:

- **Tutorials** help a new user complete a task for the first time.
- **How-to guides** explain how to achieve a specific outcome.
- **Reference pages** describe routes, tools, fields and system behaviour.
- **Explanations** describe architecture, design decisions and security boundaries.

## Start here

- [Platform overview](docs/index.md)
- [Complete an infrastructure readiness assessment](docs/tutorials/complete-an-infrastructure-readiness-assessment.md)
- [Architecture overview](docs/explanations/architecture-overview.md)
- [Authentication and access](docs/explanations/authentication-and-access.md)
- [Payment tools reference](docs/reference/payment-tools.md)
- [Troubleshooting](docs/how-to/troubleshoot-common-issues.md)
- [Verification matrix](verification/verification-matrix.md)
- [Portfolio readiness](PORTFOLIO_READINESS.md)

## Documentation status

This is version `0.1.0` of the documentation set. It describes behaviour supported by the April 2026 application documentation supplied for review.

SyncYourCloud does not currently offer a supported public API. The `openapi/` directory records the boundary for a future, separately deployed demonstration API. No API endpoints are documented as live until they have been implemented and tested.

## Scope and accuracy

The documentation distinguishes between:

- live application behaviour;
- browser-generated simulations and exports;
- prototype or mock features;
- planned integrations.

Do not describe a prototype or mock feature as production AI. Do not describe browser-generated tool output as infrastructure deployed into a customer's AWS account.

AI-generated company scenarios and outputs may be retained as **synthetic test fixtures**. They are useful for repeatable testing but are not customer validation, practitioner review or evidence of production deployment.

## Local preview

All pages are standard Markdown and can be reviewed directly in GitHub. A static documentation site can be added later without changing the content model.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for the review and verification workflow.
