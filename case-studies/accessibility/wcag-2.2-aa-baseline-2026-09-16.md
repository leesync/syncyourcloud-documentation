# SyncYourCloud WCAG 2.2 Level AA Accessibility Baseline

**Audit date:** 16 September 2026  
**Target:** <https://www.syncyourcloud.io/>  
**Standard:** WCAG 2.2, conformance target Level AA  
**Status:** Baseline findings recorded; conformance **not yet established**

## Executive outcome

This review creates an evidence-led starting point for bringing SyncYourCloud into alignment with WCAG 2.2 Level AA. The live site already exposes useful semantic structure in several areas, including a declared English language, descriptive page titles, a single visible H1 on the homepage and PCI landing page, meaningful image alternative text, and visible keyboard focus on many interactive controls.

The current evidence does **not** support a claim that the site conforms to WCAG 2.2 AA. The highest-priority issues affect navigation and forms: a keyboard-focusable mobile-menu control has no programmatic role or accessible name; sign-in and registration fields have visible labels that are not programmatically associated with the inputs; tested pages have no `main` landmark; the authentication page has no H1; and the newsletter field relies on placeholder text instead of a persistent programmatic label.

The PCI tool journey also promises “No Sign-in Required” and “Try It Free - No Sign-in” but the tested call to action redirected to `/auth`. This is primarily a product-content and journey defect rather than proof of a single WCAG failure, but it creates avoidable cognitive friction and must be resolved or accurately explained before accessibility acceptance.

## Scope and method

### Pages tested

| Page | Final URL | Tested state |
|---|---|---|
| Homepage | `https://www.syncyourcloud.io/` | Initial public view and keyboard sequence |
| PCI DSS Gap Analysis landing page | `https://www.syncyourcloud.io/tools/pci-gap-analysis` | Initial public view and primary CTA |
| Authentication | `https://www.syncyourcloud.io/auth` | Public sign-in and registration forms |

### Evidence method

- Inspected the live rendered DOM and accessibility representation.
- Inspected headings, landmarks, forms, labels, names, roles, target dimensions and live regions.
- Followed the primary PCI gap-analysis call to action.
- Traversed a representative keyboard sequence and inspected visible focus styles.
- Separated verified findings from items requiring manual or assistive-technology testing.

Automated inspection can identify many objective defects, but it cannot establish WCAG conformance on its own. Screen-reader behaviour, zoom/reflow, contrast over gradients, error recovery, focus order across complete journeys and cognitive usability still require manual testing.

## Verified strengths

| Evidence | Relevant WCAG area | Result |
|---|---|---|
| The document language is declared as English on all three tested pages. | 3.1.1 Language of Page | **Verified pass in tested sample** |
| Homepage and PCI landing page have descriptive page titles and one visible H1. | 2.4.2 Page Titled; 1.3.1 structure | **Verified pass in tested sample** |
| Visible homepage images inspected have meaningful `alt` text. | 1.1.1 Non-text Content | **Verified pass in tested sample** |
| Many links and buttons display a visible focus outline during keyboard traversal. | 2.4.7 Focus Visible | **Partially verified** |
| No duplicate IDs were detected on the homepage sample. | 4.1.1 Parsing (obsolete in WCAG 2.2, but still useful code quality evidence) | **Observed quality signal** |

## Prioritised findings

### SYC-A11Y-001 — Mobile-menu control lacks an accessible name and role

**Severity:** Critical  
**Verified evidence:** The live header contains a focusable `div.hamburger-menu-icon` with `tabindex="0"`. It has no accessible name and no button role. It receives visible keyboard focus, but its purpose is not exposed in the accessibility representation.

**Affected criteria:**

- 4.1.2 Name, Role, Value (Level A)
- 2.1.1 Keyboard (Level A) — activation with both Enter and Space still needs verification
- 2.5.3 Label in Name (Level A), if a visible label is later introduced

**User impact:** A screen-reader user encounters an unnamed focus target and cannot determine that it opens the navigation. Keyboard users may be unable to activate it consistently if click handling is implemented only for a pointer.

**Required remediation:** Use a native button and expose its state and controlled menu.

```html
<button
  type="button"
  class="hamburger-menu-icon"
  aria-label="Open navigation menu"
  aria-expanded="false"
  aria-controls="primary-navigation-menu"
>
  <!-- decorative icon -->
</button>
```

Update `aria-expanded` and the accessible label when the menu opens. Confirm that Enter and Space activate the button, Escape closes the menu, and focus moves predictably.

### SYC-A11Y-002 — Authentication inputs have no programmatically associated labels

**Severity:** Critical  
**Verified evidence:** Sign-in fields for email and password, and registration fields for display name, email, password and confirm password, have no `id`, no `aria-label`, no `aria-labelledby`, and no associated labels in the rendered DOM. Visible text labels exist but are not connected to the fields.

**Affected criteria:**

- 1.3.1 Info and Relationships (Level A)
- 3.3.2 Labels or Instructions (Level A)
- 4.1.2 Name, Role, Value (Level A)
- 1.3.5 Identify Input Purpose (Level AA), because autocomplete purposes are also absent

**User impact:** Screen-reader and voice-control users may hear generic “textbox” controls without knowing which value is required. Password managers and browser autofill have less reliable purpose information.

**Required remediation:** Give every field a stable ID, associate a visible label, and add the correct autocomplete token.

```html
<label for="signin-email">Email</label>
<input id="signin-email" name="email" type="email" autocomplete="email" required>

<label for="signin-password">Password</label>
<input id="signin-password" name="password" type="password" autocomplete="current-password" required>
```

Use `name`, `email`, `new-password` and `current-password` tokens as appropriate. Keep the visible label; do not replace it with placeholder-only instructions.

### SYC-A11Y-003 — Newsletter email field lacks a persistent programmatic label

**Severity:** High  
**Verified evidence:** The newsletter input on tested pages has no associated label or ARIA name. On the authentication page it exposes only the placeholder “Email”; on the homepage sample it had no accessible name in the inspected control data.

**Affected criteria:** 1.3.1, 3.3.2 and 4.1.2 (all Level A)

**User impact:** Placeholder text disappears after entry and is not a reliable label. Assistive-technology users may not know that the field subscribes them to a newsletter rather than signs them in.

**Required remediation:** Add a visible or visually hidden label such as “Email address for newsletter” and give the submit button a descriptive name such as “Subscribe to newsletter” rather than only an arrow.

### SYC-A11Y-004 — Tested pages have no `main` landmark or skip link

**Severity:** High  
**Verified evidence:** The homepage, PCI landing page and authentication page expose header/navigation and footer landmarks, but no `main` element was detected. No skip-to-content link was found in the initial keyboard order.

**Affected criteria:**

- 1.3.1 Info and Relationships (Level A)
- 2.4.1 Bypass Blocks (Level A)

**User impact:** Keyboard and screen-reader users must repeatedly traverse site-wide navigation before reaching page content and cannot jump directly to the principal region.

**Required remediation:** Wrap each route’s unique content in one `<main id="main-content">` and add a first-focusable skip link targeting it.

### SYC-A11Y-005 — Authentication page has no level-one heading

**Severity:** Medium  
**Verified evidence:** `/auth` has H2 headings (“Already a Member?” and “Not a Member”) but no H1.

**Affected criterion:** 1.3.1 Info and Relationships (Level A); also affects navigation and comprehension even though WCAG does not require an H1 literally.

**User impact:** The page’s primary purpose is less clear to users navigating by headings.

**Required remediation:** Add a concise H1 such as “Sign in or create your SyncYourCloud account,” then retain the two H2 headings as subsections.

### SYC-A11Y-006 — “No sign-in” promise redirects to authentication

**Severity:** High product-journey defect  
**Verified evidence:** On 16 September 2026, the public PCI page displayed “Free - No Sign-in Required” and buttons labelled “Try It Free - No Sign-in.” Activating the first primary button redirected to `https://www.syncyourcloud.io/auth`, whose copy asks the user to sign in or create a paid membership account.

**WCAG relationship:** This evidence does not, by itself, prove failure of one success criterion. It may contribute to failures involving instructions, predictable behaviour or error prevention depending on the intended workflow and later states. It is recorded separately to avoid overstating the standard.

**User impact:** Users may abandon the assessment, distrust the promise, or be unable to distinguish free anonymous assessment entry from report retrieval and membership access.

**Required remediation:** Choose and implement one truthful journey:

1. allow the assessment to start anonymously and request authentication only when saving or retrieving a report; or
2. change every CTA and supporting sentence to state exactly when and why an account is required.

Retest both pointer and keyboard activation after deployment.

### SYC-A11Y-007 — Small controls and contrast require focused manual verification

**Severity:** Needs verification  
**Evidence:** The homepage range control rendered at approximately 518 × 14 CSS pixels, and several footer links rendered with a 21-pixel text-line height. Initial computed-style sampling also flagged green and muted text as possible contrast risks, but gradients, transparency and ancestor backgrounds make those automated ratios insufficient as proof.

**Potential criteria:**

- 1.4.3 Contrast (Minimum) (Level AA)
- 1.4.11 Non-text Contrast (Level AA)
- 2.5.8 Target Size (Minimum) (Level AA)

**Required verification:** Measure final rendered foreground/background pairs with an approved contrast tool, inspect focus indicators in every component state, and apply the 24 × 24 CSS pixel rule together with its spacing and essential exceptions.

## Acceptance tests for remediation

| Test | Expected result | Evidence to retain |
|---|---|---|
| Keyboard-only navigation | Every interactive element is reachable and operable using Tab, Shift+Tab, Enter, Space and Escape as applicable. | Dated test record, route, browser and pass/fail per control |
| Screen reader | NVDA/Firefox or NVDA/Chrome announces page title, H1, landmarks, menu name/state, form labels, requirements and errors accurately. | Dated transcript or short recording and issue references |
| Forms and errors | Labels remain visible; instructions precede input; errors are text-based, field-linked and announced; focus moves predictably. | Test cases for empty, invalid and successful submission |
| Zoom and reflow | At 200% zoom and 320 CSS-pixel width, content reflows without loss, overlap or two-dimensional scrolling except permitted content. | Screenshots plus browser/viewport data |
| Contrast | Normal text is at least 4.5:1; large text at least 3:1; essential component and focus boundaries at least 3:1. | Saved analyser output with sampled colours and component state |
| Target size | Pointer targets meet 24 × 24 CSS pixels or a documented WCAG exception. | DOM measurement record and exception rationale |
| Assessment journey | Public promise matches actual access; question progress, validation, results, save/retrieve and recovery states are understandable and accessible. | End-to-end scenario matrix |

## Evidence register

| Evidence ID | Observation | Status |
|---|---|---|
| E-001 | Homepage live DOM, headings, controls, forms, images, landmarks and IDs inspected on 16 September 2026. | Verified observation |
| E-002 | PCI landing page live DOM and primary CTA inspected on 16 September 2026. | Verified observation |
| E-003 | Primary “Try It Free - No Sign-in” CTA redirected to `/auth`. | Verified observation |
| E-004 | Authentication forms expose six required inputs without associated labels or autocomplete tokens. | Verified observation |
| E-005 | Representative homepage keyboard traversal showed visible focus outlines on multiple links/buttons. | Partial pass; full-site traversal needed |
| E-006 | Screen-reader, zoom/reflow, contrast-over-gradient, error-handling and complete assessment-state tests. | **Needs verification** |

## Definition of done

Do not publish “WCAG 2.2 AA compliant” until all of the following are true:

- Every applicable Level A and AA success criterion has a dated result for each representative page template and critical state.
- Every failure has been fixed and retested, or a valid WCAG exception is documented.
- Keyboard, screen-reader, zoom/reflow, contrast, forms/errors and authentication have been manually tested.
- The anonymous assessment, save/retrieve, reassessment, export and failure-recovery journeys have been verified in the deployed environment.
- An accessibility statement accurately describes the tested scope, known limitations, contact route and review date.
- An independent technical or accessibility review has been completed, or is explicitly labelled **Needs verification**.

## Recommended implementation order

1. Replace the hamburger `div` with a named native button and verify keyboard behaviour.
2. Associate all authentication and newsletter labels; add autocomplete tokens and descriptive submit names.
3. Add a skip link and one `main` landmark per route.
4. Add the authentication-page H1 and review heading structure across remaining templates.
5. Resolve the anonymous-versus-authenticated PCI journey and align all CTA copy.
6. Run manual contrast, reflow, target-size, screen-reader and form-error testing.
7. Audit the remaining public pages and every assessment state before making a conformance claim.

## Source standard

- W3C, *Web Content Accessibility Guidelines (WCAG) 2.2*: <https://www.w3.org/TR/WCAG22/>
- W3C WAI, *Evaluating Web Accessibility Overview*: <https://www.w3.org/WAI/test-evaluate/>

