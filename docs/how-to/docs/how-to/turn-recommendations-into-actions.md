---
title: Turn recommendations into actions
description: Validate assessment recommendations and convert accepted findings into owned, prioritised actions.
---

# Turn recommendations into actions

Convert validated Infrastructure Readiness recommendations into actions with an owner, priority and target date.

Do not implement a generated recommendation without reviewing it against the live environment and your organisation’s requirements.

## Before you begin

You need:

- a completed Infrastructure Readiness result;
- a list of reviewed recommendations;
- evidence supporting each accepted finding;
- access to the appropriate technical or operational owners; and
- your organisation’s change-management process.

If you have not validated the recommendations, first [review the Infrastructure Readiness result](review-infrastructure-result.md).

## 1. Confirm the finding

Check the assessment answer associated with the recommendation.

Confirm that:

- the answer describes the current environment;
- the supporting evidence is current;
- the finding applies to the assessed scope; and
- the recommendation has been reviewed by an appropriate owner.

If the answer was incorrect, record the correction and reassess the environment before creating an action.

## 2. Describe the required outcome

Write the action as an outcome rather than copying the recommendation without context.

Include:

- the condition that needs attention;
- the affected environment or service;
- the intended result;
- the evidence required to demonstrate completion; and
- any known constraints or dependencies.

For example:

> Validate the recovery process for the payment API by completing an approved failover exercise and recording the measured recovery time and recovery point.

This is more useful than:

> Improve disaster recovery.

## 3. Assess the priority

Evaluate the potential effect of the finding on:

- security and access control;
- cardholder or customer data;
- payment processing;
- regulatory or contractual obligations;
- service availability;
- data integrity;
- recovery capability; and
- operational cost.

Assign a priority using your organisation’s approved risk or work-management process.

If no internal model exists, use the following categories as an initial planning aid:

| Priority | Use when |
| --- | --- |
| **Critical** | Immediate review is required because the condition could cause severe security, compliance, payment or availability consequences. |
| **High** | Prompt action is required to address a material weakness or untested control. |
| **Medium** | The finding should be scheduled, but existing controls reduce the immediate exposure. |
| **Low** | The action is an improvement with limited immediate impact. |

These categories do not replace an approved organisational risk assessment.

## 4. Assign an owner

Assign the action to a person or team with the authority and knowledge to investigate and complete it.

Depending on the finding, the owner may work in:

- engineering;
- cloud operations;
- security;
- compliance;
- architecture;
- finance or FinOps;
- service management; or
- payment operations.

Record other teams that must review, approve or support the action.

## 5. Set completion criteria

Define how reviewers will determine that the action is complete.

Completion evidence might include:

- an approved configuration record;
- a successful test result;
- an updated architecture diagram;
- monitoring or alerting evidence;
- an incident-response exercise;
- a disaster-recovery report;
- an approved policy or procedure; or
- an independent security or compliance review.

Creating a document does not prove that a control has been implemented or tested.

## 6. Set a target date

Choose a target date based on:

- the assigned priority;
- technical dependencies;
- change windows;
- available resources;
- regulatory or contractual deadlines; and
- the time required for testing and approval.

If the action is deferred, record the reason, approving authority and next review date.

## 7. Track the action

Record the action in your organisation’s approved work-management or risk-management system.

Include:

| Field | Required information |
| --- | --- |
| Finding | The validated condition identified during the review |
| Scope | The affected environment, product or service |
| Priority | Critical, high, medium or low |
| Owner | Person or team responsible |
| Target date | Planned completion date |
| Completion criteria | Evidence required to close the action |
| Status | Accepted, in progress, blocked, completed or deferred |
| Dependencies | Required teams, changes or approvals |
| Evidence | Links or references to supporting records |

Do not store credentials, secrets, cardholder data or other restricted information in the action record.

## 8. Verify completion

Before closing the action:

1. Review the completion evidence.
2. Confirm that the change applies to the assessed environment.
3. Verify that required testing and approvals are complete.
4. Check for unintended effects.
5. Record who accepted the completed action and when.

Repeat the assessment when appropriate, but do not use a new score as the only evidence that the action succeeded.

## Expected result

You should finish with a prioritised action that has:

- a clearly defined outcome;
- an authorised owner;
- a target date;
- measurable completion criteria;
- supporting evidence; and
- a recorded review status.

## Next steps

- [Review an Infrastructure Readiness result](review-infrastructure-result.md)
- [Understand how assessments work](../explanations/how-assessments-work.md)
- [Review assessment limitations](../reference/assessment-reference.md#limitations)
