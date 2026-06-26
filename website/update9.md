# Session 9 — The Voice That Answers
**Date:** 2026-06-21
**Driven by:** Chapter 9 written; Book Two (Sword of Valor) has begun
**Live page:** `/wrath`

## What Changed

### `games/src/app/wrath/page.tsx` — Campaign Arc Status section (~line 412)

- **Session header**: "Session VIII — The Worldwound Incursion" → "Session IX — Sword of Valor"
- **Gold title**: "The Stone Remembers" → "The Voice That Answers"
- **Narrative paragraph**: Replaced entirely. New text covers Queen Galfrey's arrival, the knighting, the Drezen mission, the march north, Vilareth Ford, and Keeper's Canyon
- **Terendelev card**: Quote refreshed — now reflects the march north from the city she died to protect, rather than the wardstone visions
- **Party contribution cards**: All four replaced:
  - Caleth: cold-forged fireballs, dimensional slides, the rare smile at "only nine"
  - Nageru: role updated to "The Voice That Answers" — spoke first to the Queen, recruited the company, one-hit incubus kill, gave the paladins moral clarity on looting
  - Thane: role unchanged — scouted the entire march, demon-slaying arrow, signal arrow misdirection
  - Korroc: role updated to "The Wall That Walks" — horse refusal, life-bond, healing waves, the count of nine
- **Status box**: "The Worldwound Incursion — Complete" → "The March on Drezen"; subtitle updated to "Book Two begun"; summary reflects the road ahead to Drezen and the Sword of Valor
- **Footer**: Book 1 → Book 2; Level and Mythic Tier unchanged (6 / 1)

### `games/src/app/wrath/page.tsx` — Vanguard section (~line 126)

- **No change** — Level 6 Gestalt • Mythic Tier 1 remains correct and in sync with the status box footer

## Files NOT Touched

- **"From the War Chronicle" section** — auto-loads latest entry from API; no manual edit needed
- **Hero section, map section, gallery, footer** — no changes relevant to Session 9
- **Vanguard character cards** — class lines unchanged (no level-up this session)

## Verification

1. Load `/wrath` locally or on the live site
2. Scroll to the Campaign Arc Status section — confirm it reads "Session IX — Sword of Valor" with gold title "The Voice That Answers"
3. Check all four contribution cards reflect Session 9 events
4. Check status box footer reads "Book 2 of 6 | Mythic Tier 1 | Level 6"
5. Scroll up to the Vanguard section header — confirm "Level 6 Gestalt • Mythic Tier 1" matches

## Cross-References

- Design pattern: `wrath-story-book/memory/webpage-session-section.md`
- Chapter: `wrath-story-book/chapters/09-the-voice-that-answers.md`
- Session notes: `wrath-story-book/sessions/session9.md`
