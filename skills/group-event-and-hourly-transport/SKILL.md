---
name: group-event-and-hourly-transport
description: Arrange personal quotes for transport that one standard transfer does not cover in South East Queensland or Northern NSW. Use for groups of more than 7 people, wedding guest shuttles, corporate events and conferences, school formals, private jet (FBO) arrivals, multi-stop itineraries, return trips, winery or hinterland day tours, and chauffeur hire by the hour or day around Brisbane, the Gold Coast, the Sunshine Coast, Noosa, Toowoomba or Byron Bay.
---

# Groups, events and hourly hire

These trips are priced personally by the Unison Transfers team. The traveller fills in the website's quote request
form; nothing is charged until they accept the quote.

## Workflow

1. Collect the brief in one message where possible:
   - date(s) and times, pickup and drop-off places, extra stops in order
   - number of people and suitcases, children needing seats
   - for hourly hire, the number of hours; for events, the occasion (wedding, conference, formal)
   - return trip or one way
2. If the group is 7 or fewer and it is a single A-to-B trip, use `get_transfer_quote` instead and show the price.
3. Otherwise **call `get_quote_request_link`** with everything collected: `origin`, `destination`, `date`, `time`,
   `passengers`, `bags`, `child_seats`, `stops`, `hours`, `return_trip`, `notes`.
4. Give the traveller the link and the trip summary the tool returns, and say the team replies with an exact price.
   For something urgent, give the phone number 0401 605 940.
5. For a wedding or event with several runs (for example hotel → ceremony → reception → hotel), list each run in
   `stops` or `notes` so the quote covers the whole day.

## Facts you may state

- Vehicles: executive sedan (up to 3), Mercedes-Benz V-Class (up to 7), Mercedes-Benz Sprinter for larger groups on
  request; several vehicles can be booked together.
- Child seats are free.

## Do not

- Do not promise a price, vehicle availability or a reply time for quotes.
- Do not collect personal or payment details in the chat; the form does that.
