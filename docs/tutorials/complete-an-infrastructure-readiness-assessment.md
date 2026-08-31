---
title: Complete your first assessment
description: Complete the Infrastructure Readiness Check and review your Payment Sync Score.
---

# Complete your first assessment

Complete the free **Infrastructure Readiness Check** to evaluate one environment, review its Payment Sync Score and identify recommendations that require further investigation.

## Before you begin

Choose one environment, product or workload to assess. Gather high-level information about its:

- cloud provider and principal regions;
- main architecture services;
- approximate transaction or workload volumes;
- availability and disaster-recovery arrangements;
- monitoring, security and compliance controls; and
- known operational constraints.

Do not enter:

- cardholder or customer data;
- credentials, access tokens or private keys;
- production secrets;
- confidential infrastructure identifiers; or
- information you are not authorised to share.

## 1. Open the assessment

Open **Infrastructure Readiness Check** from the SyncYourCloud assessment tools.

You can complete the assessment and view its initial result without signing in.

The assessment contains 21 questions across seven layers:

- Agent Orchestration;
- Security & Encryption;
- Compliance & Audit;
- Cost Optimisation;
- Observability & Monitoring;
- Payment Gateway Integration; and
- Disaster Recovery.

## 2. Define the scope

Use the same environment throughout the assessment.

Complete a separate assessment for each additional environment, product or workload. Combining information from different systems can produce findings that do not accurately represent any one environment.

## 3. Answer for the current state

For each question, select the answer that reflects what is implemented now, then select **Next**.

Do not record a planned control as an implemented control.

For example, a documented disaster-recovery plan is different from a failover process that has been tested against defined recovery time and recovery point objectives.

If you do not know an answer:

1. Check the relevant configuration, report or system record.
2. Ask the responsible engineering, security or compliance owner.
3. Return to the assessment when you have sufficient evidence.

Do not guess solely to complete the assessment.

The page displays:

- the current question;
- the completion percentage; and
- the number of answered questions.

Select **Back** to review or change an earlier answer.

## 4. Review your answers

Before viewing the result, confirm that:

- every answer concerns the same environment;
- planned controls are not recorded as implemented;
- documented processes are distinguished from tested processes;
- assumptions are not presented as verified facts; and
- no sensitive or restricted information has been entered.

## 5. View the result

After answering question 21, select **View My Results**.

The results page displays:

- the **Payment Sync Score**;
- a summary of the number of layers at risk;
- a **Layer Breakdown** containing points, percentages and status labels; and
- recommendations for each assessment layer.

## 6. Review the findings

Read the overall score together with the layer breakdown and recommendations.

Pay particular attention to:

- critical or high-priority findings;
- controls that are documented but not enforced;
- resilience arrangements that have not been tested;
- missing operational evidence; and
- recommendations based on information that the assessment cannot independently verify.

A high overall score does not cancel a serious finding within an individual layer.

Choose one recommendation for further review. Confirm the corresponding assessment answer and compare the finding with the live environment before planning a change.

## Expected result

You should now have:

- a Payment Sync Score;
- results for each assessment layer;
- a set of recommendations; and
- at least one recommendation selected for evidence-based review.

The assessment provides decision support. It does not certify compliance or replace an authorised security, compliance or architecture review.

## Next steps

- [Review an Infrastructure Readiness result](../how-to/review-infrastructure-result.md)
- [Turn recommendations into actions](../how-to/turn-recommendations-into-actions.md)
- [Understand how assessments work](../explanations/how-assessments-work.md)
- [Review assessment limitations](../reference/assessment-reference.md#limitations)
