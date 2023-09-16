# Event-Driven Microservices

## Status

accepted

## Context

We are architecting a solution for a problem domain that features reading changes from external systems, at scale, around the world.

Our driving [architectural characteristics](../../problem/architectural-charactertistics.md) are:
- fault-tolerance
- interoperability
- scalability

## Decision

Adopt a cloud-hosted Event-Driven Microservices architectural style.

## Rationale

### Pros

- Distributed & de-coupled nature is well-suited to resilient design patterns
- Independently deployable processes are well suited to scalable, managed hosting options
- Asynchronous domain events such as incoming emails and bookings being made or updated drive the behaviour of the system

### Cons

- Additional complexity (e.g. versioning strategies required, number of relationships)
- Additional traffic/communication

## Consequences

