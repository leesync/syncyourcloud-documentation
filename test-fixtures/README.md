# Synthetic test fixtures

The supplied tool-testing prompt and generated outputs describe fictional fintech companies, architectures and incidents. Use them as repeatable input fixtures for testing SyncYourCloud tools.

They are not:

- customer case studies;
- independent practitioner reviews;
- evidence of production use;
- proof that the generated AWS or PCI DSS advice is correct;
- a substitute for running the deployed tool.

## How to use a fixture

1. Select one fictional scenario.
2. Enter only the fields supported by the deployed tool.
3. Save the actual output produced by the tool.
4. Compare it with the expected structure, not with every AI-generated claim.
5. Verify technical and compliance statements against authoritative sources.
6. Record differences as product defects, documentation defects or fixture defects.

## Naming convention

Name validated fixtures by tool and scenario, for example:

`infrastructure-readiness-neobank-01.md`

Each fixture should contain:

- fictional input;
- expected output shape;
- actual output;
- pass or fail result;
- reviewer and date;
- linked issue for any failure.

