# Contributing to the documentation

## Documentation workflow

1. Create a branch for one documentation change.
2. Identify whether the page is a tutorial, how-to guide, reference or explanation.
3. Verify the behaviour in the application or source before writing it as fact.
4. Use fictional data in every example.
5. Preview the Markdown and test every instruction.
6. Open a pull request that states what was verified and what remains unverified.
7. Merge only after technical and editorial review.

## Accuracy labels

Use these terms consistently:

- **Supported:** implemented and verified in the current documented build.
- **Prototype:** implemented for evaluation but not established as production behaviour.
- **Mock:** returns predetermined or locally generated example output.
- **Planned:** not yet implemented.
- **Generated example:** output that requires review and testing before use.

## Security review

Before committing, search for:

- API keys, tokens and credentials;
- real account, organisation or user IDs;
- private bucket names and object paths;
- live internal endpoints;
- personal or cardholder data;
- production screenshots containing customer information.

## Pull-request evidence

Every procedural documentation pull request should record:

- environment used for testing;
- date tested;
- test account type;
- expected result;
- actual result;
- known limitations.

