---
title: Agent Identity Designer Guide Verification
status: changes-applied
date: 2026-09-22
site_route: /payments/agent-identity/guide
tool_route: /payments/agent-identity
---

# Agent Identity Designer Guide Verification

## Outcome

The guide and generator were reviewed against the current implementation and primary AWS, HashiCorp and PCI SSC sources. Material corrections were applied to both the guide and the generated artefacts.

## Claim review

| Area | Previous claim or behaviour | Finding | Correction |
|---|---|---|---|
| Workload identity | Every agent needs its own IAM role | Too absolute; each workload needs attributable identity, while role boundaries depend on the runtime architecture | Guide now recommends a dedicated role as the usual isolation boundary without presenting it as the only valid implementation |
| PCI DSS Requirement 8 | Requirement 8 wording implied a direct AI-agent mandate | PCI DSS defines application and system account controls but does not create a separate AI-agent category | Applicability is now explicitly tied to implementation, scope and assessor review |
| Agent Name | Used only in the UI | The value also appears in the Terraform header comment | Guide corrected |
| Role ID | Free-form field described as lowercase and hyphenated | The UI did not fully enforce the stated format or IAM name length | Input is now normalised and capped so the generated role name remains within the AWS limit |
| IAM JSON | Included a Principal element in an identity-based policy | AWS does not permit Principal in identity-based policies | Invalid statement removed; assumption controls remain in the role trust policy |
| Step Functions | Express or Standard could be selected with waitForTaskToken | Express Workflows do not support callback integration patterns | Human approval now generates a Standard Workflow only |
| Step Functions execution role | State machine used the agent runtime role | The role trust policy did not allow Step Functions to assume it | Dedicated Step Functions execution role and Lambda invocation policy added |
| Resource ARNs | Guide said to replace an account-position wildcard | The IAM JSON uses ACCOUNT_ID and some actions intentionally fall back to wildcard resources | Guide now identifies the real placeholder and requires review of every wildcard |
| Terraform readiness | Export described as directly deployable | Provider settings, variables and integration resources are still required | Export is now described as a starter module requiring fmt, validate, plan and non-production testing |
| Human approval | Workflow resumes only after a human sends the token | Step Functions resumes when an authorised caller returns the token; human identity must be enforced by the approval service | Guide and generated comments corrected |
| Least privilege | Broad permissions described automatically as a PCI DSS violation | Whether a control fails depends on scope, implementation and evidence | Wording qualified |
| Evidence | Screenshots or Terraform state suggested as proof | These may support evidence but do not alone prove operating effectiveness | Guide now calls for deployed policy, trust policy, approvals, reviews, CloudTrail and test evidence |

## Verified controls retained

- PCI DSS v4.0.1 Requirement 8.6 references application and system accounts.
- IAM roles provide temporary workload credentials when assumed through supported AWS services.
- DynamoDB GetItem and Query are read operations; PutItem, UpdateItem and DeleteItem can modify data.
- kms:Decrypt and kms:GenerateDataKey perform different cryptographic permissions and should be granted only when required.
- Bedrock InvokeModel is required for direct model invocation through the applicable Bedrock API.
- Secrets Manager rotation requires a compatible rotation mechanism and validation.
- The CDE toggle is an internal tag and does not determine PCI DSS scope.

## Primary sources

1. [AWS IAM security best practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)
2. [AWS Principal policy element](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_principal.html)
3. [AWS IAM Role API reference](https://docs.aws.amazon.com/IAM/latest/APIReference/API_Role.html)
4. [AWS Step Functions workflow types](https://docs.aws.amazon.com/step-functions/latest/dg/choosing-workflow-type.html)
5. [AWS Step Functions service integration patterns](https://docs.aws.amazon.com/step-functions/latest/dg/connect-to-resource.html)
6. [AWS temporary security credentials](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp.html)
7. [HashiCorp terraform validate](https://developer.hashicorp.com/terraform/cli/commands/validate)
8. [PCI SSC Document Library](https://www.pcisecuritystandards.org/document_library/)

## Limitation

This verification checks published claims and static generator logic. It is not evidence that a generated configuration has been deployed successfully or that a production environment complies with PCI DSS. Each export still requires architecture review, policy validation, deployment testing and evidence from the target environment.
