---
title: Review an Infrastructure Readiness result
description: Interpret your Payment Sync Score, layer results and recommendations.
---

# Review an Infrastructure Readiness result

Review your Infrastructure Readiness result to identify areas that require validation, investigation or improvement.

The result supports technical decision-making. It does not certify that an environment is secure, resilient or compliant.

## Before you begin

You need:

- a completed Infrastructure Readiness Check;
- the environment used to answer the assessment;
- access to relevant technical and operational evidence; and
- support from the appropriate engineering, security or compliance owners.

If the result is no longer available, complete a new assessment using the current state of the same environment.

## 1. Check the assessment scope

Confirm which environment, product or workload the answers describe.

Do not compare the result with live evidence from a different environment. Differences in regions, services, configurations and operating procedures can make the comparison misleading.

Record the assessment date and its scope before reviewing individual findings.

## 2. Review the Payment Sync Score

Use the **Payment Sync Score** as a summary of the submitted answers.

Do not interpret the score in isolation. Two environments with similar overall scores may have different weaknesses and risk profiles.

A high score does not override:

- a critical finding within one layer;
- an untested resilience assumption;
- a missing security control;
- incomplete compliance evidence; or
- an inaccurate assessment answer.

## 3. Review the Layer Breakdown

Examine the points, percentage and status shown for each layer:

- Agent Orchestration;
- Security & Encryption;
- Compliance & Audit;
- Cost Optimisation;
- Observability & Monitoring;
- Payment Gateway Integration; and
- Disaster Recovery.

Identify:

- the lowest-scoring layers;
- layers with critical or high-priority findings;
- controls that exist in documentation but are not implemented;
- processes that have not been tested; and
- answers that were based on incomplete evidence.

The lowest percentage is not automatically the first problem to address. Consider the potential effect of each finding on security, payment processing, compliance, availability and recovery.

## 4. Read the recommendations

Review the recommendations associated with each layer.

For every important recommendation, ask:

1. Which assessment answer produced this finding?
2. Was the answer supported by current evidence?
3. Does the recommendation apply to this architecture?
4. What could happen if the condition remains unchanged?
5. Who is authorised to review or approve any resulting action?

A recommendation may identify an area for investigation without prescribing the correct implementation for your environment.

## 5. Validate the underlying evidence

Compare each priority finding with relevant evidence, such as:

- approved architecture diagrams;
- AWS configuration records;
- monitoring and alerting settings;
- incident and change records;
- disaster-recovery test results;
- security policies and control evidence;
- compliance records; and
- payment-provider or acquirer requirements.

Use read-only evidence where possible during the initial review.

Do not change a production environment solely because an assessment generated a recommendation.

## 6. Assign a review outcome

Assign one of the following outcomes to each priority recommendation:

| Outcome | Meaning |
| --- | --- |
| **Accepted** | The finding is supported by evidence and requires action. |
| **Rejected** | Evidence shows that the finding does not apply or was based on an incorrect answer. |
| **Deferred** | The finding is valid, but action will be considered later. |
| **Needs investigation** | More evidence or specialist review is required. |

Record the evidence and reasoning supporting the outcome.

## 7. Escalate important findings

Ask the appropriate owner to review findings that could affect:

- cardholder or customer data;
- identity and access controls;
- encryption or secret management;
- payment processing;
- regulatory or contractual obligations;
- production availability; or
- disaster recovery.

The assessment result does not replace an authorised technical, security, compliance or architecture review.

## Expected result

You should finish with:

- a recorded assessment scope and date;
- a list of priority findings;
- evidence associated with each finding;
- an assigned review outcome; and
- identified owners for further investigation or action.

## Next steps

- [Turn recommendations into actions](turn-recommendations-into-actions.md)
- [Understand how assessments work](../explanations/how-assessments-work.md)
- [Review assessment limitations](../reference/assessment-reference.md#limitations)
