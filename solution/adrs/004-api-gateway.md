# API Gateway

## Status

accepted

## Context

We want the benefits of an API gateway to protect our Trip Dashboard API. Using Firebase or similar as per [#003](003-streaming-database.md) may mean that read operations already use a managed alternative.
Regardless of the implementation of [#003](003-streaming-database.md), an API Gateway is at least required for write operations.

## Decision

Use an explicit API Gateway in addition to any "built-in" equivalent that a managed streaming database may provide.

## Rationale

### Pros

- DDOS protection
- Routing
- Security / Isolate internal network from public

### Cons

- Additional cost

## Consequences

The App will connect to the larger system via an API Gateway, at least for writes. Reads may occur directly from the managed streaming database where the implementation allows.
