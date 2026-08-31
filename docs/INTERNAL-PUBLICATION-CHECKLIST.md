# Assessment help-centre publication checklist

This file is for editorial review and is not customer-facing.

Before publishing, verify every statement against the current website:

- assessment names and capitalisation;
- page titles and navigation paths;
- button and field labels;
- sign-in requirements;
- membership and assessment allowances;
- save, resume and export behaviour;
- exact result components and terminology;
- support route and information requested;
- behaviour when generation fails; and
- AWS connection wording.

## Live test record — 30 August 2026

Verified while signed out:

- **Infrastructure Readiness Check** opens directly.
- It contains 21 questions across seven named layers.
- An answer enables **Next**; **Back** is available after question one.
- Progress shows question number, percentage and answered count.
- The final control is **View My Results**.
- The results page shows **Payment Sync Score**, **Layer Breakdown** and **Recommendations**.
- **Save My Results** and **Sign in** lead to account access.
- **Retake Assessment** is present.
- **Acquirer Readiness** displays `Scope & above` and `Export: Sync+`.

Product copy requiring resolution before PCI DSS help content is published:

- The PCI DSS entry page says `Free - No Sign-in Required` and uses **Try It Free - No Sign-in**.
- Selecting that control redirects a signed-out user to the authentication page.
- The home page contains both `No account needed` and `Create a free account` claims for this assessment.

Run every tutorial and how-to procedure from a clean test account. Capture the observed result for each step and revise any instruction that depends on assumption rather than interface evidence.

Record individual claims, procedures and evidence in [VERIFICATION-MATRIX.md](VERIFICATION-MATRIX.md). The matrix is the release gate for customer-facing assessment documentation.

## Page verification status

| Page | Editorial status | Product verification |
|---|---|---|
| Assessment landing page | Ready for review | Navigation links checked locally |
| Complete your first assessment | Ready | Core signed-out journey verified 30 August 2026 |
| Choose an assessment | Ready for review | Access wording partially verified 30 August 2026 |
| Review an Infrastructure Readiness result | Ready | Result controls verified 30 August 2026 |
| Turn recommendations into actions | Ready | Advisory procedure; owner review required |
| Save an assessment result | Ready for testing | Test with a clean account before publication |
| Reassess an environment | Ready for testing | Start control verified; complete saved-result journey still required |
| Resolve assessment problems | Ready for testing | Test each supported recovery path |
| How assessments work | Ready for review | Confirm product and AWS-connection wording |
| Interpret the Payment Sync Score | Ready for review | Result components verified 30 August 2026 |
| Documented controls and tested controls | Ready | Explanatory content; owner review required |
| Assessment types and limitations | Ready for review | PCI DSS access wording remains blocked |
| Information you can enter | Ready | Data-handling review required |
| Assessment terminology | Ready for review | Confirm terms against current interface |

Do not describe a page as product-verified solely because its links and Markdown syntax pass automated checks.

Editorial checks:

- each page serves one dominant user need;
- headings are action-led and searchable;
- warnings contain an action the user can take;
- examples contain no real customer or infrastructure data;
- limitations are accurate without sounding promotional or defensive;
- links resolve; and
- customer-facing pages contain no internal implementation history.
