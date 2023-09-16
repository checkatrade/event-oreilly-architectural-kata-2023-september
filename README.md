# O'Reilly Architectural Kata 2023 - Team Checkatrade

This is the Team Checkatrade submission for the [O'Reilly Architectural Kata 2023](https://learning.oreilly.com/live-events/architectural-katas-fall-2023/0636920097709/).

View our submission on [GitHub Pages](https://congenial-adventure-8krl2ek.pages.github.io/).

[Kata Info & Resources](event/event.md)

## Road Warrior

The [brief](event/kata-brief.md) is to create an architecture for a travel dashboard, called Road Warrior.

![image logo](./images/logo.png)

## Team Checkatrade

| Img | Name | GitHub | LinkedIn |
|-|-|-|-|
| ![image](images/team/jack.jpg) | Jack Frankland | [GitHub](https://github.com/jackfrankland) | [LinkedIn](https://www.linkedin.com/in/jackfrankland/?lipi=urn%3Ali%3Apage%3Ad_flagship3_people_connections%3BFZxCll5DQouFM6zHFN48zg%3D%3D) |
| ![image](images/team/adam.jpg) | Adam Hill | [GitHub](https://github.com/AdamDavidHill) | [LinkedIn](https://www.linkedin.com/in/adamdavidhill/) |
| ![image](images/team/carlos.jpg) | Carlos Menenzes | [GitHub](https://github.com/carlosalbertomenezes) | [LinkedIn](https://www.linkedin.com/in/carloscardosomenezes/?lipi=urn%3Ali%3Apage%3Ad_flagship3_people_connections%3BFZxCll5DQouFM6zHFN48zg%3D%3D) |
| ![image](images/team/jens.jpg) | Jens Skott | [GitHub](https://github.com/ctjens) | [LinkedIn](https://www.linkedin.com/in/jens-skott-5aa4b513/?lipi=urn%3Ali%3Apage%3Ad_flagship3_people_connections%3BFZxCll5DQouFM6zHFN48zg%3D%3D) |

## Repository Index

### Problem

- [Assumptions](problem/assumptions.md)
- [Goals](problem/goals.md)
- [Requirements](problem/requirements.md)
- [Actors, Actions & Interests](problem/actors.md)
- [Risks](problem/risks.md)
- [Architectural Charactertistics](problem/charactertistics.md)
- [Glossary](problem/glossary.md)

### Solution

- [Architectural Style Analysis](solution/architectural-style-analysis.md)
- [Security, Privacy & Compliance](solution/security-privacy-compliance.md)

> **Note:** All wireframe and diagram `.png` files can be viewed normally, but also have `Excalidraw` metadata embedded, and so can be imported back into Excalidraw and viewed/re-edited in their *original vector form*.

#### UI Wireframes

We made UI wireframes to help visualise the view of the system from our Traveller user's perspective, and sanity-check our pre-conceptions of interactions and flows.

| Thumbnail | Title | Description |
|-----------|-------|-------------|
| [![image Login Screen (.excalidraw.png)](/images/wireframes/ui-login.excalidraw.png)](/images/wireframes/ui-login.excalidraw.png)       | [Login](/images/wireframes/ui-login.excalidraw.png) | We offer multiple means of login, including common Login providers, and integration with native biometric methods. We are also up front with our terms and privacy information, respecting GDPR. |
| [![image Manage Trip Screen (.excalidraw.png)](/images/wireframes/ui-manage-trip.excalidraw.png)](/images/wireframes/ui-manage-trip.excalidraw.png)       | [Manage Trip](/images/wireframes/ui-manage-trip.excalidraw.png) | Our "main screen" allows the user to manage their trips. Trip parts can be added and removed. Adding a new part, such as a flight, takes you to the next screen to provide details. There are links to help options, and the EoY report can be downloaded. The overall Trip can be shared, either privately or via Social Media. |
| [![image Add Flight Screen (.excalidraw.png)](/images/wireframes/ui-add-flight.excalidraw.png)](/images/wireframes/ui-add-flight.excalidraw.png)       | [Add Flight](/images/wireframes/ui-add-flight.excalidraw.png) | This screen allows you to enter a Booking code. There is also the option to connect an Email account, which we then sync incoming emails with to look for new or updated bookings.
| [![image Manage Emails Screen (.excalidraw.png)](/images/wireframes/ui-manage-emails.excalidraw.png)](/images/wireframes/ui-manage-emails.excalidraw.png)       | [Manage Emails](/images/wireframes/ui-manage-emails.excalidraw.png) | Similar to the previous screen, you can manage your Email account connections from an "Account" area. Connecting or disconnecting them. |

#### Diagrams

| Thumbnail | Title | Description |
|-----------|-------|-------------|
| [![image Context Diagram (.excalidraw.png)](/images/diagrams/context.excalidraw.png)](/images/diagrams/context.excalidraw.png)       | [Context Diagram](/images/diagrams/context.excalidraw.png) | An overview of how the system fits together and connects with external actors and systems. |
| [![image Email Reader Diagram (.excalidraw.png)](/images/diagrams/reader.excalidraw.png)](/images/diagrams/reader.excalidraw.png)       | [Email Reader Diagram](/images/diagrams/reader.excalidraw.png) | The Email Reader is responsible for email integrations, and extracting Booking Codes from incoming emails. Email account integrations can be added/removed. This uses a document database as a fast means of reading/writing data for user-specific events. The data store would store the necessary information to integrate with a user email account, as well as a list of previously reported booking codes, so it knows whether it's a new booking or not. |
| [![image Trip Aggregator Diagram (.excalidraw.png)](/images/diagrams/aggregator.excalidraw.png)](/images/diagrams/aggregator.excalidraw.png)       | [Trip Aggregator Diagram](/images/diagrams/aggregator.excalidraw.png) | The Trip Aggregator is for combining fragmented trip elements, and re-constituting the overall picture of a trip. Each time the overall picture is re-constituted, a Trip Updated event would be published. If it's the first time we've seen that booking code, then a dedicated event is raised, allowing another part of the system to begin polling/integrating with associated booking events for that trip. Anonymised data is added to the data lake, where it can either be queried by external customers via a metrics API, or queried by a report generation process, which would be run on a schedule to generated EoY reports. The data lake, report generation and analytics could easily be de-coupled from the aggregator if desired.  |
| [![image Trip Dashboard Diagram (.excalidraw.png)](/images/diagrams/dashboard.excalidraw.png)](/images/diagrams/dashboard.excalidraw.png)       | [Trip Dashboard Diagram](/images/diagrams/dashboard.excalidraw.png) | The Dashboard API is  largely a "Backend For Front-End", supporting the app integration with the wider system, and event bus. Booking codes may come from the app or emails, and so be received or sent by the Dashboard. The Dashboard listens to Trip Updated events, where it updates the Trips in the app accordingly. It has a document database as per [003 Streaming Database](solution/adrs/003-streaming-database.md) to cache and stream this application data. |
| [![image Travel Agent Interface Diagram (.excalidraw.png)](/images/diagrams/interface.excalidraw.png)](/images/diagrams/interface.excalidraw.png)       | [Travel Agent Integration Diagram](/images/diagrams/interface.excalidraw.png) | The Travel Agent Integration Interface is a unified abstraction over multiple external integration implementations. This connects to different agencies and systems, registering and unregistering callbacks accordingly. It maintains a list of booking codes that our users are interested in. It shares detailed incoming trip information, which will be picked up by the Trip Aggregator. |
| [![image Flow Diagram (.excalidraw.png)](/images/diagrams/flow.excalidraw.png)](/images/diagrams/flow.excalidraw.png)       | [Flow Diagram](/images/diagrams/flow.excalidraw.png) | A representation of the process flow when either new booking codes arrive in emails, or the user enters them manually. |

#### ADRs

- [000 ADR Template](solution/adrs/000-adr-template.md)
- [001 Event-Driven Microservices.md](solution/adrs/001-event-driven-microservices.md)
- [002 Filter Email.md](solution/adrs/002-filter-email.md)
- [003 Streaming Database](solution/adrs/003-streaming-database.md)
- [004 API Gateway](solution/adrs/004-api-gateway.md)
- [005 Cross-Platform Mobile Framework](solution/adrs/005-cross-platform-mobile-framework.md)
- [006 Integration Service](solution/adrs/006-integration-service.md)
- [007 Open Graph](solution/adrs/007-open-graph.md)
- [008 App Auth](solution/adrs/008-app-auth.md)
- [009 Separate Dashboard from Aggregator](solution/adrs/009-separate-dashboard-from-aggregator.md)
- [010 Email Reader Non-Global](solution/adrs/010-email-reader-non-global.md)
- [011 Email Webhooks](solution/adrs/011-email-webhooks.md)
