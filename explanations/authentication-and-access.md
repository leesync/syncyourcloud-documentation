# Authentication and access

SyncYourCloud uses Firebase Authentication for user identity and Firestore for membership state.

## Supported sign-in flows

The documented application supports:

- email and password registration;
- email and password sign-in;
- Google sign-in by redirect;
- Google sign-in by popup;
- email verification;
- password reset;
- sign-out.

The production experience prefers redirect-based Google sign-in.

## Authentication lifecycle

1. The application starts and registers an authentication-state listener.
2. Firebase resolves the current session or redirect result.
3. On sign-in, the application creates a Firestore user document if one does not already exist.
4. The user context subscribes to the Firestore user document.
5. Membership changes update the interface through the real-time listener.
6. On sign-out, the listener is cancelled and local membership state returns to its default.

The user context applies a five-second loading timeout so that the application does not remain indefinitely in a pending state.

## Protected routes

Dashboard routes are wrapped in the dashboard layout. If no authenticated user is available, the user is redirected to `/auth`.

Authentication and authorisation are different controls:

- authentication establishes the user's identity;
- membership state determines which product features or exports the interface unlocks.

## First-run and session behaviour

The dashboard presents a first-run onboarding modal once per user on a given browser. The marker is stored in local storage and should not be treated as a security control.

A session-timeout warning is rendered globally. It warns the user before the Firebase session expires.

## Security guidance

- Never place Firebase credentials, Stripe secrets or AWS credentials in documentation examples.
- Treat browser storage as user-interface state, not secure server-side storage.
- Do not use the presence of an unlocked button as the sole proof of authorisation for a server-side action.
- Verify Firestore and Storage security rules separately from client-side route protection.
- Use fictional user IDs and organisation names in screenshots and examples.

## Troubleshooting sign-in

If a redirect sign-in returns the user to the wrong page, confirm that the intended path was stored before redirect and restored after `getRedirectResult` completes.

If the dashboard displays the wrong membership, confirm that the Firestore listener is attached to the signed-in user's document and that the stored tier value matches a supported internal code.

