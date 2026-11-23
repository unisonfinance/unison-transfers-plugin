---
name: northern-nsw-to-queensland
description: Private transfers between Northern NSW and Queensland. Use when someone in or going to Byron Bay, Ballina, Lennox Head, Bangalow, Kingscliff, Casuarina, Salt Village, Cabarita Beach, Pottsville, Tweed Heads, Murwillumbah, Brunswick Heads, Mullumbimby, Suffolk Park, Yamba or a Byron hinterland retreat needs a car to or from Gold Coast Airport (OOL), Brisbane Airport (BNE), the Brisbane cruise terminal, Brisbane, the Gold Coast or the Sunshine Coast.
---

# Northern NSW ⇄ Queensland transfers

## The licence rule (always apply)

Unison Transfers is licensed for trips that **start or end in Queensland**:

- Byron Bay → Gold Coast Airport: yes. Brisbane Airport → Kingscliff: yes. Casuarina → Brisbane cruise terminal: yes.
- Byron Bay → Ballina Airport, Kingscliff → Byron Bay, Tweed Heads → Lennox Head: **no** (starts and ends in NSW).

When a trip is NSW-to-NSW, say plainly that this operator cannot carry it and stop. Do not suggest splitting the
trip or routing through Queensland.

## Workflow

1. Identify both ends. Many Byron-area travellers fly into Gold Coast Airport (OOL, about 1 hour from Byron Bay) or
   Brisbane Airport (BNE, about 2 hours); if they have not chosen an airport, price both with two
   `get_transfer_quote` calls so they can compare.
2. **Call `get_transfer_quote`** with the places, `date`, `time`, `passengers`, `bags`. For a flight, use the
   `flight-pickup-planner` skill.
3. Present the vehicles, prices and drive time from the result, and the booking link.
4. Retreats (Gaia, Crystal Creek, Elements of Byron and others): use the retreat name as the place; for a group
   arriving together, price the V-Class or use `get_quote_request_link` for more than 7.

## Do not

- Do not quote NSW-to-NSW trips under any wording.
- Do not invent drive times; the tool returns them.
