# Unison Transfers plugin (Claude and ChatGPT)

Private airport, cruise terminal and chauffeur transfers in South East Queensland and Northern NSW, Australia:
Brisbane and Brisbane Airport (BNE), the Brisbane International Cruise Terminal, the Gold Coast and Gold Coast Airport
(OOL), the Sunshine Coast and Sunshine Coast Airport (MCY), Noosa, Ipswich, Toowoomba, Tamborine Mountain, Byron Bay,
Ballina Byron Airport (BNK) and the Tweed Coast.

Ask for a transfer and the assistant prices it for your date, time and group (per vehicle, AUD), plans the pickup time
from your flight, lists the routes served from a place and gives you the link to book on the Unison Transfers website.
Nothing is booked or paid in the chat. No sign-in is needed.

## What is inside

- `.mcp.json` / `mcp.json`: the Unison Transfers MCP server, `https://mcp.unisontransfers.com.au/mcp` (no authentication,
  read-only): `get_transfer_quote`, `plan_airport_transfer`, `find_transfer_routes`, `get_transfer_prices`,
  `get_booking_link`, `get_quote_request_link`, `get_service_info`, plus a quote card (MCP Apps).
- `skills/`: six skills
  - `private-transfer-quote`: price and book a transfer between two places
  - `flight-pickup-planner`: pickup time from a flight, arrivals and departures
  - `cruise-terminal-transfers`: to and from the Brisbane International Cruise Terminal
  - `northern-nsw-to-queensland`: Byron Bay, Ballina, Tweed and Kingscliff to and from Queensland
  - `group-event-and-hourly-transport`: groups over 7, weddings, events, multi-stop and hourly hire (personal quote)
  - `international-visitor-transfers`: visitors from overseas: prices in their own currency, time zones, arrival

Trips that start and end in New South Wales cannot be booked (operator licence).

## Install

Claude Code: `/plugin marketplace add unisonfinance/unison-transfers-plugin`, then `/plugin install unison-transfers`.
Claude.ai: add the connector `https://mcp.unisontransfers.com.au/mcp` (Settings → Connectors).

Support: bookings@unisontransfers.com.au · 0401 605 940 · https://www.unisontransfers.com.au/contact
