# Security

## Authentication & Authorization

We offload much of the risk and implementation overhead of authentication and authorization by using a combination of third party login providers ("Login with Google" etc.) for our app's authentication, and a framework such as Firebase for managing our authorization. Therefore we never store passwords/salts ourselves. Care must however be taken in the storage and transport of our user identity, especially the emails.

## Privacy

- Must access minimal data for emails (new only where possible), and not store raw content
- Anonymise all analytics
- Anonymise data where possible, for example the Trip Aggregator databases contain rich details of trips, but could organise user data via a abstracted keys rather than emails, and so do not need to store user emails in the same database. If subsequently compromised, it would be harder for an attacker to understand whom the trip related to.

## Compliance

- GDPR, inc. Right to Be Forgotten
- Anonymise analytics data
- Delegate consent to read emails to auth providers
- Do not store raw email content
