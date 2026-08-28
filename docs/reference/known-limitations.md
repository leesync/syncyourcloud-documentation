# Known limitations

This page prevents prototype, simulated or fallback behaviour from being presented as a production capability.

## No supported public API

The supplied application documentation does not establish a live, supported public SyncYourCloud API. Do not publish API reference material or claim production API ownership until a real endpoint has been implemented, secured and tested.

## Browser-based payment tools

The documented payment tools generate output in the browser. They do not connect to a customer's AWS account or deploy generated policies, alarms, dashboards or infrastructure-as-code.

## Assessment fallback

The assessment service has a five-second timeout and can fall back to a bundled assessment definition when the configured remote service is unavailable. Documentation and support responses must distinguish a fallback result from a successful remote response.

## AI insights

The supplied AI insights implementation notes describe a mock generator and a planned model integration. Do not call this production AI analysis without evidence that the deployed application invokes and validates a live model.

## Data persistence boundaries

The supplied documentation confirms S3 persistence for pre-screen form data. It does not prove that every payment-tool input, assessment answer or generated result is stored in S3.

## Tool count

Marketing material refers to 26 tools. The supplied route documentation identifies 19 payment-tool routes, including two readiness assessments, plus separate public and cloud tools. Reconcile the deployed navigation and catalogue before using an exact count in developer documentation.

## Compliance outputs

PCI DSS mappings and gap reports are decision-support outputs. They are not an Attestation of Compliance, Report on Compliance or Qualified Security Assessor opinion.

