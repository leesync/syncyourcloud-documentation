# SyncYourCloud platform overview

SyncYourCloud helps fintech and payment engineering teams examine infrastructure readiness, payment-control gaps and operational risks. Users answer structured questions or configure a tool, review the generated output and, where their membership permits, export the result for further review.

The platform is a React single-page application. It combines:

- public assessments and lead-generation tools;
- an authenticated dashboard;
- payment-infrastructure assessment and design tools;
- Firebase Authentication and Firestore membership records;
- selected S3-backed form persistence through AWS Amplify Storage;
- hosted Stripe Payment Links for self-service subscriptions.

## What the tools produce

The payment tools generate structured artefacts such as:

- readiness scores and prioritised findings;
- PCI DSS gap summaries;
- architecture decision records;
- security-control matrices;
- cardholder-data-flow briefs;
- latency and scaling recommendations;
- IAM policy or Terraform examples;
- failure playbooks and observability configurations;
- cost models, rollback plans and failover runbooks.

These outputs support analysis and planning. They do not deploy infrastructure, move money, validate compliance or replace review by an authorised security, compliance or architecture professional.

## Product areas

| Area | Access | Purpose |
| --- | --- | --- |
| Public website | No sign-in | Product information, articles and selected public tools |
| Public assessments | No sign-in | Complete a readiness assessment and review browser-generated results |
| Dashboard | Sign-in required | Access membership features and payment tools |
| Membership | Public and authenticated views | Compare tiers and open the appropriate subscription or enquiry journey |
| Guides | Varies by route | Explain how individual tools work |

## Supported user journey

1. Open a public tool or sign in to the dashboard.
2. Enter information about the payment or cloud environment.
3. Review the generated score, configuration or report.
4. Treat the output as a decision-support artefact and verify it against the real environment.
5. Export the artefact when the relevant membership tier permits it.

## Important boundaries

- Payment dashboard calculations run in the browser in the documented build.
- Generated infrastructure-as-code and policy examples are not deployed automatically.
- Firebase holds identity and membership state; it is not the payment processor.
- Stripe hosts the self-service checkout journey.
- S3 persistence applies to the documented pre-screen form flow. Do not assume every assessment response is stored in S3.
- AI insight content in the supplied implementation notes is mock or planned unless separately verified in the deployed application.

## Next steps

- New user: [Complete an infrastructure readiness assessment](tutorials/complete-an-infrastructure-readiness-assessment.md)
- Developer or reviewer: [Read the architecture overview](explanations/architecture-overview.md)
- Support or operations: [Troubleshoot common issues](how-to/troubleshoot-common-issues.md)

