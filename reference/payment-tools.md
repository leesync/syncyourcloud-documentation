# Payment tools reference

This reference lists the payment-dashboard tools identified in the supplied application documentation. Each tool runs in the browser in the documented build. Export availability varies by membership tier.

| Tool | Route | Primary output |
| --- | --- | --- |
| Infrastructure Readiness | `/payments/infra-readiness` | Readiness assessment and results |
| Agentic Readiness | `/payments/agentic-readiness` | Agentic payment readiness assessment |
| PCI Gap Analysis | `/payments/pci-gap-analysis` | PCI DSS gap report with severity ratings |
| Architecture Decision Records | `/payments/arch-decision-records` | Structured architecture decision records |
| Security Controls Matrix | `/payments/security-controls` | Filterable PCI DSS controls and evidence pointers |
| Cardholder Data Flow | `/payments/cardholder-data-flow` | Configurable data-flow diagram and security brief |
| Latency Analysis | `/payments/latency-analysis` | Pipeline latency analysis and recommendations |
| Scaling Roadmap | `/payments/scaling-roadmap` | Phased infrastructure scaling plan |
| Agent Identity Designer | `/payments/agent-identity` | IAM policy or Terraform example |
| Spend Controls | `/payments/spend-controls` | Agent spending and approval policy example |
| Idempotency Safety Rails | `/payments/idempotency-rails` | Idempotency, retry and circuit-breaker configuration |
| Agent Payment Flow Simulator | `/payments/agent-flow-simulator` | Placement risks, use cases and audit brief |
| Failure Playbook | `/payments/failure-playbook` | Failure scenarios, remediation and escalation runbook |
| Observability Pack | `/payments/observability-pack` | CloudWatch, X-Ray and alerting configuration examples |
| Infrastructure Cost Modeller | `/payments/cost-modeller` | Estimated AWS service cost breakdown |
| Rollback Designer | `/payments/rollback-designer` | Saga compensation plan and Step Functions example |
| Multi-Region Failover | `/payments/multi-region-failover` | Failover topology, validation and runbook |
| Acquirer Readiness | `/payments/acquirer-readiness` | Weighted readiness report across five sections |
| Architecture Change Impact | `/payments/arch-change-impact` | Change-risk assessment and rollback checklist |

## Export behaviour

Some tools can export Markdown, CSV, spreadsheet, JSON, YAML, Terraform or CloudFormation examples. Where an export is unavailable for the current tier, the interface displays a locked control and directs the user to membership information.

Generated configuration is an example. Review and test it before use. SyncYourCloud does not apply it to an AWS account.

## Inventory note

Product messaging refers to 26 tools, while the supplied dashboard route reference identifies 19 payment-tool routes, including the two readiness assessments. Reconcile the public catalogue, dashboard routes and deployed build before publishing a numbered inventory claim.

