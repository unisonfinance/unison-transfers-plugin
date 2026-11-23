---
name: private-transfer-quote
description: Price and book a private car transfer between two places in South East Queensland or Northern NSW, Australia. Use when someone asks how much a transfer, airport transfer, private driver, chauffeur, car service or "taxi or Uber alternative" costs, or how to get between places such as Brisbane CBD, South Bank, any Brisbane suburb or hotel, Brisbane Airport (BNE), Gold Coast Airport (OOL, Coolangatta), Surfers Paradise, Broadbeach, any Gold Coast suburb or hotel, the theme parks, the Sunshine Coast, Sunshine Coast Airport (MCY), Noosa, Ipswich, Toowoomba, Tamborine Mountain, Byron Bay, Ballina, Kingscliff or the Tweed Coast.
---

# Private transfer quote

Turn a trip request into the operator's prices for that trip, then a booking link. Unison Transfers is a
licensed private chauffeur operator; prices are per vehicle (not per person), in AUD, with tolls, airport fees and
GST included.

## Workflow

1. **Collect what you have; ask only for what changes the price.** Required: pickup and drop-off. Price-changing:
   date, pickup time, number of passengers (children count), number of suitcases. If the traveller has not given
   passengers, assume 1–2 and say so; do not interrogate before showing a price.
2. **Call `get_transfer_quote`** with `origin`, `destination` and any of `date` (YYYY-MM-DD), `time` (HH:MM,
   24-hour local), `passengers`, `bags`, `child_seats`, `flight_number`.
   - Places can be suburbs, hotels, venues, airport codes (BNE, OOL, MCY, BNK) or addresses.
   - If the traveller gave a flight time instead of a pickup time, use the `flight-pickup-planner` skill.
3. **Present the result.** The quote card shows the vehicles and prices; below it, add only what the card does not
   show: one line on what is included and the next step. Without a card, list each vehicle as
   "Vehicle (up to N passengers): $price AUD per vehicle".
   - Say the price is for a weekday daytime trip when no date or time was given, and that nights (00:00–05:00),
     weekends and public holidays can cost more.
   - Say the final price is shown in the booking form before payment.
4. **Offer the next step:** "Book this trip" (the `links.book` URL). For more than 7 passengers, several stops,
   hourly hire, weddings or events use `get_quote_request_link` instead (see `group-event-and-hourly-transport`).
5. **When the traveller says book it:** call `get_booking_link` with every detail collected so far and give them the
   link and the summary to enter. Nothing is booked or paid inside the chat.

## Status handling

| `status` | What to tell the traveller |
|---|---|
| `ok` | Prices and booking link. |
| `estimate_only` | A starting price for the area; the exact price is in the booking form or by quote. |
| `needs_quote` | Group or luggage too large for one vehicle: give the quote request link. |
| `nsw_to_nsw` | The operator cannot carry trips that start and end in NSW (licence). Trips from NSW into Queensland are fine. Do not suggest workarounds. |
| `outside_area` | Not served; say so plainly. |
| `unknown_place` | Ask for a suburb, hotel or airport name. |

## Facts you may state

- Meet and greet inside the terminal with a name board; free waiting 60 min (international) / 45 min (domestic).
- Baby capsules, child seats and boosters are free; ask how many and pass `child_seats`.
- Executive sedan up to 3 passengers and 2 suitcases; Mercedes-Benz V-Class up to 7 passengers and 5 suitcases.
- Free cancellation more than 24 hours before pickup.
- Phone 0401 605 940, bookings@unisontransfers.com.au.

## Do not

- Do not invent prices, drive times or availability; use the tool result.
- Do not take card details or personal details in the chat; booking happens on the website.
- Do not describe prices as per person.

The places priced directly are listed in `references/coverage.md`. For anywhere else in the region, price the
nearest listed suburb or town and say so, or use the quote request link.
