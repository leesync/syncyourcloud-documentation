# Complete an infrastructure readiness assessment

This tutorial shows how to complete a SyncYourCloud infrastructure readiness assessment and interpret its result.

## Before you begin

Prepare high-level information about the environment you want to assess, including:

- cloud provider and primary region;
- approximate transaction or workload volume;
- key services in the architecture;
- resilience and disaster-recovery arrangements;
- monitoring, security and compliance controls;
- known operational problems.

Do not enter cardholder data, credentials, private keys, access tokens or production secrets.

## 1. Open the assessment

Use either the public Infrastructure Readiness tool or the authenticated dashboard route.

The public route is intended for a quick assessment. The dashboard route provides the signed-in product experience and may expose additional membership features.

## 2. Describe the environment

Answer each question using the current state of the system, not the target state. If a control exists only in a document but is not enforced or tested, select the answer that reflects the implemented control.

For example, a disaster-recovery plan that has not been exercised is different from a tested failover process with measured recovery time and recovery point objectives.

## 3. Submit the assessment

After the final question, submit the assessment to generate a result. The documented build calculates assessment output in the application and presents a scorecard with findings and recommendations.

If the configured remote assessment service is unavailable, the application can fall back to bundled assessment definitions. This fallback prevents the questionnaire from becoming unusable, but it does not prove that a remote service completed the analysis.

## 4. Review the score

Read the overall score together with the category breakdown. A single score is a summary, not a compliance decision.

Pay particular attention to:

- red or critical findings;
- controls that are documented but not enforced;
- resilience assumptions that have not been tested;
- missing operational evidence;
- recommendations that depend on facts the assessment cannot observe directly.

## 5. Validate the recommendations

Before acting on a recommendation:

1. Confirm that the input was accurate.
2. Compare the finding with the live AWS configuration and internal records.
3. Ask the responsible engineering, security or compliance owner to review it.
4. Record accepted, rejected and deferred actions with an owner and target date.

## 6. Save or export the result

Export availability depends on the tool and membership tier. When export is locked, the application sends the user to the membership page instead of generating a file.

If you use a public tool, create an account when prompted if you want to continue in the dashboard. Do not assume that a browser result has been saved unless the interface confirms it.

## Expected result

You should finish with a structured decision-support artefact: a score, a set of findings and a prioritised list of actions. The result remains subject to technical and professional review.

