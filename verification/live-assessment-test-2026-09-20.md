# Live assessment test — 20 September 2026

## Scope

This record captures a public, signed-out browser test of the Infrastructure Readiness Check at `https://www.syncyourcloud.io/tools/infra-readiness`.

It is author-recorded evidence of observed interface behaviour. It is not an independent technical, security, compliance or editorial review.

## Test record

- **Test ID:** SYC-INFRA-PUBLIC-2026-09-20
- **Date:** 20 September 2026
- **Environment:** Production public website
- **Starting state:** Signed out, fresh browser session
- **Data used:** Synthetic answer selections; no customer, payment, account or confidential data
- **Result:** Public completion, results display and signed-out retake passed
- **Evidence type:** Browser-observed labels, controls, state and result content

## Verified observations

### Entry and questionnaire

- The entry page used the name **Payment Sync Score Infrastructure Readiness Check**.
- The description stated **21 questions across 7 critical layers**.
- Seven named layers were displayed:
  - Agent Orchestration
  - Security & Encryption
  - Compliance & Audit
  - Cost Optimisation
  - Observability & Monitoring
  - Payment Gateway Integration
  - Disaster Recovery
- Question 1 displayed 0% complete and 0/21 answered.
- **Back** and **Next** were disabled before the first answer.
- Selecting an answer increased the answered count and enabled **Next**.
- Question 2 displayed 5% complete and 1/21 answered.
- **Back** returned to question 1 while retaining 1/21 answered and an enabled **Next** control.
- Question 21 displayed 95% complete and 21/21 answered after selection.
- The final action was **View My Results**.

### Results

The signed-out journey produced:

- a 45% overall result;
- **Payment Sync Score (19/42)**;
- the heading **Partial readiness: 1 critical gap to address**;
- a seven-layer **Layer Breakdown**;
- a status, points value and percentage for every layer;
- a **Recommendations** section with one recommendation for every layer;
- **Save My Results** and **Sign in** links targeting `/auth`;
- an email-results form;
- a **Retake Assessment** control.

### Retake

Selecting **Retake Assessment** returned to:

- question 1 of 21;
- 0% complete;
- 0/21 answered;
- disabled **Back** and **Next** controls.

This verifies the signed-out reset behaviour only.

## Observations requiring product-owner confirmation

- The final answered question displays **95% complete**, not 100%, before the user selects **View My Results**. Confirm whether this is the intended definition of completion.
- The results copy used the grammatically incorrect phrases **1 layer are at risk** and **1 layer need attention**.
- The recommendation copy included specific assertions such as a seven-year audit-log retention period and engaging a QSA above a stated monthly processing value. These claims require accountable compliance review before documentation treats them as validated guidance.

## Needs verification

The following were not proved by this session:

- saving and retrieving results with an authenticated clean account;
- persistence after signing out and signing back in;
- authenticated reassessment history;
- failure recovery and answer preservation after a loading or network error;
- allowance-limit behaviour;
- Acquirer Readiness entitlement enforcement;
- locked and eligible export behaviour, file type, filename and contents;
- PCI DSS Gap Analysis access behaviour;
- email delivery from the results form;
- supported public API availability;
- independent technical, security, compliance or editorial review.

## Documentation impact

This session supports updates to:

- `docs/VERIFICATION-MATRIX.md`;
- the Infrastructure Readiness tutorial;
- result-review guidance;
- reassessment guidance, limited to signed-out reset behaviour.

Claims about authenticated saving, retrieval, exports, failure recovery or entitlement enforcement must remain labelled **Needs verification** until separate controlled tests are complete.
