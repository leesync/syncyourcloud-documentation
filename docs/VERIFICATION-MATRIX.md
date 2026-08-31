# Assessment documentation verification matrix

This internal matrix records whether customer-facing documentation statements have been checked against the current SyncYourCloud product.

Use these statuses consistently:

- **Verified** — observed directly in the current product and recorded with a date.
- **Partially verified** — part of the documented behaviour was observed; remaining steps still require testing.
- **Needs testing** — the statement is plausible but has not been observed through the complete user journey.
- **Blocked** — contradictory product behaviour or copy prevents an accurate instruction.
- **Editorial review** — the statement is guidance rather than interface behaviour and requires an accountable owner to approve it.

Do not publish a claim marked **Needs testing** or **Blocked** as confirmed product behaviour.

## Product-wide terminology and access

| ID | Claim or control | Documentation affected | Test method | Status | Evidence | Required action |
|---|---|---|---|---|---|---|
| PRD-001 | The product name is **Infrastructure Readiness Check**. | All pages | Compare the assessment entry page, questionnaire and result page. | Verified | Observed signed out, 30 August 2026. | Recheck after product copy changes. |
| PRD-002 | The assessment contains 21 questions. | Tutorial, reference | Complete or inspect the full questionnaire. | Verified | Final question and **View My Results** observed, 30 August 2026. | Recheck if the assessment definition changes. |
| PRD-003 | Questions are organised into seven named layers. | Tutorial, result review, reference, terminology | Compare questionnaire and result labels. | Verified | Seven layers observed, 30 August 2026. | Confirm spelling and capitalisation during release review. |
| PRD-004 | The overall result is named **Payment Sync Score**. | Tutorial, result review, score explanation, terminology | Generate a result and compare the heading. | Verified | Results page observed, 30 August 2026. | Preserve exact interface capitalisation. |
| PRD-005 | The result contains **Layer Breakdown** and **Recommendations**. | Tutorial, result review, reference | Generate a result and inspect all result sections. | Verified | Results page observed, 30 August 2026. | Recheck after result-page changes. |
| PRD-006 | The Infrastructure Readiness Check can be completed and initially viewed without signing in. | README, tutorial, choose assessment, save result, troubleshooting, reference | Start signed out, complete all questions and view the result. | Verified | Signed-out result journey observed, 30 August 2026. | Retest in a private browser window before publication. |
| PRD-007 | Saving a result requires authentication. | Tutorial, save result, troubleshooting, reference | Select **Save My Results** while signed out. | Partially verified | **Save My Results** and **Sign in** led to account access, 30 August 2026. | Complete save flow with a clean test account and confirm persistence. |
| PRD-008 | **Retake Assessment** starts a new assessment safely. | Reassess environment, troubleshooting | Generate a result, select the control and observe state/reset behaviour. | Needs testing | Control was present on 30 August 2026; complete reset behaviour was not recorded. | Test whether answers, result and saved state are retained or reset. |
| PRD-009 | Acquirer Readiness requires Scope membership or above. | Choose assessment, reference | Inspect entry page and test with signed-out and clean-account states. | Partially verified | Entry page displayed `Scope & above`, 30 August 2026. | Confirm actual enforcement with an ineligible clean account. |
| PRD-010 | Acquirer Readiness export requires Sync membership or above. | Choose assessment, reference, troubleshooting | Inspect entry page and attempt export with each relevant entitlement. | Partially verified | Entry page displayed `Export: Sync+`, 30 August 2026. | Verify the locked and eligible export journeys. |
| PRD-011 | PCI DSS Gap Analysis is available without sign-in. | Choose assessment, reference, troubleshooting | Start from the entry page while signed out and attempt the assessment. | Blocked | Entry page claimed no sign-in, but the control redirected to authentication, 30 August 2026. | Align product access and product copy before publishing this claim. |

## Tutorial verification

| ID | Procedure or statement | Test method | Status | Evidence | Required action |
|---|---|---|---|---|---|
| TUT-001 | The assessment opens from the assessment tools. | Follow the public navigation from the website. | Verified | Public route reached while signed out, 30 August 2026. | Record the canonical URL before website publication. |
| TUT-002 | Selecting an answer enables **Next**. | Test at least one answer type on several questions. | Verified | Observed signed out, 30 August 2026. | Retest after questionnaire UI changes. |
| TUT-003 | **Back** is available after question one and preserves the earlier answer. | Move forward, return and inspect the selected answer. | Partially verified | **Back** was present, 30 August 2026; answer persistence was not recorded. | Verify answer persistence explicitly. |
| TUT-004 | Progress displays question number, completion percentage and answered count. | Compare progress at the start, middle and final question. | Verified | Observed signed out, 30 August 2026. | Confirm the percentage calculation at representative points. |
| TUT-005 | The final action is **View My Results**. | Complete question 21. | Verified | Observed signed out, 30 August 2026. | Recheck exact label before publication. |
| TUT-006 | The result shows score, layers at risk, layer points/percentages/status and recommendations. | Generate a result and record each component. | Partially verified | Score, Layer Breakdown and Recommendations observed; exact layers-at-risk wording needs a recorded check. | Capture a sanitised screenshot or test note for every component. |
| TUT-007 | **Save My Results** allows a signed-in user to keep the result. | Complete the flow with a clean account, sign out, return and locate the saved result. | Needs testing | Authentication redirect observed only. | Test persistence end to end before publication. |

## How-to and troubleshooting verification

| ID | Journey | Documentation page | Status | Required test |
|---|---|---|---|---|
| HOW-001 | Review score and layer results. | `how-to/review-infrastructure-result.md` | Partially verified | Confirm every displayed field, label and status value against a fresh result. |
| HOW-002 | Save and retrieve a result. | `how-to/save-assessment-result.md` | Needs testing | Use a clean account; save, leave the page, sign out, sign in and retrieve the same result. |
| HOW-003 | Retake an assessment. | `how-to/reassess-environment.md` | Needs testing | Record answer reset, result history and saved-result behaviour. |
| HOW-004 | Resolve sign-in requirements. | `how-to/troubleshoot-assessments.md` | Partially verified | Test protected and public tools from signed-out, free and eligible membership states. |
| HOW-005 | Recover from result-loading failure. | `how-to/troubleshoot-assessments.md` | Needs testing | Reproduce or simulate the supported failure state; confirm retry behaviour and whether answers persist. |
| HOW-006 | Resolve assessment allowance limits. | `how-to/troubleshoot-assessments.md` | Needs testing | Reach the allowance with a clean test account and record the exact message and available actions. |
| HOW-007 | Export a result. | `how-to/troubleshoot-assessments.md`, reference | Needs testing | Test locked and eligible export controls; verify file type, filename and contents. |
| HOW-008 | Contact support. | `how-to/troubleshoot-assessments.md` | Needs testing | Confirm the current support route and the non-sensitive information requested. |

## Editorial and professional review

| ID | Guidance | Documentation affected | Status | Reviewer required |
|---|---|---|---|---|
| EDT-001 | Recommendations are decision support and require validation. | Multiple pages | Editorial review | Product owner and appropriate technical/security/compliance reviewer. |
| EDT-002 | A score is not a compliance certification or automatic approval. | Result and reference pages | Editorial review | Product owner and compliance reviewer. |
| EDT-003 | Users must not submit cardholder data, credentials, tokens, keys, secrets or confidential identifiers. | Tutorial and data guidance | Editorial review | Security/privacy reviewer. |
| EDT-004 | Planned, documented, implemented and tested controls represent different assurance levels. | Explanation and tutorial pages | Editorial review | Architecture/security/compliance reviewer. |
| EDT-005 | Assessment outputs do not deploy infrastructure, inspect AWS automatically, move money or replace professional review. | Reference and explanation pages | Editorial review | Product owner and legal/compliance reviewer. |

## Release gate

The assessment documentation can move from release candidate to publishable only when:

1. Every customer-facing product claim is **Verified** or deliberately rewritten so it does not claim untested behaviour.
2. Every task procedure has been completed from its stated starting condition.
3. PCI DSS access copy and actual access behaviour agree.
4. Saved-result, reassessment and export journeys have been tested with suitable clean accounts.
5. All local links pass an automated check.
6. Examples and evidence contain no customer data, credentials, tokens, secrets or confidential infrastructure identifiers.
7. The accountable product, security and compliance reviewers have approved the relevant editorial guidance.

## Test record template

Copy this block for each new test session:

```text
Test ID:
Date and time:
Environment or product version:
Tester:
Starting state: signed out | clean account | existing account | eligible membership
Browser/device:
Steps completed:
Observed result:
Evidence location:
Status: pass | fail | blocked
Documentation pages affected:
Required documentation change:
```
