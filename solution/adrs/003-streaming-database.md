# Streaming Database

## Status

accepted

## Context

We face the challenge of having many updates to be pushed from our system to user-facing UIs. The overhead of managing open sockets is unattractive, and may complicate both client and server sides. Similarly we require both authentication and authorization. These are difficult problems to solve, and have heavy security implications.

## Decision

Adopt a streaming database and accompanying framework, such as Firebase.

## Rationale

### Pros

- Global
- Managed
- Distributed
- Authentication built in
- Authorization to access data built in
- Scalable streaming updates of data in app
- Clientside integration / framework
- Notifications can be application or operating system level
- Easier for a startup to delegate this technical overhead to a framework

### Cons

- A degree of vendor lock in / operating model lock in

## Consequences

Applications use the Firebase framework. UI frameworks such as React / React Native become an attractive choice to embrace the flow of streaming updates.
