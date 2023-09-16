# Cross-Platform Mobile Framework

## Status

accepted

## Context

The system needs to communicate with a variety of third party external systems. These include both individual travel provider APIs, and Global Distribution Systems that travel providers integrate with.

## Decision

Use a dedicated service to encapsulate these varied integrations.

## Rationale

### Pros

- Encapsulate variances of these integrations
- Single standardized interface for internal events

### Cons

- Will grow in complexity over time as more and more integrations are added

## Consequences

The system will have a single abstraction to work against for communicating with external travel systems.
