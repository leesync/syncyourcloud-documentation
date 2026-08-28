# Live Site Verification Report

## Document control

| Field | Value |
|---|---|
| Product | SyncYourCloud |
| Test date | 28 August 2026 |
| Tester | Leesha Chudasama |
| Environment | Public production website |
| Browser | Add browser and version |
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
| SYC-001 | Homepage tool count | One consistent tool total is used | Not yet tested | Pending | — |
| SYC-002 | Infrastructure Readiness route | Route displays the Infrastructure Readiness Assessment | Not yet tested | Pending | — |
| SYC-003 | PCI DSS Gap Analysis route | Route displays the PCI DSS Gap Analysis | Not yet tested | Pending | — |
| SYC-004 | Published product copy | Pages contain finished customer-facing content only | Not yet tested | Pending | — |
| SYC-005 | Protected dashboard | Unauthenticated users cannot access protected content | Not yet tested | Pending | — |
| SYC-006 | Public assessment | Expected public assessment can be started without authentication | Not yet tested | Pending | — |

## Detailed test records

### SYC-001: Homepage tool count

**URL:** https://www.syncyourcloud.io/

**Procedure**

1. Open the homepage in a private browser window.
2. Search the page for every statement describing the number of tools.
3. Record each number and the section in which it appears.
4. Compare the statements for consistency.

**Expected result**

The homepage uses one accurate and consistent tool total.

**Actual result**

Pending manual verification.

**Status:** Pending

**Evidence:** Not yet captured.

**Required action:** To be determined after testing.

---

### SYC-002: Infrastructure Readiness route

**URL:** https://www.syncyourcloud.io/tools/infra-readiness

**Procedure**

1. Open the URL in a private browser window.
2. Record the page title and primary heading.
3. Record the assessment or tool presented.
4. Compare the route name with the displayed content.
5. Test whether the primary call-to-action opens the expected journey.

**Expected result**

The route displays the Infrastructure Readiness Assessment and its associated
journey.

**Actual result**

Pending manual verification.

**Status:** Pending

**Evidence:** Not yet captured.

**Required action:** To be determined after testing.

---

### SYC-003: PCI DSS Gap Analysis route

**URL:** https://www.syncyourcloud.io/tools/pci-gap-analysis

**Procedure**

1. Open the URL in a private browser window.
2. Record the page title and primary heading.
3. Confirm that the page describes the PCI DSS Gap Analysis.
4. Test the primary call-to-action.
5. Record whether authentication is required.

**Expected result**

The route displays the PCI DSS Gap Analysis and opens the correct assessment
journey.

**Actual result**

Pending manual verification.

**Status:** Pending

**Evidence:** Not yet captured.

**Required action:** To be determined after testing.

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

No findings have been confirmed yet. This section will be updated after the
manual checks are completed.

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
