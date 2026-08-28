# Troubleshoot common issues

## The assessment takes more than five seconds

The documented assessment service attempts a configured remote request and uses a five-second timeout. If the request does not complete, the application can load bundled assessment definitions.

Check the browser network panel for the failed or aborted request. Then confirm whether the displayed result came from the fallback path before reporting an API incident.

## A user is redirected to the sign-in page

Dashboard routes require an authenticated Firebase user.

1. Confirm that Firebase has resolved the authentication state.
2. Confirm that the redirect sign-in result completed.
3. Check whether the session expired.
4. Sign in again and return to the dashboard route.

## The wrong membership features are displayed

Membership state is read from the user's Firestore document through a real-time listener.

1. Confirm the signed-in user ID.
2. Inspect the corresponding Firestore user document.
3. Confirm that the membership tier uses a supported internal value.
4. Confirm that the real-time subscription is active.
5. Refresh the membership subscription if the application exposes that action.

## An export button is locked

Exports are gated by tool and membership tier. A locked export control navigates to the membership page. This is expected behaviour when the current tier does not include that export.

Do not alter client-side state to bypass the control. If the user's subscription has changed, verify the Firestore membership record and allow the real-time listener to update the interface.

## Pre-screen data does not save

The pre-screen persistence service uses AWS Amplify Storage and S3. Automatic saves are debounced by two seconds.

1. Wait for the debounce interval to complete.
2. Confirm that the user is permitted to write to the intended storage path.
3. Check the browser console and network panel for Amplify Storage errors.
4. Confirm that the configured bucket and region match the deployed environment.
5. Retry with fictional test data; never use cardholder data or credentials.

## Stripe checkout does not open

Self-service subscription buttons open a Stripe-hosted Payment Link.

1. Confirm that the button is intended for a self-service tier.
2. Check whether the browser blocked a new tab or redirect.
3. Confirm that the configured Payment Link is active.
4. For enquiry-only tiers, use the application form instead of a direct checkout link.

## Generated infrastructure code fails validation

Tool output is generated as a starting point and is not automatically deployed or guaranteed to match a target AWS account.

1. Save the generated file outside the production repository.
2. Run the relevant formatter and validator.
3. Replace sample account IDs, regions, resource names and thresholds.
4. Review IAM scope, encryption, retention and logging settings.
5. Test in a sandbox account through the organisation's normal review process.

