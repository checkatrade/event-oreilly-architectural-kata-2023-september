# Actors, Actions & Interests

## Actors

| Actor | Description |
|-------|:------------|
| Traveller | Our primary "user". They interact with Road Warrior via Web and Mobile UIs. Travel data relates to their planned travels. They own the email accounts, and they are the ones editing their bookings. |
| Targeted Person | These are colleagues and associates of the traveller, whom the traveller wishes to share details with of individual trips. This information may be viewed on the platform, or via third party social media platforms. |
| Public | Given that data may be shared on various social media platforms, we acknowledge that either intentionally or unintentionally, there is a possibility that viewers of the data are from the public at large. How publicly this data is shared may be down to the third party privacy settings of the individual external platforms rather than Road Warrior. May consume data exposed by Road Warrior. |

## Excluded Actors

| Actor | Description |
|-------|:------------|
| Travel Agent | These are the agents who provide third party support to travellers for when things go wrong with arranging the trip. Because Road Warrior forwards users on to these Agent's own systems, they are not direct users of with Road Warrior. |

## Actions

### Traveller

- Register
- Login/Logout
- Reset Passwords
- Create/Read/Update/Delete email integration
- View upcoming trips
- View EoY reports
- Request support
- Share Trip
- Create/Read/Update/Delete Trips*
- Create/Read/Update/Delete Third-Party Reservation**

> \* = The brief mentions Updating a Trip. As interactions with the agencies is done manually, we interpret this as basic modification of the outline of a trip, perhaps labelling it with a friendly name, for example. Primarily, the manual adding of trips would only be via entering a Booking code. Other mechanisms add trips automatically.

> \** = Modification of the bookings themselves is an external action to Road Warrior. Road Warrior comes to know of bookings either through email integration, or the user entering a code. No actual bookings are created or modified within Road Warrior.

### Targeted Person

- View shared trip

### Public

- View shared trip

## Interests / Concerns

| Actor/Org | Interest | Implied Characteristic(s) |
|-|:-|:-|
|Traveller|Email Privacy|Security / Privacy|
|Traveller|Choose Agency|Configurability, Integration, Interoperability|
|Traveller|Rich UI|Responsiveness|
|Traveller|Always connected around the world|Availability, Fault-Tolerance|
