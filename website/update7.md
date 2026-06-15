# Update 7 — Session VII (Up Through the Gray Garrison)

**Date:** 2026-06-07
**Driven by:** Chapter 7 / Session 7 landing
**Live page:** `/wrath` on the games site

## What changed

### `src/app/wrath/page.tsx` — Campaign Arc Status section (around line 412)

REPLACE-not-append, as always — this is a current-state window. The section was sitting at Session 6 state (party standing at the closed garrison doors). Advanced it to Session 7 (the garrison breached, two floors cleared).

- **Session label**: *Session VI → Session VII — The Worldwound Incursion* (umbrella subtitle unchanged)
- **Title (big gold heading)**: *The Blade That Chooses → The Threshold and the Bar* (Chapter 7's title)
- **Narrative paragraph**: rewritten — replaced the "doors are in front of them" summary with the interior breach: a house with no honest tenants, the cleaned shrine, two knights laid to rest, the recovered armory + adamantine warhammer, the Othirubo letter surfacing **Lord Staunton**, the fight up through both floors, Nageru run through and brought back, the wardstone fragment still above.
- **Terendelev "Fallen Guardian" card**: unchanged (standing memorial; the quote still holds).
- **All four PC contribution cards rewritten** per Session 7 beats:
  - **Caleth** — cleaned the shrine and read the hidden Celestial, spoke the passphrase that opened the temple armory, conjured water to douse burning allies, dimensional-slid through the crossfire and struck down the cultist who felled Nageru; still carries Quednys's rod, now plus the letter.
  - **Nageru** — first through every door, the spinning-kick that put an Abrikandilu through a wall, kicked the barred door off its brackets, lit his fists with the dragon's scale against the dretches, listened a displacement-tiefling out of the smoke; *took a glaive through the chest, went down, and rose* (his near-death is the card's weight).
  - **Thane** (POV chapter) — chimed the barred door, fire through the gap, read every threshold, trap-checked the passphrase-vault, stood guard at the knights' rite, **found the letter and read "Lord Staunton" aloud, filing it cold against an older one he carries** (subtle nod to the S. V. letter — readers in-the-know catch the thread; it is NOT spelled out), went first up the killing stair.
  - **Korroc** — cleaned a fouled shrine to a goddess not his own, took up the **adamantine First Crusade warhammer** with a prayer to both Torag and Iomedae and a borrowed sunburst shield, the demon's foulness broke on his faith, held the wall in the crossfire and would not let Nageru stay down.
- **Milestone box**: *The Doors of the Gray Garrison → Up Through the Gray Garrison*; subtitle *"Two floors taken — the wardstone fragment still waits above"*; paragraph rewritten for the floor-by-floor assault, the recovered armory/relic, the Staunton letter, and the still-unfound wardstone / still-cold rod / the stair at the end of the bloodied hall.
- **Book / Mythic Tier / Level footer**: **Book 1 / Mythic Tier 0 / Level 5.** The party leveled **4 → 5** (the DM advanced them a level after reading ahead in Book 1). Mythic Tier stays 0 — Mythic Tier 1 in this AP lands at the wardstone-shard climax, which the party has not reached. Footer and Vanguard line updated together.

### `src/app/wrath/page.tsx` — Vanguard section (around line 126)

- Updated to *"Level 5 Gestalt • Mythic Tier 0"* — kept in sync with the Status Box footer (the party leveled 4 → 5).

## Files NOT touched (relevant but intentionally unchanged)

- **The auto-loading "From the War Chronicle" section** — pulls from `/api/stories`; updates itself when a new chronicle entry posts.
- **The Vanguard character cards themselves** — names, classes, portraits, sheet links unchanged.
- **Hero, map, "Kenabres is Burning" transition, image gallery** — all unchanged.

## Verification

- `npm run dev` and visit `localhost:3000/wrath` (or the live site)
- Scroll past the "Kenabres is Burning" transition
- The arc-status section should now read **Session VII — The Worldwound Incursion / The Threshold and the Bar**
- Confirm the Vanguard section higher up shows *"Level 5 Gestalt • Mythic Tier 0"* and that it matches the Status Box footer (Book 1 / Mythic Tier 0 / Level 5) at the bottom of the arc-status section
- The "From the War Chronicle" section below auto-pulls independently of this update

## Cross-references

- Chapter that drove this update: `wrath-story-book/chapters/07-no-honest-tenants.md`
- Session notes: `wrath-story-book/sessions/session7.md`
- Pattern reference: `website/update4.md` (the prior changelog) and the live section itself

## Housekeeping notes (not blocking)

- **`memory/webpage-session-section.md` is missing.** Both `CLAUDE.md` and the inline page comment (line 412) reference it as the design-pattern source, but the file no longer exists in the memory dir. The live section is currently the only record of the pattern. Worth recreating from this section, or updating the references.
- **`website/update5.md` and `update6.md` were never written** — only `update4.md` existed before this file. The live page was advanced through Session 6 without matching changelogs. Update 7 resumes the practice; the 5/6 gap is documented here rather than backfilled.
