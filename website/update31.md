# Session 31 — The Face I Wear (Book 4 opens)

**Date:** 2026-11-21
**Driven by:** `chapters/31-the-face-i-wear.md` (Nageru POV) and `sessions/session31.md`
**Live page:** `/wrath` (route served from `G:\Projects\games\src\app\wrath\page.tsx`)

**Book 3 → Book 4.** The table has finished Book 3, the GM's between-books interlude (Ch 30.5) is done, and Session 31 opens *The Midnight Isles*. The milestone footer now reads `Book 4 of 6`. The Book 4 adventure-log page itself was already updated by Will; this pass touched only `/wrath`.

**No level or tier change.** Still **Level 12, all four Mythic 5**: the Vanguard header stays `Level 12 Gestalt · Mythic 5`, no per-card `tier`, footer `Mythic Tier 5 · Level 12`.

---

## What changed

### `G:\Projects\games\src\app\wrath\page.tsx`

**Theater of War — Citadel Drezen map pin (~line 205)**
- Was: turned inside out, the impostor gone, every room searched and nothing found.
- Now: held; the thing that wore the wizard's face is in the strongest cell under the citadel and nobody may talk to it; the Queen came and left within the week, west, with the knights.
- Other six pins (Temple of Irori, Delamere's Tomb, Eagle Rock, Vilareth Ford, Wintersun Hall, the Molten Scar) **unchanged and checked**; nothing in Session 31 touches them.
- **No pin for the Midnight Fane.** It is about 240 miles west, across the whole Worldwound, well off the edge of this regional map (`worldwound-map3-1.jpg` covers the country around Drezen). A Fane pin would need a wider map.

**Theater of War — sidebar "Citadel Drezen" briefing (~line 276)**
- Replaced: the impostor caught (found by scrying in a knight's face, leading the wizard and the demon toward a bounty, "a mercenary… very good at what it does"), and the Queen in and out with a few dozen paladins and two copper plates.

**Theater of War — Commander's Note (~line 283)**
- Replaced: Irabeth on the monk carrying his own face up to her floor, never before having to ask which of two men was real, and being left with a fortress and a thing in a cell that smiles when asked how it fooled them.

**Campaign Arc Status — session header**
- Top label: `Session XXX — Is That Really You This Time` → **`Session XXXI — The Midnight Fane`**
- Gold title: `What Came Back Clean` → **`The Face I Wear`** (the chapter title)

**Campaign Arc Status — narrative paragraph**
- Replaced: the impostor found in a borrowed face, the Queen's errand (close the crystal rift with the four as the power and someone on the Abyss side when it shuts), and the walk in through the Fane's front doors. Inline span `the Midnight Fane` with `{" "}` on both sides.
- It says "one of the knights' own" face without naming Nageru, and does not say who will go through the rift (not decided).

**Campaign Arc Status — Terendelev card**
- **Considered and left unchanged.** Last session's quote (her century as a plain woman in Kenabres; *"she was better than she looked, not worse"*) is about faces that are not what they seem, which is still exactly this session's motif, and it passes the card's hard rule (delete her name and it is not a recap). Refreshing it this week would only have made it more about the doppelganger.

**Campaign Arc Status — four party cards (all replaced)**
- **Caleth — "The One Who Read the Plates"**: the hour over the basin, the fold without asking, spitting in the cell, and reading every language on the copper plates (*"Nobody yet knows why."*).
- **Nageru — "The One Who Fought Himself"**: his own face in the water, one miss and two held blows, carrying himself through the gate, "never speak to it," vouching for the demon in one sentence, and a promise that holds if it serves her.
- **Thane — "The One Who Asked How They Get Back"**: the cipher, the portable hole and the wrong bag, the only question in the room, and the Fane's front doors.
- **Korroc — "The One Who Struck Exactly Hard Enough"**: the axe back off the wall, three measured blows on the thing that fooled his sight and a long moment looking at nothing, the anti-magic cell, and the axe dropped into Thane’s portable hole for some peace.
- Lengths in line with the Session 30 set. **Kept off the page:** Nageru's private reason it was his face, the uncle, Korroc's Kenabres cellar, the unlaid life link.

**Campaign Arc Status — milestone box**
- Status title: `The Fortress Searching Itself` → **`Inside the Midnight Fane`**
- Subtitle: → **`The impostor caged · The Queen's errand · An audience with no name`**
- Summary replaced: the Queen a mile out with her paladins in enemy marks; the Locust Lord statue, the giant, the incubus's audience; the packing floor; the elixir room; and the woman in Iomedae's armor with the face of a paladin `dead for decades` (inline span, `{" "}` before; the period follows directly). **Yaniel is not named on the page**, so the cliffhanger stays in the chapter.
- **Footer:** `Book 3 of 6` → **`Book 4 of 6`**. Tier and level unchanged.

---

## Files NOT touched

- **The Vanguard section (~lines 115–160)** — no level or tier change; header and sync comment still correct.
- **`{/* FROM THE WAR CHRONICLE */}`** — auto-loads the latest dispatch from `/api/stories?campaign=wrath&limit=1`.
- **Hero, Worldwound divider, Kenabres section, Visions galleries** — static.
- **Map art and all pin coordinates** — only the Drezen tooltip copy changed.
- **`.codex-remote-attachments/`** — untracked, left alone as before.

---

## Verification

1. Run the games site with the `games-dev` configuration (port 3000) and open `http://localhost:3000/wrath`.
2. **The Vanguard** header: **LEVEL 12 GESTALT · MYTHIC 5**.
3. **Theater of War** — the Drezen pin tooltip begins *"Held. The thing that wore the wizard's face…"*; the sidebar begins *"The impostor is caught."*; the Commander's Note begins *"The monk carried it up the hill…"*
4. **Campaign Arc Status** label **SESSION XXXI — THE MIDNIGHT FANE**; gold title **The Face I Wear**.
5. Cards: **THE ONE WHO READ THE PLATES / THE ONE WHO FOUGHT HIMSELF / THE ONE WHO ASKED HOW THEY GET BACK / THE ONE WHO STRUCK EXACTLY HARD ENOUGH**.
6. Milestone **INSIDE THE MIDNIGHT FANE**; footer **BOOK 4 OF 6 | MYTHIC TIER 5 | LEVEL 12**.
7. Word-jam check: *"the front doors of the Midnight Fane and were told"* and *"the face of a paladin dead for decades."* read with normal spacing.
8. **Results this pass:** the rendered text of the whole Campaign Arc Status section, the Drezen sidebar and the Commander's Note was read back from the running page and matches the source; steps 2–7 check out; **no console errors.** `npx tsc --noEmit` reports 12 errors, **all pre-existing and outside `page.tsx`** (Playwright test typings, `src/lib/supabase.ts`); the count is identical with this change stashed.

---

## Cross-references

- Design pattern: `wrath-story-book/memory/webpage-session-section.md`
- Chapter: `wrath-story-book/chapters/31-the-face-i-wear.md`
- Session notes: `wrath-story-book/sessions/session31.md`
- Mission canon: `wrath-story-book/memory/midnight-fane-and-the-abyss-mission.md`
