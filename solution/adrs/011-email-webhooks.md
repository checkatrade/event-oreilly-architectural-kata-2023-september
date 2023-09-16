# Email Webhooks

## Status

accepted

## Context

Problem is that we have 15M users, and need to know if there's an email for all of them at least every 5 minutes. If we were to poll them once every 5 minutes, that's an enormous volume of calls all at once. Even if we were to evenly spread the calls, that's still 50k per second. Preferable is that where possible, email providers call us when new emails are available. We would offer a webhook / endpoint and subscribe the account to notify us of incoming emails.

## Decision

Prefer webhooks or equivalent notification-based interactions with email providers where possible.

## Rationale

### Pros

- More manageable volume of traffic

### Cons

- N/A

## Consequences

We reduce total calls to email providers significantly.
