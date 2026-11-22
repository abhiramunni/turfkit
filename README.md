# TurfKit — Book the turf. Split the bill. Run the game.

A single-file web app for Bengaluru's 5-a-side and 7-a-side football players. Find a turf with real listed hourly rates, plan the slot, set the formation on a pitch board, split the cost per head, and keep a match log — all on-device, no signup, no backend.

**Live:** https://abhiramunni.github.io/turfkit/

## What it does

- **Find a turf** — 8 turfs across Jayanagar, Basavanagudi, JP Nagar, HBR Layout, Electronic City and Whitefield, with hourly rates from public listings (October 2026), formats, hours and phone numbers. Filter by area and format, sort by price.
- **Next-game scoreboard** — live countdown to kick-off (seeded with Sunday 22 Nov 2026, 6:00 PM, Jayanagar).
- **Plan a game** — pick a turf, date, start-time slot and duration; the bill shows the rate, total and per-head share instantly (evening rates cost more, mornings are cheapest). Save the game to update the scoreboard.
- **Formation board** — a pitch diagram with 5-a-side (1-2-1) and 7-a-side (1-3-2) formations. Tap a spot, tap a player to place them. Squad manager with add/remove.
- **Split the cost** — enter what each player actually paid; the app shows who owes, who overpaid and who is settled, with a copyable summary for the group chat.
- **Match log** — log scores, scorers and player of the match; win/draw/loss tally builds up over the season.
- **Match-day kit checklist** — 8 items with a progress ring.
- **Guides** — 6 plain-language guides: turf etiquette, shoes vs studs, warm-up, what to carry, splitting fairly, booking tips.

## How it works

Everything is one self-contained `index.html` (plus two photos). All data is stored in `localStorage` under `turfkit-v1` — nothing leaves the device. Sample squad, matches and kit state are seeded on first run and can be removed with "Remove samples"; "Erase everything" resets to a clean slate.

Rates are indicative, from public listings in October 2026 — always confirm with the turf before booking. TurfKit does not take bookings; call the turf to lock your slot.

## Files

- `index.html` — the app (single file; photos are repo-root `.webp` files it references)
- `turfkit-hero.webp` — floodlit turf hero photo
- `turfkit-flatlay.webp` — match-day kit flat-lay photo
- `README.md` — this file

## Build notes

Source is split into `chunks/c01–c16` and assembled with `build.py` (embeds the two photos as base64 for local QA). `make-publish.py` swaps the base64 back out for the repo-root `.webp` files to keep the published `index.html` small. QA is `qa-test.js` (headless jsdom assertions).
