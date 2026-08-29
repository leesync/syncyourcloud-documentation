# SyncYourCloud Documentation

Product documentation and live-site verification records for [SyncYourCloud](https://syncyourcloud.io), a platform that helps fintech and payment teams assess AWS infrastructure, payment controls and operational readiness.

This repository demonstrates a docs-as-code workflow covering product documentation, procedural testing, technical review and maintenance through GitHub issues and pull requests.

## What this repository contains

- Task-based tutorials for new users.
- How-to and troubleshooting guidance.
- Explanations of architecture, authentication and access boundaries.
- Reference material for payment-infrastructure tools.
- Dated verification records comparing documented behaviour with the deployed product.
- Contribution, style and change-management guidance.

## Start here

- [Platform overview](docs/index.md)
- [Complete an Infrastructure Readiness assessment](docs/tutorials/complete-an-infrastructure-readiness-assessment.md)
- [Architecture overview](docs/explanations/architecture-overview.md)
- [Authentication and access](docs/explanations/authentication-and-access.md)
- [Payment tools reference](docs/reference/payment-tools.md)
- [Troubleshoot common issues](docs/how-to/troubleshoot-common-issues.md)
- [Known limitations](docs/reference/known-limitations.md)
- [Verification matrix](verification/verification-matrix.md)
- [Portfolio readiness](PORTFOLIO_READINESS.md)

## Live-site verification

The initial verification cycle was completed on **28 August 2026**. Six checks were performed against the deployed SyncYourCloud application using Safari Private Browsing.

Each check recorded the route and journey tested, expected behaviour, dated actual result, status, appropriate evidence and required follow-up. Only public information and fictional test data were used. Credentials, tokens, private infrastructure identifiers and customer data were excluded.

### Verification summary

| Check | Result | Verified behaviour or finding |
| --- | --- | --- |
| SYC-001: Product inventory claims | Fail | Three homepage references used the outdated term **25 modules**. Other product journeys referred to **26 assessments** and **28+ assessments**, so the product did not present one consistent inventory. |
| SYC-002: Infrastructure Readiness route | Pass | The intended assessment opened at question 1 of 21 without requiring authentication. |
| SYC-003: PCI DSS Gap Analysis journey | Fail | Public copy promised no-sign-in access, but the call to action opened a paid membership and authentication journey. |
| SYC-004: Public editorial copy | Fail, remediated | Internal editorial instructions, inconsistent terminology and mismatched navigation were visible in published copy. Customer-facing copy was deployed through application pull request #18 and retested. |
| SYC-005: Protected dashboard access | Pass | An unauthenticated request redirected to sign-in without exposing dashboard, account, membership, assessment or report content. |
| SYC-006: Public assessment access | Pass | The free Infrastructure Readiness Check opened at question 1 of 21 without registration, authentication, membership or payment. |

The count references document what the tested interfaces displayed; they do not declare that 25, 26 or 28+ is the authoritative inventory. Maintaining one canonical inventory remains a product-governance requirement.

The audit was tracked through [issue #1](https://github.com/leesync/syncyourcloud-documentation/issues/1) and merged through [documentation pull request #2](https://github.com/leesync/syncyourcloud-documentation/pull/2). The customer-facing copy correction was delivered separately through application pull request #18 so that product defects were not disguised as documentation changes.

## Documentation model

The repository separates four kinds of content:

- **Tutorials** guide a new user through a complete learning task.
- **How-to guides** help a user achieve a specific outcome or resolve a problem.
- **Reference pages** record routes, tools, fields and defined system behaviour.
- **Explanations** describe architecture, design decisions and security boundaries.

The GitHub repository is the detailed source of truth. Shorter user-facing versions of the dashboard, assessment and results guidance can be published in a Help or Guides area on the SyncYourCloud website and linked from relevant product screens.

## Product boundaries

The documentation distinguishes between verified live behaviour, browser-generated simulations and exports, prototypes or mock features, and planned integrations.

Generated assessment output supports analysis and planning. It does not deploy infrastructure, move money, validate PCI DSS compliance or replace review by an authorised security, compliance or architecture professional.

SyncYourCloud does not currently provide a supported public API. API portfolio material must be labelled as a demonstration or proposed integration until working endpoints have been implemented, secured and tested.

## Website documentation recommended

The public product should provide concise guidance for:

1. Creating an account and signing in.
2. Navigating the dashboard.
3. Choosing the appropriate assessment.
4. Answering assessment questions safely.
5. Interpreting scores, findings and recommendations.
6. Saving, exporting or retrieving results.
7. Understanding membership and access restrictions.
8. Troubleshooting common access and assessment problems.
9. Understanding how submitted data is handled.
10. Recognising the limitations of generated outputs.

Contextual links should appear beside the relevant dashboard feature or assessment rather than requiring users to search the repository.

## Contributing

Read [CONTRIBUTING.md](CONTRIBUTING.md) before changing product claims or procedures. A documented route or behaviour should not be labelled **verified** until every published step has been tested against the deployed application and the dated result has been recorded.

## Version status

The initial documentation set is version `0.1.0`. The live-site verification cycle supplements that baseline with evidence gathered on 28 August 2026. See [CHANGELOG.md](CHANGELOG.md) for recorded changes.
