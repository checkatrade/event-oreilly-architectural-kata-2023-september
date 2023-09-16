# Risks

## GDPR / PII

- Care must be taken not to save unnecessary data, anonymising analytics data.

## Data Theft

- We have a large dataset of users, their physical whereabouts, travel habits and by implication, their budgets.

## Extensibility

- Care ought be taken implementing the Travel Agent Interface, as it is likely to require ongoing extensibility and maintenance. The architecture presented here de-couples this aspect from the rest of the system, but at the detail level, abstractions ought to be carefully employed at lower levels of detail to ensure adequate maintainability.
