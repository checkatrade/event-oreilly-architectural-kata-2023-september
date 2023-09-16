# Separate Dashboard from Aggregator

## Status

accepted

## Context

Although they use similar data (the assembled Trip), we want the app to be useable whether the process of aggregatoring and transforming trip data is available or not. Therefore, separating the Trip Dashboard from the Trip Aggregator facilititates a resilient separation.

## Decision

Separate the Trip Dashboard and Trip Aggregator processes.

## Rationale

### Pros

- More resilient / independent faults
- Each can spike independently
- Trip Dashboard insulated from complexity of "stitching" / assembling aggregated Trips from atomic inputs

### Cons

- Additional complexity
- Additional traffic
- Additional cost

## Consequences

The Trip Dashboard and Trip Aggregator are independent.
