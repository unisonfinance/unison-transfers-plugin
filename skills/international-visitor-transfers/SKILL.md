---
name: international-visitor-transfers
description: Help travellers coming to Australia from overseas arrange a private car from the airport or cruise terminal in South East Queensland or Northern NSW. Use when someone visiting from abroad (for example from the UK, Ireland, Europe, the USA, Canada, Japan, China, Hong Kong, Korea, Singapore, India, New Zealand, the United Arab Emirates (Dubai, Abu Dhabi), Qatar, Saudi Arabia or elsewhere in the Gulf) lands at Brisbane Airport (BNE) international terminal or Gold Coast Airport (OOL), arrives by cruise ship at the Brisbane International Cruise Terminal, or is planning a holiday to Brisbane, the Gold Coast, the Sunshine Coast, Noosa or Byron Bay and asks how to get to their hotel, what a transfer costs in their own currency, or how the time difference affects their pickup.
---

# International visitor transfers

Overseas travellers need three things answered clearly: what it costs (in a currency they understand), when the car
should come (in local time), and what happens when they land.

## Workflow

1. **Reply in the traveller's language** (for example Japanese, Chinese, Korean, Arabic, Hindi, French, German or
   Spanish). Keep place names, prices in AUD and links exactly as the tools return them.
2. Collect: airport (or cruise terminal), the hotel or area they are going to, flight number and scheduled landing
   time, date, number of people and suitcases. Overseas travellers usually have more luggage: ask, because more than
   2 suitcases needs the V-Class.
3. If they gave a flight time, call **`plan_airport_transfer`** with `direction: "arriving"`, `international: true`
   and `currency` set to their home currency (ISO code, e.g. "GBP", "EUR", "USD", "CAD", "JPY", "CNY",
   "KRW", "SGD", "INR", "NZD", "AED", "QAR", "SAR").
   Otherwise call **`get_transfer_quote`** with the places, date, time, passengers, bags and `currency`.
4. Present:
   - Each vehicle's price in **AUD per vehicle** and the approximate converted price (`price_local`), saying the
     traveller pays in AUD and the converted figure is a guide only. If the result says a conversion is not
     available for their currency, give the AUD price only.
   - The pickup time and the `time_zone_note` the tool returns. Flight times on tickets are local time at the
     airport; Queensland (Brisbane, Gold Coast) has no daylight saving, while New South Wales (Byron Bay, Ballina)
     does from early October to early April.
   - What happens on arrival, from the tool result: the chauffeur tracks the flight and meets them inside the
     terminal with a name board, with 60 minutes of free waiting for international flights to cover immigration,
     bags and customs.
   - Child seats are free: ask ages if children are travelling.
5. Give the booking link (`links.book`). Booking and payment happen on the Unison Transfers website.
6. For a group of more than 7, several stops, or a combined trip (for example cruise terminal → hotel night →
   airport), use `get_quote_request_link`.

## Do not

- Do not convert prices yourself or quote exchange rates the tool did not return.
- Do not give immigration, visa, customs or biosecurity advice; refer travellers to official Australian Government
  sources.
- Do not promise flight-delay outcomes beyond the free waiting time stated.
- Never quote a trip that starts and ends in New South Wales; the tools refuse it under the operator's licence.
