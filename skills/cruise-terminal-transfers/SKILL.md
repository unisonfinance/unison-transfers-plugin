---
name: cruise-terminal-transfers
description: Get cruise passengers to or from the Brisbane International Cruise Terminal (Cruise Terminal Drive, Pinkenba, at Luggage Point) by private transfer. Use when someone is starting or ending a cruise in Brisbane and needs a car, chauffeur or van between the terminal and Brisbane Airport (BNE), Brisbane CBD or a Brisbane hotel or suburb, the Gold Coast, Gold Coast Airport (OOL), the Sunshine Coast, Noosa, Toowoomba, or Northern NSW towns such as Kingscliff, Casuarina, Byron Bay and Ballina.
---

# Brisbane cruise terminal transfers

Cruise passengers usually travel with more luggage and on fixed embarkation and disembarkation days, so get the
bags right and allow time.

## Workflow

1. Confirm the direction: **to the terminal** (embarkation) or **from the terminal** (disembarkation).
2. Collect: the other place, date, time (for embarkation, the time they want to arrive at the terminal; for
   disembarkation, a realistic time after the ship's disembarkation window), passengers and suitcases. Cruise
   luggage matters: 2 passengers often have 3–4 suitcases, which needs the V-Class.
3. **Call `get_transfer_quote`** with origin and destination ("Brisbane cruise terminal" works as a place),
   `date`, `time`, `passengers`, `bags`.
   - To list everywhere served from the terminal, call `find_transfer_routes` with `place: "Brisbane cruise terminal"`.
4. Present the vehicles that fit the luggage, the drive time and the booking link.
   - Embarkation: suggest arriving at the terminal at the time the cruise line gives on the ticket; work back from
     the drive time shown.
   - Disembarkation: suggest a pickup time after the cruise line's disembarkation time; the chauffeur meets them.
5. For a group or a pre-cruise hotel night plus terminal run (two trips), offer `get_quote_request_link` for a
   combined quote, or price each leg separately with `get_transfer_quote`.

## Northern NSW passengers

A trip from a NSW town (Kingscliff, Casuarina, Tweed Heads, Byron Bay, Ballina…) to the Brisbane cruise terminal is
fine because it ends in Queensland. A trip between two NSW places is not available.

## Do not

- Do not invent ship times, terminal opening times or check-in rules; refer the traveller to their cruise line.
