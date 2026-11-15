# Session 30 — What Came Back Clean

**Date:** 2026-11-15
**Driven by:** `chapters/30-what-came-back-clean.md` (Korroc POV) and `sessions/session30.md`
**Live page:** `/wrath` (route served from `G:\Projects\games\src\app\wrath\page.tsx`)

**No level or tier change.** The party is still **Level 12, all four Mythic 5**, so the page keeps the single-header shape: the Vanguard header stays `Level 12 Gestalt · Mythic 5`, there is still no per-card `tier` field, and the milestone footer stays `Mythic Tier 5 · Level 12`. Nothing in the Vanguard section was touched this pass.

**The session's reveal drove the whole update.** The Aravashnial the party brought home in Session 24 and lived with for two months was an impostor, and it walked out of Citadel Drezen hours before they got back. That is now the subject of the status box, the Drezen map pin, the sidebar briefing and the Commander's Note — four places that all previously described a fortress calmly holding its ground while the knights were away.

**Book number stays at 3** — asked and confirmed (Will, 2026-11-15). The table has just finished Book 3 and the GM runs an interlude when switching books; the footer reads `Book 3 of 6` until that interlude happens.

---

## What changed

### `G:\Projects\games\src\app\wrath\page.tsx`

**Theater of War — Citadel Drezen map pin (~line 205)**
- Was: held, the axe on Irabeth's table, engineers west after the bell, the knights gone southwest with a demon guiding them.
- Now: the knights are back, a starved elf is in the infirmary, the fortress searched every room between dusk and dawn and found nothing.
- Other seven pins (Temple of Irori, Delamere's Tomb, Eagle Rock, Vilareth Ford, Wintersun Hall, the Molten Scar) **unchanged and checked** — none of them moved this session, and nothing in Session 30 contradicts them.
- **No pin was added for the Green Gate / Ivory Sanctum.** The place is explicitly a blank spot on the in-fiction map, and pin positions have to be derived visually against the art rather than guessed. If you want one, it needs a look at `worldwound-map3-1.jpg` first.

**Theater of War — sidebar "Citadel Drezen" briefing (~line 276)**
- Was: the demon naming the Green Gate, twenty people sent west for the bell, the knights leaving at dawn.
- Now: the Sanctum is cleared and abandoned; the wizard who came back has been caged since the spring; the version that advised the fortress for two months was something else wearing his face, and it left before they arrived. Closes on Aron having ridden four hours beside it that morning talking about a bell.

**Theater of War — Commander's Note (~line 283)**
- Was: Korroc's axe lent to Irabeth, hung where it can see the door.
- Now: Irabeth on ordering every room in the citadel opened and not knowing what she told them to look for. *"It argued with me about the eastern bridge. Four of the best people I have, two of them sworn paladins, looked straight at it and saw nothing. So I will not be telling my soldiers to watch for anything in particular. I will be telling them to watch."*
- The axe is still canonically on her table; it just stopped being the most interesting thing in the fortress.

**Campaign Arc Status — session header**
- Top label: `Session XXIX — No More Games` → **`Session XXX — Is That Really You This Time`**
- Gold title: `The Center of the Fire` → **`What Came Back Clean`** (matches the chapter title)

**Campaign Arc Status — narrative paragraph**
- Replaced entirely. Walks the rooms in the order the party walked them (the iron circle, the web cavern, the dissection room, the silent cages) and lands on the find in the third cell and the question it opens. Inline span is now `Citadel Drezen` with `{" "}` on both sides.

**Campaign Arc Status — Terendelev card**
- **Refreshed, and deliberately kept about her.** The previous quote was the silver scales and the dwarves using theirs to drift down cliffs; good, but a year old in feel and unconnected to the present moment.
- The new one is her century in Kenabres as a plain woman in gray traveling clothes, and the fact that the only people who ever learned what she was learned it in the half-second before she died for them. One closing clause ties to the session — men in this company flinching at faces now — and the point of it is that **the first disguised thing any of them met was better than she looked, not worse.**
- Checked against the card's hard rule: delete her name and it does not read as a recap of Session 30. It reads as a paragraph about a dragon.

**Campaign Arc Status — four party cards (all replaced)**
- **Caleth — "The One Who Saw It Happen"**: the mark taking hold at the cell-block door, the four-or-five-breath absence, telling the party the vision in order without his voice changing, putting the orders down and asking Thane instead, and picking the burned robes up off the floor.
- **Nageru — "The One Who Said It Plainly"**: the acid breath nobody had seen in a year (*"it is old"*), four misses and then four inches of back foot, and the rock in the gorge — *"we did everything there is to do. There was nothing to find."*
- **Thane — "The One Who Asked First"**: saying what nobody wanted said, being moved by being asked rather than ordered, the collar off in ten minutes on a year of self-taught Abyssal, and taking the tongs out of Korroc's hand — *"I'm not a paladin either."*
- **Korroc — "The One Who Could Not Put It Down"**: finding the elf by feel through the silence, the five stones, the last rites in two languages, and the hand he could not lower.
- Lengths are in line with previous passes; no card got longer than the Session 29 set.

**Campaign Arc Status — milestone box**
- Status title: `Rooms` → **`The Fortress Searching Itself`**
- Subtitle: → **`The Sanctum emptied · The prisoner home · Something loose in Drezen`**
- Summary replaced: the carpet, the one waking question, the cup still cool in the empty study, and a citadel awake and looking for something it cannot describe. Inline span is `this time`, with `{" "}` on both sides.
- **Footer unchanged**: `Book 3 of 6 | Mythic Tier 5 | Level 12`.

---

## Files NOT touched

- **The Vanguard section (~lines 115–160)** — no level or tier change this session, and the header already reads `Level 12 Gestalt · Mythic 5`. The sync comment there is still correct.
- **`{/* FROM THE WAR CHRONICLE */}` (~line 562)** — auto-loads the latest dispatch from `/api/stories?campaign=wrath&limit=1`. Nothing to edit by hand.
- **Hero, Worldwound divider, Kenabres section, Visions galleries** — static, unaffected by this session.
- **The map art itself** (`worldwound-map3-1.jpg`) and all pin coordinates — only the Drezen tooltip copy changed; no pin moved.
- **`.codex-remote-attachments/`** — untracked, left alone as in previous passes.

---

## Verification

1. Run the games site with the `games-dev` configuration (port 3000), then open `http://localhost:3000/wrath`.
2. **The Vanguard** header should still read **LEVEL 12 GESTALT · MYTHIC 5**, with no Mythic Tier line on the character cards.
3. **Theater of War** — hover the blue pin on Citadel Drezen; the tooltip should begin *"Held, and turned inside out."* The sidebar beneath should begin *"The Ivory Sanctum is cleared and abandoned."*
4. **Campaign Arc Status** top label: **SESSION XXX — IS THAT REALLY YOU THIS TIME**. Gold title: **What Came Back Clean**.
5. Four cards: **THE ONE WHO SAW IT HAPPEN / THE ONE WHO SAID IT PLAINLY / THE ONE WHO ASKED FIRST / THE ONE WHO COULD NOT PUT IT DOWN**.
6. Milestone box: **THE FORTRESS SEARCHING ITSELF**. Footer: **BOOK 3 OF 6 | MYTHIC TIER 5 | LEVEL 12**.
7. Word-jam check: *"sitting in his chair in Citadel Drezen since the spring"* and *"whether it was really them this time, and to be calmed"* should both read with normal spacing.
8. **Results this pass:** rendered page text for the whole Campaign Arc Status section and the Drezen pin was read back and matches the source; the browser console showed **no errors**; steps 2–7 all check out.
9. ⚠ `npx tsc --noEmit` reports **12 errors, none in `page.tsx`** — `@playwright/test` is not installed (`playwright.config.ts`, `tests/browser/upgrade.spec.ts`) and `src/lib/supabase.ts:16` passes a `retry` option the current Supabase types reject. **These are pre-existing and unrelated to this pass**, but note that `webpage-session-section.md` records tsc as returning zero errors as of Session 23 — so they arrived since then and are worth a look on their own time.

---

## Cross-references

- Design pattern and update process: `wrath-story-book/memory/webpage-session-section.md`
- Chapter that drove this update: `wrath-story-book/chapters/30-what-came-back-clean.md`
- Session notes: `wrath-story-book/sessions/session30.md` (including the dated appendix of table rulings)
- The impostor, the rescue and the failed transfer: `wrath-story-book/memory/aravashnial-taken.md`
- The new crystal/elixir canon: `wrath-story-book/memory/nahyndrian-elixir-and-crystals.md`
- Previous pass: `wrath-story-book/website/update29.md`
