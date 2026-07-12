# Session 10 — The House That Beauty Built
**Date:** 2026-06-28
**Driven by:** Chapter 10 written; saboteur thread introduced; party leveled to 7
**Live page:** `/wrath`

## What Changed

### `games/src/app/wrath/page.tsx` — Campaign Arc Status section (~line 412)

- **Session header**: "Session IX — Sword of Valor" → "Session X — Sword of Valor"
- **Gold title**: "The Voice That Answers" → "The House That Beauty Built"
- **Narrative paragraph**: Replaced entirely. New text covers the sabotaged wagon, the chapel clearing (gargoyles, ghouls, demons), the consecration/Radiance power-up, and the shadowblood/clean-sweep threat
- **Terendelev card**: Quote refreshed — now reflects the Worldwound's wrongness and the chapel that still stood in it, rather than the march north
- **Party contribution cards**: All four replaced:
  - Caleth: role updated to "The Painter's Fury" — sabotage discovery, fireball-in-anger, inverted scorching ray, chapel consecration, Radiance powering up
  - Nageru: role updated to "The Thunder's Reach" — staircase climb, gargoyle spotting, enlarged by Caleth, spear throws with smite-light
  - Thane: role unchanged "Shadow of Judgment" — scouting, lock-picking, invisibility, shadowblood discovery, camp sweep finding nothing
  - Korroc: role unchanged "The Wall That Walks" — levitated on dragonscale, Stonelord skin turning claws, tanking the large demon, wanting the drug destroyed
- **Status box**: "The March on Drezen" → "The Enemy Within"; subtitle updated to "The road to Drezen · A saboteur unseen"; summary emphasizes the internal threat
- **Footer**: Level 6 → Level 7; Book and Mythic Tier unchanged (2 / 1)

### `games/src/app/wrath/page.tsx` — Vanguard section (~line 126)

- **Level updated**: "Level 6 Gestalt • Mythic Tier 1" → "Level 7 Gestalt • Mythic Tier 1" — now in sync with status box footer

## Files NOT Touched

- **"From the War Chronicle" section** — auto-loads latest entry from API; no manual edit needed
- **Hero section, map section, gallery, footer** — no changes relevant to Session 10
- **Vanguard character cards** — class lines unchanged

## Verification

1. Load `/wrath` locally or on the live site
2. Scroll to the Campaign Arc Status section — confirm it reads "Session X — Sword of Valor" with gold title "The House That Beauty Built"
3. Check all four contribution cards reflect Session 10 events
4. Check status box footer reads "Book 2 of 6 | Mythic Tier 1 | Level 7"
5. Scroll up to the Vanguard section header — confirm "Level 7 Gestalt • Mythic Tier 1" matches

## Cross-References

- Design pattern: `wrath-story-book/memory/webpage-session-section.md`
- Chapter: `wrath-story-book/chapters/10-the-house-that-beauty-built.md`
- Session notes: `wrath-story-book/sessions/session10.md`
