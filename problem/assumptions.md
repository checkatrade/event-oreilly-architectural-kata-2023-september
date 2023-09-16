# Assumptions

## Assumptions

| Id | Title | Assumption |
|:--:|:------|:--------|
| 1 | Limited Email Parsing | The analysis of emails is only about extracting a booking code, such that it might be achieved with a selection of reasonably simple parsing algorithms, and not necessitate natural language processing to extract more complex structured data, and that this data will be looked up from other systems from the code. |
| 2 | Definition of Richest UI | "Richest UI" means use of native capabilities where possible, e.g. GPS, biometric auth etc. |
| 3 | Help Me Mechanism | "Help me!" really just means forward to a help page, so we need to know the URL etc. of the provider, but not intercede in the help communication as such. |
| 4 | Updating a Booking | The idea of "updating" a booking within the app is a very light touch, in that it is just the app-specific "entry" of the booking that's being updated, for example editing a convenient name for the overall trip, rather than for example, requesting a change of flight time. |
