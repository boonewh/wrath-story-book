# Session 11 — The Latch That Held
**Date:** 2026-07-05
**Driven by:** Chapter 11 written; Ahari Gorge / Vescavor queen; Aravashnial revealed as Riftwarden; Drezen blueprints from the Stonevein parents; assault on Drezen imminent
**Live page:** `/wrath`

## What Changed

### `games/src/app/wrath/page.tsx` — Campaign Arc Status section (~line 412)

- **Session header** (~line 418): "Session X — Sword of Valor" → "Session XI — Sword of Valor"
- **Gold title** (~line 419): "The House That Beauty Built" → "The Latch That Held"
- **Narrative paragraph** (~lines 425–435): Replaced entirely. New text covers the Ahari Gorge halt, the Vescavor swarms and the descent beneath the riverbed, the killing of the queen, the Abyssal rift and the vrocks, Aravashnial revealing himself as a Riftwarden and sealing the rift, the saboteur's near-fatal ambush of scout Aron Kir, and the sealed satchel from Queen Galfrey containing the reconstructed Drezen blueprints signed by the Stonevein parents. Ends on the army within striking distance and the assault at dawn.
- **Terendelev card** (~lines 445–450): Quote refreshed — now reflects Korroc drifting down into the nest on the scale's silver light, and the recurring cost/comfort of spending the dragon's dying gift each time a scale wakes. Same elegiac register.
- **Party contribution cards** (~lines 455–479): All four replaced. `name` and `classes` fields unchanged; `role` strings kept as earned:
  - **Caleth** — role unchanged "The Painter's Fury": fireball turned to ice, ally turned invisible under vrock claws, three Radiance thrusts, blinking three companions through solid stone, carrying the blueprints in his spellbook.
  - **Nageru** — role unchanged "The Thunder's Reach": spotting the silent tunnel-mouth, the running kick at the ice-burst, taking the queen's acid, holy-smite fists on two vrocks, reviving the dying scout by hand.
  - **Thane** — role unchanged "Shadow of Judgment": scouting point through the nest, moving before the ice burst, stunned and rising under a vrock, reading the drag-trail and gnome-sized prints, slamming the evidence on the war-council table, reading his father's handwriting.
  - **Korroc** — role unchanged "The Wall That Walks": drifting into the nest on dragonscale light, planting himself between wizard and demons, flinging mythic protection to his stunned cousin, his life-bond drinking the party's wounds, hearing his parents' names read off the letter.
- **Status box** (~lines 493–501): title "The Enemy Within" → "The Eve of Drezen"; subtitle "The road to Drezen · A saboteur unseen" → "Striking distance · A traitor still unnamed"; summary replaced — gorge cleared, rift sealed, blueprints in hand, assault at dawn, saboteur still unfound (suspicion has a shape now — small, quick — but no proof).
- **Footer** (~lines 504–508): UNCHANGED — Book 2 of 6 | Mythic Tier 1 | Level 7.

### `games/src/app/wrath/page.tsx` — Vanguard section (~line 126)

- **NOT touched.** Already reads "Level 7 Gestalt • Mythic Tier 1" from Session 10. Level and Mythic Tier are unchanged for Session 11, so no edit was needed. Verified in sync with the status-box footer.

## Files NOT Touched

- **Vanguard section header (~line 126)** — no level/tier change this session; already in sync.
- **"From the War Chronicle" section** — auto-loads latest entry from API; no manual edit needed.
- **Hero section, map section, gallery, Vanguard character cards, footer** — no changes relevant to Session 11.

## Guardrails Observed

- No secrets leaked: nothing about Caleth's lineage/Riftwarden-orphan status, nothing hinting Caleth already knew Aravashnial's identity. Aravashnial's Riftwarden reveal is presented as it plays publicly in Chapter 11.
- The saboteur is kept as "suspicion without proof" — **Nurah is not named anywhere on the page**. The chapter carries the specifics.
- Name spellings verified: Aravashnial, Vescavor, Aron Kir, Drezen, Terendelev, Stonevein.

## Verification

1. Load `/wrath` locally or on the live site.
2. Scroll to the Campaign Arc Status section — confirm it reads "Session XI — Sword of Valor" with gold title "The Latch That Held".
3. Check the narrative paragraph, Terendelev quote, and all four contribution cards reflect Session 11 events.
4. Check the status box reads "The Eve of Drezen" / "Striking distance · A traitor still unnamed".
5. Check the status box footer reads "Book 2 of 6 | Mythic Tier 1 | Level 7".
6. Scroll up to the Vanguard section header — confirm "Level 7 Gestalt • Mythic Tier 1" still matches (no edit needed).
7. Confirm the word "Nurah" appears nowhere on the page.

## Cross-References

- Design pattern: `wrath-story-book/memory/webpage-session-section.md`
- Chapter: `wrath-story-book/chapters/11-what-the-stone-remembers.md`
- Session notes: `wrath-story-book/sessions/session11.md`
- Prior changelog: `wrath-story-book/website/update10.md`
