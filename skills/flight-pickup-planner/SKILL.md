---
name: flight-pickup-planner
description: Plan an airport transfer around a flight in South East Queensland or Northern NSW. Use when a traveller landing at or flying out of Brisbane Airport (BNE), Gold Coast Airport (OOL, Coolangatta), Sunshine Coast Airport (MCY) or Ballina Byron Airport (BNK) gives a flight number or flight time and needs to know when the car should come, how long the drive takes to their hotel or suburb, and what it costs.
---

# Flight pickup planner

## Workflow

1. Work out the direction:
   - **Arriving**: the flight lands, the traveller is collected at the airport and driven to a hotel, suburb, the
     cruise terminal or another town.
   - **Departing**: the traveller is collected from a hotel, home or the cruise terminal and driven to the airport.
2. Collect: airport, the other place, flight time (landing time for arrivals, departure time for departures, local
   time HH:MM), date, domestic or international, passengers, suitcases, flight number if given.
3. **Call `plan_airport_transfer`** with `airport`, `other_place`, `direction` (`arriving` or `departing`),
   `flight_time`, and `date`, `international`, `passengers`, `bags`, `flight_number` when known.
4. Present:
   - The suggested pickup time and the one-line reason from `reasoning`.
   - Arrivals: the pickup is booked for the landing time; the chauffeur tracks the flight and waits free of charge
     (60 min international, 45 min domestic), meeting the traveller inside the terminal with a name board.
   - Departures: the pickup time already allows for the drive, traffic and the usual airline check-in advice
     (about 2 h domestic, 3 h international). Tell the traveller to check their airline's own advice.
   - The vehicle prices from `options` and the booking link.
5. If an option's `surcharges` lists a night, weekend or holiday rate, say it is included in the price shown. Without
   a date, prices are for a weekday; say weekends and public holidays can cost more.
6. When the traveller wants to book, call `get_booking_link` with the pickup time from step 3 (not the flight time),
   the date, the flight number and the passengers.

## Do not

- Do not look up live flight status or promise a flight is on time.
- Do not change the airline's check-in advice; present it as general guidance.
- Do not quote a price the tool did not return.
