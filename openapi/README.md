# OpenAPI status

SyncYourCloud does not currently expose a supported public API in the supplied implementation evidence. This directory intentionally contains no API specification yet.

The next portfolio milestone is a separate, sanitised Assessment API demonstration. It should be implemented and tested before an OpenAPI document is published.

## Proposed demonstration scope

The demonstration may include fictional assessment data and these candidate operations:

- create an assessment;
- retrieve an assessment by ID;
- update answers;
- submit an assessment;
- retrieve a generated report.

Candidate operations are not live endpoints. They must not appear in public reference documentation until the implementation exists.

## Definition of done

An initial `openapi.yaml` is ready only when:

1. every documented operation exists in the demonstration environment;
2. authentication and authorisation behaviour is defined;
3. request and response examples use fictional data;
4. error responses have been exercised;
5. every procedure has been tested with Postman or `curl`;
6. no production identifiers, credentials or customer data are present;
7. the specification passes OpenAPI validation.

