# App Auth

## Status

accepted

## Context

The app ought to authenticate and authorize via a managed provider, as per the framework chosen in [#003](003-streaming-database.md). The implementation is a framework within the app that communicates with the hosted solution.

## Decision

Use a managed authentication and authorization provider, such as Firebase.

## Rationale

### Pros

- Offers different & convenient sign-on options, such as social media providers
- Scalable
- Secure
- Simple to implement
- Ability to integrate with native authentication mechanisms, e.g. biometrics

### Cons

- Additional cost

## Consequences

The app handles authentication and authorization via a managed provider.
