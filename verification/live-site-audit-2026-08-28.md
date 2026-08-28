# Live Site Verification Report

## Document control

| Field | Value |
|---|---|
| Product | SyncYourCloud |
| Test date | 28 August 2026 |
| Tester | Leesha Chudasama |
| Environment | Public production website |
| Browser | Safari, Private Browsing mode |
| Related issue | #1 |
| Status | In progress |

## Purpose

This report compares the published SyncYourCloud documentation with the
deployed product. It records expected behaviour, actual behaviour and any
documentation or product inconsistencies found during testing.

The audit uses public information and fictional test data only. It does not
include credentials, authentication tokens, customer information or private
infrastructure identifiers.

## Result definitions

- **Pass:** Actual behaviour matches the documented or expected behaviour.
- **Fail:** Actual behaviour conflicts with the documentation or expected behaviour.
- **Blocked:** The check could not be completed.
- **Pending:** The check has not yet been performed.

## Verification summary

| ID | Area | Expected result | Actual result | Status | Evidence |
|---|---|---|---|---|---|
| SYC-001 | Homepage assessment count | Homepage consistently describes 26 assessments | Three references to 25 modules and two references to 26 assessments were found | Fail | Screenshots captured on 28 August 2026 |
| SYC-002 | Infrastructure Readiness route | Route displays the free Infrastructure Readiness Assessment without requiring sign-in | Correct assessment displayed and question 1 of 21 opened without authentication | Pass | Landing-page and assessment screenshots captured on 28 August 2026 |
| SYC-003 | PCI DSS Gap Analysis route | Free PCI DSS assessment starts without sign-in | Landing page promises no-sign-in access, but the primary button opens a paid membership and sign-in page | Fail | Landing-page and membership-page screenshots captured on 28 August 2026 |
| SYC-004 | Published product copy | Pages contain finished customer-facing content only | Not yet tested | Pending | — |
| SYC-005 | Protected dashboard | Unauthenticated users cannot access protected content | Not yet tested | Pending | — |
| SYC-006 | Public assessment | Expected public assessment can be started without authentication | Not yet tested | Pending | — |

## Detailed test records

### SYC-001: Homepage assessment count


**URL:** https://www.syncyourcloud.io/

**Procedure**

1. Open the homepage in a private browser window.
2. Search the page for every statement describing the number of assessments or modules.
3. Record each number and the section in which it appears.
4. Compare the statements for consistency.

**Expected result**

The homepage consistently describes the product suite as containing 26 assessments.

**Actual result**

The homepage uses two different product totals and two different terms.

A browser text search found:

- Three references to “25 modules”.
- Two references to “26 assessments”.
- No references to 17.
- No references to “tools”.

“Assessments” is the current intended customer-facing term and has replaced “tools”. The references to “25 modules” are outdated copy.

**Status:** Fail

**Evidence:** Homepage screenshots captured on 28 August 2026 show three references to 25 modules and two references to 26 assessments.

**Required action:** Replace the three outdated references to “25 modules” with “26 assessments”. Review the updated homepage to confirm that the count and terminology are consistent throughout.

---

### SYC-002: Infrastructure Readiness route

**URL:** https://www.syncyourcloud.io/tools/infra-readiness

**Procedure**

1. Open the URL in a Safari Private Browsing window.
2. Record the main heading and assessment description.
3. Confirm that the page presents an infrastructure-readiness assessment.
4. Start the assessment using the primary call to action.
5. Confirm that the first assessment question loads.
6. Record whether authentication is required.

**Expected result**

The route displays the Infrastructure Readiness Assessment and opens its associated journey.

**Actual result**

The route displayed the “Payment Sync Score” Infrastructure Readiness Check.

The landing page described a free public assessment containing 21 questions across seven infrastructure layers:

- Agent orchestration
- Security and encryption
- Compliance and audit
- Cost optimisation
- Observability and monitoring
- Payment gateway integration
- Disaster recovery

Starting the assessment successfully opened question 1 of 21. No sign-in was requested, which matches the intended behaviour for this free public assessment.

**Status:** Pass

**Evidence:** Two screenshots captured on 28 August 2026 show the Infrastructure Readiness landing page and question 1 of the free public assessment.

**Required action:** No correction is required. Retain this test as regression evidence for future route or assessment changes.
**Status:** Pass

**Evidence:** Two screenshots captured on 28 August 2026 show the Infrastructure Readiness landing page and question 1 of the associated assessment.

**Required action:** No immediate product or documentation correction is required. Retain this test as regression evidence for future route or assessment changes.

---

---

### SYC-003: PCI DSS Gap Analysis route

**URL:** https://www.syncyourcloud.io/tools/pci-gap-analysis

**Procedure**

1. Open the URL in a Safari Private Browsing window.
2. Confirm that the landing page describes the PCI DSS Gap Analysis.
3. Record the access statements displayed on the landing page.
4. Select the primary “Try It Free – No Sign-in” call to action.
5. Confirm whether the assessment opens without authentication or payment.
6. Record the resulting page and access requirements.

**Expected result**

The route displays the PCI DSS Gap Analysis and allows users to start the free assessment without signing in.

**Actual result**

The PCI DSS Gap Analysis landing page loaded successfully and described the assessment as free and accessible without signing in.

The page displayed the following access statements:

- “FREE – NO SIGN-IN REQUIRED”
- “Free, 15 minutes, no account needed”
- “Try It Free – No Sign-in”

After selecting “Try It Free – No Sign-in”, the user was taken to a membership page instead of the assessment.

The resulting page asked existing members to sign in. New users were instructed to sign up and pay to activate membership. The PCI DSS assessment could not be started anonymously as promised on the landing page.

**Status:** Fail

**Evidence:** Two screenshots captured on 28 August 2026 show the no-sign-in promise on the PCI DSS Gap Analysis landing page and the membership page displayed after selecting the primary call to action.

**Required action:** Decide whether the PCI DSS Gap Analysis is a free public assessment or a members-only assessment. If it is public, correct the call-to-action destination so the assessment opens without authentication. If membership is required, remove the “free” and “no sign-in” claims and clearly explain the access and payment requirements before the user selects the button.

---

---

### SYC-004: Published product copy

**URLs tested:** To be added during testing.

**Procedure**

1. Review the homepage and assessment landing pages.
2. Look for internal instructions, drafting notes and placeholder text.
3. Check that customer-facing claims are clear and supportable.
4. Record the exact location of any issue without reproducing sensitive data.

**Expected result**

Published pages contain completed customer-facing content only.

**Actual result**

Pending manual verification.

**Status:** Pending

**Evidence:** Not yet captured.

**Required action:** To be determined after testing.

---

### SYC-005: Protected dashboard

**URL:** Add the protected dashboard URL.

**Procedure**

1. Sign out of SyncYourCloud.
2. Open a private browser window.
3. Attempt to open the protected dashboard directly.
4. Record whether the application redirects to sign-in or exposes content.
5. Do not record authentication tokens or private user information.

**Expected result**

An unauthenticated user is redirected to authentication and cannot access
protected account content.

**Actual result**

Pending manual verification.

**Status:** Pending

**Evidence:** Not yet captured.

**Required action:** To be determined after testing.

---

### SYC-006: Public assessment access

**URL:** Add the assessment URL tested.

**Procedure**

1. Open the assessment in a private browser window.
2. Confirm whether authentication is required.
3. Start the journey using fictional information.
4. Record validation behaviour and the first successful step.
5. Stop before submitting any information that should not enter production.

**Expected result**

The documented public assessment can be started without authentication.

**Actual result**

Pending manual verification.

**Status:** Pending

**Evidence:** Not yet captured.

**Required action:** To be determined after testing.

## Findings
### Finding 1: Outdated assessment count and terminology

SyncYourCloud now uses “assessments” as its customer-facing term. The current suite contains 26 assessments.

The homepage correctly refers to 26 assessments in two places but retains three outdated references to 25 modules. These legacy references create an inconsistent product count and naming convention.

The three references to “25 modules” should be replaced with “26 assessments”.

### Finding 2: PCI DSS access promise conflicts with the user journey

The PCI DSS Gap Analysis landing page repeatedly states that the assessment is free and requires no sign-in. Its primary “Try It Free – No Sign-in” button instead opens a membership page that asks existing users to sign in and new users to register and pay.

This prevents users from accessing the assessment under the conditions advertised on the landing page. The product owner must confirm the intended access model before the copy or routing is corrected.

**Priority:** High

**Affected journey:** PCI DSS Gap Analysis acquisition and onboarding

**Recommended resolution:** Either provide direct anonymous access to the assessment or replace the free-access claims with accurate membership and payment information.



## Documentation changes required

To be determined after testing.

## Product changes required

To be determined after testing.

## Security and privacy notes

- Use fictional test information only.
- Do not commit passwords, API keys or authentication tokens.
- Do not expose Firebase, Stripe or AWS secrets.
- Do not include customer or payment information.
- Review screenshots for personal information before committing them.

## Completion criteria

- [ ] All six checks have been performed.
- [ ] Every check has a dated actual result.
- [ ] Pass, fail, blocked or pending status is recorded accurately.
- [ ] Evidence is referenced where appropriate.
- [ ] Documentation corrections are committed separately.
- [ ] Product defects are recorded without being disguised as documentation fixes.
- [ ] Issue #1 is updated with the audit results.
