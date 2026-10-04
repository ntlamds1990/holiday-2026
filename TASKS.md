# Holiday Planner — Session Handoff
**Last updated: 4 Oct 2026**
**Live at: https://ntlamds1990.github.io/holiday-2026/**

---

## What the planner is

A self-contained single-page HTML trip execution tool for an 18-day family holiday (14 Dec 2026 – 1 Jan 2027): Singapore → NYC → Fort Worth → Orlando (Universal + Epic Universe + Disney) → Vermont → Boston → NYC → Singapore. Five travellers: Nicholas, Cheryl, Evan (9), Elena (7), newborn.

Everything is embedded in one file (`index.html`) — no build step, hosted on GitHub Pages from the `master` branch root.

---

## What was built this session

### UX batch
- FAB buttons (💰 Spend, 🌐 Tools) moved from header to fixed bottom-right stack
- Nav strip: city group labels (NYC / DFW / Orlando / Disney / Vermont / Boston) above each leg's date pills
- Tools panel: overflow fixed, height converter split to 2 rows, `overflow-x: hidden`
- Weather panel: shows current conditions + 3-day forecast (hi/lo + midday description) from wttr.in
- Swipe-to-dismiss: drag-down gesture on both Tools and Spend panels
- Flight cards: Flightradar24 track buttons per flight; boarding pass + check-in links
- Manual ↺ refresh button in header (workaround for fixed-layout blocking pull-to-refresh)

### Data updates (Budget_10 → _11)
- **Dec 16**: Added JFK T8 lunch (Shake Shack / Dos Toros)
- **Dec 17**: Added hotel breakfast, Reata Restaurant dinner; swapped Gaylord Texan → Fort Worth Museum of Science and History; Trinity Metro transit plan; added Reata reservation doc slot
- **Dec 18**: Added hotel breakfast, Bluebonnet Café zoo lunch
- **Dec 22**: EPCOT meals updated to call out World Showcase food pavilions
- **Dec 26**: Added The Family Table reservation doc slot
- **Dec 29**: Added Regina Pizzeria dinner; updated Marriott Gold breakfast note; cannoli renamed to Treat
- **Dec 31**: Added ATRIO Conrad breakfast

### Section reviews completed (1–9)
All nine sections reviewed and signed off:
1. Header — countdown + day summary
2. Hero — city gradients + Unsplash images
3. Plan/Timeline — timings, map links, Disney LL strategy
4. Lodging — check-in day prominent cards
5. Flights — boarding pass, check-in, track buttons
6. Meals — all gaps filled
7. Documents — missing reservation slots added (Tavern on the Green, Reata, Family Table)
8. Expense modal — reviewed, no changes needed
9. Spend panel — thousands separators, SGD equivalent, individual committed items with sub-rows, Pre-paid section on relevant day pages

### Pre-paid sections on day pages
Big-ticket committed costs (hotel check-ins, flights, activity tickets, Hertz) now appear as a "Pre-paid" section on the relevant day page, so the cost of what you've already paid for shows up in context on the day itself.

### Dec 22 EPCOT strategy
Full two-park day timeline built out:
- 07:00 LLMP opens (book Frozen Ever After first)
- 08:30 Early Entry: Frozen Ever After → Remy's
- 09:15 Guardians LLSP + Test Track + Soarin' (LLMP stack)
- 12:30 World Showcase food walk (France/Norway/Japan/Germany, ~2.5–3 hrs)
- 15:00 Hard departure to Magic Kingdom via Disney bus
- 16:00 MVMCP early entry (2 hrs before party)
- 19:00 Party: parade (twice), Holiday Wishes fireworks, character meets, free cookies/cocoa

---

## What's left — code

### 1. Theme park ride strategies (the main remaining work)
Three park days still need the same treatment Dec 22 got. For each: fix timeline order, add ride strategy with LL guidance, add any practical notes (height checks, entry timing, etc.).

**Dec 19 — Universal Studios Florida + Islands of Adventure**
- 2-park day, Express Unlimited included via Royal Pacific
- Hagrid's Motorbikes is Express-exempt — must rope-drop
- Elena height (~51.2") is marginal for VelociCoaster (51" min) — flag clearly
- Hogwarts Express connects the two parks (one direction each ticket type)
- Current timeline is thin — needs ride order and practical notes

**Dec 20 — Epic Universe**
- Early Park Admission (1 hr, Royal Pacific perk) — Super Nintendo World first
- Separately purchased Express Passes in play (not hotel-included)
- Dark Universe deprioritised (no EPA, longest waits, less relevant for 7-year-old)
- Current timeline reasonable but could use more specific ride guidance

**Dec 21 — Hollywood Studios**
- Rise of the Resistance LLSP (purchased Dec 14, 7-day window)
- LLMP stack: Slinky Dog, Smugglers Run, Tower of Terror
- Timeline is decent but could be tightened

### 2. Link booking documents
All `doc:null` placeholders need real URLs once confirmations are to hand. This is content, not code — paste Google Drive or booking confirmation links into the relevant `doc:` fields in `index.html`.

Priority order:
- Hotel receipts (`lodging.doc` on each check-in day)
- Flight boarding passes (`flights[].doc` on each flight day)
- Activity ticket confirmations (`docs[]` on activity days)

---

## What's left — actions (outside the planner)

| Date | Action |
|------|--------|
| **7 Oct 2026** | Worthington Renaissance Fort Worth — confirm self-funded cost split. Update `LOCKED_COSTS` in `index.html` and remove the amber TBC warning from Spend panel |
| **15 Oct 2026** | Tavern on the Green reservation opens — book it, then add the confirmation link to Dec 15 docs |
| **ASAP** | Top of the Rock — book timed entry at rockefellercenter.com (holiday slots sell out) |
| **ASAP** | Statue of Liberty ferry — book earliest morning slot (9:00–10:00am) at statuecitycruises.com |
| **ASAP** | One World Observatory — book ~3:30–3:45pm slot at oneworldobservatory.com for sunset views |
| **1 Nov 2026** | Smugglers' Notch ski camp + gear rental booking window opens — book both |
| **14 Dec 2026** | Rise of the Resistance LLSP — 7-day window opens at 7am ET (in-flight on SQ24 — use WiFi or buy on landing) |
| **15 Dec 2026** | Guardians: Cosmic Rewind LLSP — 7-day window opens at 7am ET |
| **21 Dec 2026** | Hollywood Studios LLMP — buy at 7am day-of |
| **22 Dec 2026** | EPCOT LLMP — buy at 7am day-of (Frozen Ever After first) |

---

## Key technical notes for next session

- **File**: `C:\Users\ntlam\OneDrive\Documents\04_Work & Projects\Active Projects\holiday-planning\index.html`
- **Branch**: `master` — push directly to deploy to GitHub Pages
- **Budget spreadsheet**: lives on Google Drive, accessible via MCP. Latest version: `Family_Trip_Budget_11.xlsx` (file ID: `1rezhrjBe-jB9mkeWA_KKZwlJrV76tbgQ`)
- **LOCKED_COSTS total**: ~$32,734 USD committed. Worthington excluded (TBC).
- **Currency API**: `open.er-api.com/v6/latest/USD`, 5-min cache, shared between Tools and Spend panels
- **Expense storage**: `localStorage` key `holiday2026_exp`
- **All doc fields are `null`** — structure is ready, links just need to be pasted in

---

## 3-line session close
- Built and pushed 9 section reviews, UX batch, Budget_10/11 data sync, pre-paid day sections, and full EPCOT strategy
- Next: theme park strategies for Dec 19 (Universal), Dec 20 (Epic Universe), Dec 21 (Hollywood Studios), then document linking
- No blockers — Worthington cost is the only open financial item (reminder 7 Oct)
