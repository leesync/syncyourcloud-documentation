---
title: How assessments work
description: Understand how SyncYourCloud assessments turn structured answers into scores, findings and recommendations.
---

# How assessments work

SyncYourCloud assessments use structured questions to help you examine a defined environment and identify areas that may require further investigation.

An assessment provides decision support. It does not inspect your cloud account, verify your answers or make changes to your infrastructure.

## Assessment workflow

An assessment follows four stages:

1. **Define the scope.** Choose one environment, product or workload.
2. **Answer the questions.** Describe the current state using the available responses.
3. **Generate the result.** SyncYourCloud evaluates the submitted answers and presents the available scores, findings and recommendations.
4. **Validate the result.** Compare important findings with live configuration and organisational evidence.

The quality of the result depends on the accuracy, completeness and scope of the submitted answers.

## Assessment scope

Each assessment should represent one clearly defined environment, product or workload.

For example, separate assessments may be appropriate for:

- production and non-production environments;
- independently operated payment products;
- workloads with different cloud architectures;
- systems operating in different regions; or
- environments governed by different security or compliance controls.

Combining several environments in one response can obscure important differences and make the result less useful.

## Infrastructure Readiness layers

The Infrastructure Readiness Check organises its questions into seven layers:

| Layer | Area considered |
| --- | --- |
| **Agent Orchestration** | The coordination and control of automated or agent-supported processes |
| **Security & Encryption** | Security controls, access protection and the protection of data |
| **Compliance & Audit** | Governance, evidence and audit-related practices |
| **Cost Optimisation** | Cost visibility, resource use and optimisation practices |
| **Observability & Monitoring** | Monitoring, alerting and operational visibility |
| **Payment Gateway Integration** | The resilience and operation of payment-related integrations |
| **Disaster Recovery** | Recovery planning, testing and continuity arrangements |

The layers provide a consistent way to organise the result. They do not represent every control or requirement that may apply to an environment.

## Answers and evidence

Assessment answers are declarations made by the person completing the assessment. SyncYourCloud does not automatically inspect or confirm the corresponding configuration.

An answer is more reliable when it is supported by evidence such as:

- current architecture records;
- approved configurations;
- monitoring data;
- test results;
- incident or change records;
- security-control evidence; or
- compliance documentation.

A documented control is not necessarily an implemented control. An implemented control is not necessarily an effective or tested control.

## Scores

The Payment Sync Score summarises the answers submitted during the assessment.

The score can help you:

- establish an initial view of the environment;
- compare results from repeated assessments of the same scope;
- identify layers that require closer examination; and
- communicate areas for further investigation.

Do not use the score as the sole basis for a production, security, compliance or investment decision.

Changes in scope, interpretation or evidence can affect the result. A later score should only be compared with an earlier score when both assessments represent equivalent environments and use consistent evidence.

## Layer results

The Layer Breakdown provides a more detailed view of the assessment than the overall score.

Review layer results to identify:

- weaker areas hidden by the overall score;
- assumptions that require validation;
- controls that have not been tested;
- missing evidence; and
- areas requiring specialist review.

A strong result in one layer does not offset a serious weakness in another.

## Findings and recommendations

Recommendations indicate areas that may require validation, investigation or improvement.

A recommendation is not an instruction to make an immediate production change. Before acting on it:

1. Confirm the associated assessment answer.
2. Compare the finding with current evidence.
3. Determine whether it applies to the assessed environment.
4. Ask an authorised owner to review it.
5. Record the resulting decision and evidence.

A recommendation may be accepted, rejected, deferred or marked as requiring further investigation.

## Repeating an assessment

Repeat an assessment when it supports a defined review activity, such as:

- evaluating a material architecture change;
- reviewing progress after completing approved actions;
- preparing for an internal technical review;
- reassessing recovery arrangements after a test; or
- examining a significant change in payment volume or operating model.

Do not compare results casually across unrelated systems. Record the scope, date and supporting evidence for each assessment.

## Human review

SyncYourCloud assessments are designed to support human decision-making.

Important findings should be reviewed by people with responsibility for the affected area, which may include:

- engineering;
- architecture;
- cloud operations;
- security;
- compliance;
- FinOps;
- service management; or
- payment operations.

Generated output does not replace professional judgement, organisational governance or authorised approval.

## Limitations

An assessment does not:

- connect to or inspect your AWS account automatically;
- verify that submitted answers are accurate;
- deploy or modify cloud infrastructure;
- process or move money;
- test payment transactions;
- certify PCI DSS compliance;
- guarantee security, resilience or availability; or
- replace an authorised technical, security or compliance review.

For the complete list, see [Assessment reference](../reference/assessment-reference.md#limitations).

## Related guides

- [Complete your first assessment](../tutorials/complete-your-first-assessment.md)
- [Review an Infrastructure Readiness result](../how-to/review-infrastructure-result.md)
- [Turn recommendations into actions](../how-to/turn-recommendations-into-actions.md)
