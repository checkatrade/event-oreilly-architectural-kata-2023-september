# Email Reader Non-GLobal

## Status

accepted

## Context

We have an architecture generally oriented towards global availability. We also have an Email Reader component that integrates with third party Email Providers. Although some aspects of the system require responsiveness according to region, others are concerned with raw throughput to particular implementations, which in turn may be specific to a region. The suggestion here is that the Email Reader in particular is focused on its integration with third party Email Providers, but does not necessarily dictate a global availability. It must cope with significant throughput, but may reasonably be limited to operation within regions specific to the email providers supported.

## Decision

Email Reader does not need to be "global".

## Rationale

### Pros

- May save unnecessary region-specific implementations
- Focus on specific throughput rather than broad availability

### Cons

- N/A

## Consequences

We might reduce overall cost and complexity by limiting the scope of the Email Reader implementation.
