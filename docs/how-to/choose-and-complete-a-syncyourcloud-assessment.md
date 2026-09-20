# How to choose and complete a SyncYourCloud assessment

Use a SyncYourCloud assessment to review the current state of your payment infrastructure, identify gaps and create a prioritised list of actions.

This guide explains how to choose the right assessment, prepare useful information and review your results safely.

## Choose the right assessment

Start with the problem you need to understand.

| If you want to… | Start with… |
| --- | --- |
| Review the overall readiness of your payment infrastructure | **Infrastructure Readiness Check** |
| Identify potential gaps against Payment Card Industry Data Security Standard (PCI DSS) requirements | **PCI DSS Gap Analysis** |
| Review your readiness to work with an acquirer | **Acquirer Readiness Assessment** |

If you are unsure where to begin, use the **Infrastructure Readiness Check**. It provides the broadest starting point and can help you identify areas that need a more focused review.

## Before you begin

Gather high-level information about the environment you want to assess, including:

- your cloud provider and primary region;
- the main services in your architecture;
- approximate transaction or workload volumes;
- resilience and disaster-recovery arrangements;
- monitoring, security and compliance controls;
- known operational problems.

Answer for one clearly defined environment, product or workload. Mixing several systems in one response can make the findings less useful.

Do not enter:

- cardholder or customer data;
- passwords, credentials or access tokens;
- private keys or production secrets;
- confidential infrastructure identifiers;
- information you are not authorised to share.

## Complete an assessment

### 1. Open the assessment

Select the assessment from the SyncYourCloud website or your dashboard.

The public **Infrastructure Readiness Check** can be started without creating an account. Assessments and features inside the protected dashboard require you to sign in, and some may require an eligible membership.

### 2. Read the introduction

Check the purpose of the assessment and any access requirements before you begin. Make sure it addresses the environment or decision you want to review.

### 3. Answer using the current state

Choose the answer that reflects what is implemented today, not what is planned.

For example, a disaster-recovery plan that has not been tested is different from a failover process that has been exercised with measured recovery objectives.

If you are unsure about an answer, check the relevant system record or ask the responsible engineering, security or compliance owner. Avoid guessing simply to complete the assessment.

### 4. Review your answers

Before submitting, check that:

- every answer relates to the same environment;
- planned controls have not been recorded as implemented controls;
- tested processes are distinguished from documented-only processes;
- no sensitive or restricted information has been entered.

### 5. Submit the assessment

Submit your answers to generate the available score, findings and recommendations.

Do not close the page while the result is being generated. If the assessment does not complete, keep your non-sensitive answers available and try again after checking your connection.

## Understand your results

Treat the result as decision support, not as an automatic approval or compliance decision.

Review:

- the overall score in context;
- category-level results;
- critical or high-priority findings;
- controls that are documented but not enforced;
- resilience assumptions that have not been tested;
- recommendations that depend on facts the assessment cannot verify directly.

A strong overall score does not cancel a serious finding in an individual category.

## Turn recommendations into actions

For each important recommendation:

1. Confirm that the assessment answer was accurate.
2. Compare the finding with the live configuration and internal evidence.
3. Ask the appropriate technical, security or compliance owner to review it.
4. Record whether the action is accepted, rejected or deferred.
5. Assign an owner and target date to accepted actions.

Generated recommendations must be reviewed and tested before they are used in a production environment.

## Save or export your result

Saving and export options vary by assessment and membership. If an export control is locked, follow the on-screen membership guidance.

Do not assume that a result has been saved unless the interface confirms it. If you completed a public assessment and want to continue in the dashboard, create an account when prompted.

## Troubleshooting

### The assessment asks me to sign in

Some assessments and dashboard features require an account or membership. Sign in with the account connected to your SyncYourCloud access.

### I cannot export the result

Export availability varies by tool and membership. Check whether the export control is locked and follow the access information shown on screen.

### The result does not match my environment

Review your answers for planned controls, untested processes or information taken from different environments. Complete the assessment again using the current state of one clearly defined system.

### I am unsure whether a recommendation is safe

Do not implement it automatically. Ask an authorised engineering, security, architecture or compliance professional to review the recommendation against the live environment.

## Important limitations

SyncYourCloud assessment results support analysis and planning. They do not:

- deploy or change cloud infrastructure;
- access or inspect your AWS account automatically;
- move money or process payments;
- certify PCI DSS compliance;
- replace an authorised security, compliance or architecture review.

Always validate important findings against the live system and your organisation’s evidence.
