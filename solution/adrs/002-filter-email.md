# Filter Email

## Status

accepted

## Context

Our large userbase have a large volume/rate of new emails. Our system is only interested in a subset of these emails.

When emails are received we wish to only process those applicable to travel, or are whitelisted. If we pass all emails around our system unfiltered, there will be unnecessary traffic and overhead.

## Decision

Have the same process that integrates with reading from email providers also handle the filtering of emails.

## Rationale

### Pros

- Raw personal data does not escape this component, so inherently more secure overall
- Fewer messages passing around our queues

### Cons

- Extra coupling of concerns (not independently deployable & either aspect failing breaks both)

## Consequences

The Email Reader will integrate with third party email systems, read emails, ignore non-travel emails, and apply logic to extract and output structured travel data.
