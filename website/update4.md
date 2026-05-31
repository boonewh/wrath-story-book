# Update 4 — Session IV (The Library After the Fight)

**Date:** 2026-05-18
**Driven by:** Chapter 4 / Session 4 landing
**Live page:** `/wrath` on the games site

## What changed

### `src/app/wrath/page.tsx` — Campaign Arc Status section (around line 411)

- **Top section comment**: renamed from `{/* SESSION I: CHARACTER PROGRESS */}` to `{/* CAMPAIGN ARC STATUS — REPLACE-NOT-APPEND each session. See wrath-story-book/memory/webpage-session-section.md ... */}` — self-documenting, points to the design pattern memory
- **Session label**: *Session I → Session IV — The Worldwound Incursion*
- **Title (big gold heading)**: *The Fall of Kenabres → Above the Sunken Sky* (matches Chapter 4's umbrella title)
- **Narrative paragraph**: surface-emergence summary replacing the underground-arc summary
- **Terendelev card**: unchanged (quote still works as written)
- **All four PC contribution cards rewritten** per Session 4 beats:
  - **Caleth** — orphan rescue, near-death at library, *"a secret about an old wizard he is only beginning to understand"* (quiet Riftwarden allusion; readers in-the-know catch it, casual readers don't)
  - **Nageru** — subdued by threshold-violation, guard duty at Gwerm Manor; *"his fists were missed"* does double duty (true in-fiction + quietly acknowledges the player was absent)
  - **Thane** — city-reading, half-orc kill at Anevia's home, kneeling to Klarah with the *"I'll carry you when you get tired"* promise
  - **Korroc** — ruined city grief, last rites for the corrupted Sarenrae knights, first Stonelord stone-strike, the fire-elemental transformation
- **Status box**: *The Underground Cleared → The Library After the Fight* — party-split fact made explicit, replacing the previous "ready to surface" optimism
- **Book / Mythic Tier / Level footer**: unchanged at 1 / 0 / 3 — *verify whether Session 4 leveled the party; update if so*

### `src/app/wrath/page.tsx` — Vanguard section (around line 125)

- Added an inline code comment above the *"Level 3 Gestalt • Mythic Tier 0"* span warning that this line must stay in sync with the Status Box footer below. Both places display level/tier info; both must update together when the party levels or gains a Mythic Tier.

## Files NOT touched (relevant but intentionally unchanged)

- **The auto-loading "From the War Chronicle" section** below the arc-status block — that pulls from the `/api/stories` endpoint and updates automatically when a new chronicle entry posts; no manual edit needed.
- **The Vanguard character cards themselves** — names, classes, portraits, and sheet links are unchanged.
- **The image gallery, hero, map, "Kenabres is Burning" transition** — all unchanged.

## Verification

- Visit `/wrath` on the live site (or `npm run dev` locally and visit `localhost:3000/wrath`)
- Scroll past the "Kenabres is Burning" transition section
- The next section should now read **Session IV — The Worldwound Incursion / Above the Sunken Sky**
- The Vanguard section higher up should still show *"Level 3 Gestalt • Mythic Tier 0"* — confirm it matches the Status Box footer at the bottom of the arc-status section
- The "From the War Chronicle" section below should auto-pull whatever the most recent chronicle entry is (independent of this update)

## Cross-references

- Design pattern for this section: `wrath-story-book/memory/webpage-session-section.md`
- Chapter that drove this update: `wrath-story-book/chapters/04-the-smith-in-the-ruin.md`
- Session notes: `wrath-story-book/sessions/session-4.md`
