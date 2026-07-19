# Session 13 — The Sound the Thunder Makes
**Date:** 2026-07-19
**Driven by:** Chapter 13 written (Nageru POV); the cemetery cleansed (ghouls, berbalang, desecrated Iomedaean mausoleum re-hallowed), Ahari Bridge cleared (four demon-fused aurochs chained to the piers as living demolition, handlers, an ice-returned fireball, every chain shattered), the mythic-enhanced chimera killed, army moved to the Ahari's south edge. **Party leveled: Level 8, Mythic Tier 2** (chimera kill granted Tier 2; GM granted Level 8 early).
**Live page:** `/wrath`

## What Changed

### `games/src/app/wrath/page.tsx` — Vanguard section (~line 126)

- **Level/Mythic line UPDATED:** "Level 7 Gestalt • Mythic Tier 1" → **"Level 8 Gestalt • Mythic Tier 2"**. Changed together with the status-box footer (see below) per the keep-in-sync comment.

### `games/src/app/wrath/page.tsx` — Theater of War / strategic map section (~lines 186–286)

- **Ahari Bridge pin** (top-[56%] left-[40%]): RED → **BLUE** (`bg-wardstone-blue` classes throughout). Label: "Cleared. Four chained beasts meant to drop the span are dead; engineers shore the piers. The road west is open."
- **Crusader Camp pin MOVED:** top-[79%] left-[84%] → **top-[69%] left-[39%]** (the district on the Ahari's south bank, directly below the bridge — verified against the map image with a crosshair crop). Label opens right again (`right-6` → `left-6`, since it's no longer near the map's right edge). New label: army at the Ahari's south edge, citadel in sight.
- **The Cemetery pin** (top-[67%] left-[9%]): RED → **BLUE**. Label: "The curse is broken and the tomb re-hallowed. The dead of the First Crusade sleep clean at last."
- **Unchanged pins:** Citadel Drezen (red — the only red pin left on the map), Paradise Hill (blue), The Unnamed Bridge (blue). Pin tally is now 5 blue / 1 red; the legend (Crusader Held / Demon Held) needs no change.
- **Sidebar "The Ahari"** rewritten: the crossing was rigged to fall (living demolition), beasts dead, chains broken, army camped at the span's south edge, engineers making it fit to carry a crusade.
- **Sidebar "Commander's Note"** re-quoted to the session's dread: "The thing we killed at the bridge was too strong for its own skin. Whatever power woke in our four at Kenabres — the enemy has found a version of its own."
- **Sidebar "Citadel Drezen"** — unchanged; still accurate.

### `games/src/app/wrath/page.tsx` — Campaign Arc Status section (~line 451)

- **Session header:** "Session XII — Sword of Valor" → "Session XIII — Sword of Valor"; gold title → **"The Sound the Thunder Makes"**.
- **Narrative paragraph:** replaced entirely — the vote ending on Korroc, Thane's walkout scout and the chained-beast discovery, the cemetery's curse broken (ghouls, the winged horror, the re-hallowed mausoleum), the bridge cleared (handlers, the ice-returned fireball, the chains), the three-headed chimera and its ice storm, the army at the Ahari's south edge, and Aravashnial's warning: the beast was enhanced the way the stone changed the four.
- **Terendelev card:** quote refreshed — the crusade she died for now stands at the Ahari with the citadel in sight; the four are "twice what they were"; her scales slept unspent through the bridge. Same elegiac register.
- **Party contribution cards:** all four replaced (`name`/`classes`/`role` unchanged):
  - **Caleth** — the caress-range lightning, the re-hallowing dispel, the returned ice fireball, the cold ward over every friend he could see, dragged to the edge of the dark and walking straight within the hour ("Damn, that hurt").
  - **Nageru** — shadowing Thane, reading the beasts as living demolition, the caught-and-returned crossbow bolt, the stillness breaking ("NO!" — the first time any of them heard him raise his voice), first to fallen Caleth.
  - **Thane** — the council walkout that found the beasts, both mausoleum locks, keeping the door while the paladins cleaned, unseen through the bridge fight, the daggers that killed the chimera mid-scream.
  - **Korroc** — the tie-breaking vote against his own argument, every chain shattered, the chimera's winter biting a child of the forge twice as deep, letting go of the life-link rather than fall, still standing when it died.
- **Status box:** title "A Foothold on the Edge" → **"The Road West Is Open"**; subtitle → "The Ahari cleared · The citadel in sight"; summary replaced — cemetery cleansed, bridge saved and shored, camp at the south edge, the power deepened (Tier 2), the enemy making mythic things of its own, saboteur still unproven/unnamed/loose.
- **Footer UPDATED:** Book 2 of 6 | **Mythic Tier 2** | **Level 8** (was Tier 1 / Level 7). In sync with the Vanguard line.

## Files NOT Touched

- **"From the War Chronicle" section** — auto-loads latest entry from `/api/stories`; no manual edit needed.
- **Theater of War header, subtitle ("Intelligence Report: The Drezen Approach"), legend labels** — still accurate; unchanged.
- **Hero, Worldwound divider, transition, gallery, Vanguard character cards, footer** — no changes relevant to Session 13.

## Guardrails Observed

- **"Nurah" appears nowhere on the page** — saboteur is "unproven, unnamed, and loose" only. Confirmed by grep.
- **"blueprint" appears nowhere on the page.** Confirmed by grep.
- No secrets: nothing about Caleth's lineage, the Caleth–Aravashnial connection, or Nageru's order/origin (his card describes the shout, not the Sunken Fist).
- REPLACE-not-append honored throughout.
- Name spellings verified: Ahari, Aravashnial, Irabeth, Korroc, Caleth, Nageru, Thane, chimera, aurochs (not named on page; "demon-fused beasts" used).

## Verification

1. Load `/wrath` locally (dev server on port 3000) or on the live site after deploy.
2. Vanguard header: **"Level 8 Gestalt • Mythic Tier 2"**.
3. Theater of War: five blue pins (Paradise Hill, Unnamed Bridge, Ahari Bridge, Crusader Camp, Cemetery) and one red (Citadel Drezen). Hover each — Ahari reads cleared, Cemetery reads re-hallowed, Camp sits just south of the Ahari span.
4. Sidebar: "The Ahari" describes the rigged bridge and the new camp; Commander's Note carries the enemy-mythic dread.
5. Campaign Arc Status: "Session XIII — Sword of Valor" / "The Sound the Thunder Makes"; narrative, Terendelev quote, and all four cards reflect Session 13.
6. Status box: "The Road West Is Open" / "The Ahari cleared · The citadel in sight"; footer reads **Book 2 of 6 | Mythic Tier 2 | Level 8**.
7. Confirm "Nurah" and "blueprint" appear nowhere on the page.
8. Remember to commit on `main` this time (see Session 12's lesson: work committed to a side branch never reaches Vercel).

## Cross-References

- Design pattern: `wrath-story-book/memory/webpage-session-section.md`
- Chapter: `wrath-story-book/chapters/13-the-sound-the-thunder-makes.md`
- Session notes: `wrath-story-book/sessions/session13.md`
- Prior changelog: `wrath-story-book/website/update12.md`
