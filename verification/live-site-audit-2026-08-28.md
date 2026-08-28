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
| SYC-004 | Published product copy | Pages contain finished customer-facing content only | Internal instructions, inconsistent terminology, mismatched navigation and contradictory access claims were found | Fail — remediation in progress | Screenshots and product-code pull request #18 |
| SYC-005 | Protected dashboard | Unauthenticated users cannot access protected content | Protected URL redirected to sign-in and exposed no dashboard data | Pass | Authentication redirect screenshot captured on 28 August 2026 |
| SYC-006 | Public assessment access | Free Infrastructure Readiness Check starts without authentication | Question 1 of 21 opened in Safari Private Browsing without registration, authentication or payment | Pass | Landing-page and first-question screenshots captured on 28 August 2026 |
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

**URLs tested:**

- https://www.syncyourcloud.io/
- https://www.syncyourcloud.io/tools/infra-readiness
- https://www.syncyourcloud.io/tools/pci-gap-analysis

**Procedure**

1. Review the homepage and assessment landing pages.
2. Search for internal instructions, drafting notes and placeholder text.
3. Check that product counts and terminology are consistent.
4. Compare button labels with their destinations.
5. Check that access claims match the actual user journey.
6. Record confirmed issues using public information only.

**Expected result**

Published pages contain finished customer-facing content only. Product terminology, access claims and navigation labels accurately describe the associated content and journeys.

**Actual result**

The audit identified four content problems:

1. The homepage used both “25 modules” and “26 assessments”.
2. “See all 26 assessments” did not display a catalogue of all 26 assessments.
3. The “How It Works” section exposed internal editorial instructions about animations, visuals, framing and messaging.
4. The PCI DSS Gap Analysis page promised free, no-sign-in access but directed users to authentication and paid membership.

**Status:** Fail — remediation and retesting in progress

**Evidence:** Screenshots captured on 28 August 2026 show the conflicting assessment count, mismatched navigation, internal editorial instructions and contradictory PCI DSS access journey.

**Remediation completed in source control:**

The public-facing product-tour copy was rewritten in `ProductTour.jsx`. The correction replaced internal editorial instructions with customer-focused explanations of assessment inputs, findings, decision support and remediation planning.

The change was managed through:

- Branch: `fix/product-tour-customer-copy`
- Commits:
  - `fix: replace internal product tour copy`
  - `fix: remove duplicate product tour copy`
- Pull request: [Replace internal product-tour instructions with customer-facing copy](https://github.com/leesync/dashboard-webtools/pull/18)
- Files changed: One
- Merge target: `main`

**Retest status:** Pending completion of the AWS Amplify deployment.

**Remaining actions:**

- Verify the corrected product-tour copy after deployment.
- Replace “25 modules” with “26 assessments”.
- Correct or rename “See all 26 assessments”.
- Resolve the PCI DSS free-access and membership contradiction.
- Repeat SYC-004 after every correction is deployed.

---

### SYC-005: Protected dashboard access

**Protected URL tested:** Add the exact dashboard URL copied from the authenticated session.

**Procedure**

1. Sign in to SyncYourCloud and open the protected dashboard.
2. Copy the exact dashboard URL.
3. Sign out of the application.
4. Open a Safari Private Browsing window.
5. Open the protected dashboard URL directly.
6. Record the resulting URL and page.
7. Confirm whether any account or dashboard information is exposed.

**Expected result**

An unauthenticated user is redirected to authentication and cannot access protected account or dashboard content.

**Actual result**

A signed-in user could access the SyncYourCloud dashboard and its onboarding journey.

When the same protected URL was opened without an authenticated session, the application displayed the SyncYourCloud sign-in page. No dashboard, membership, assessment, report or account content was exposed.

**Status:** Pass

**Evidence:** A screenshot captured on 28 August 2026 shows the authentication page displayed after an unauthenticated attempt to open the protected route.

**Required action:** No immediate correction is required. Retain this test as regression evidence for future authentication or routing changes.

---

---

### SYC-006: Public assessment access

**URL:** https://www.syncyourcloud.io/tools/infra-readiness

**Procedure**

1. Open the assessment landing page in a Safari Private Browsing window.
2. Confirm that no authenticated session exists.
3. Start the Infrastructure Readiness Check.
4. Confirm that the first assessment question loads.
5. Record whether registration, authentication or payment is required.
6. Stop before submitting unnecessary production data.

**Expected result**

The documented free Infrastructure Readiness Check can be started without authentication or payment.

**Actual result**

The public Infrastructure Readiness landing page loaded successfully in Safari Private Browsing mode.

Starting the assessment opened question 1 of 21. The assessment did not request registration, authentication, membership activation or payment before displaying the first question.

This matches the intended access model for the free public assessment.

**Status:** Pass

**Evidence:** Screenshots captured on 28 August 2026 show the public Infrastructure Readiness landing page and question 1 of 21 displayed without authentication.

**Required action:** No immediate correction is required. Retain this test as regression evidence for future access-control or routing changes.
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

### Finding 3: Internal editorial instructions were publicly visible

The homepage product tour contained instructions about retaining animations, changing framing and repositioning messages. This copy addressed the page editor rather than the customer.

**Priority:** High

**Remediation:** Replaced the internal instructions with customer-facing explanations through product-code pull request #18.

**Verification:** Pending deployment and production retest.

### Finding 4: Assessment navigation does not match its label

The “See all 26 assessments” control does not present a catalogue of all 26 assessments.

**Priority:** Medium

**Remediation:** Pending confirmation of the intended destination.


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
