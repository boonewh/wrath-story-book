# Session 12 — The Strain the Smith Takes
**Date:** 2026-07-12
**Driven by:** Chapter 12 written (Korroc POV); the whispered night council, the pre-dawn advance on Drezen, the watchtower fight (schir + a vrock that sees the unseen), Paradise Hill prisoners freed and armed, the bridge taken after Caleth's acid-fireball, Irabeth bringing the army up, and ~~the siege of Drezen begun on the south bank~~ with the cemetery named as the next target *(struck claim superseded — see **Canon Correction** below: wrong bridge named, siege prematurely declared)*
**Live page:** `/wrath`

## What Changed

### `games/src/app/wrath/page.tsx` — Campaign Arc Status section (~line 412)

- **Session header** (~line 418): "Session XI — Sword of Valor" → "Session XII — Sword of Valor"
- **Gold title** (~line 419): "The Latch That Held" → "The Strain the Smith Takes"
- **Narrative paragraph** (~lines 425–437): Replaced entirely. New text covers the whispered night council (planning kept off the open air because a traitor still walks the camp), the pre-dawn advance with a hundred paladins, the watchtower taken (schir demons and a vrock that could see the unseen), some two hundred prisoners freed at Paradise Hill and many armed (blades and bows), the bridge seized after Caleth's fireball fell as acid on the enemy leadership and the cultist/tiefling camps routed, Irabeth bringing the army up the dry riverbed, and the siege of Drezen begun — camp on the south bank, a cemetery no one returns from named as the next target. **⚠ Superseded — the bridge/siege geography here was wrong; see Canon Correction below for the paragraph as it now stands.**
- **Terendelev card** (~lines 445–451): Quote refreshed. The old quote described the nest descent (now stale). New quote reflects the dragon's *absence* as the siege begins — she never lived to see Drezen; her scale at Korroc's belt slept quiet and unspent this fight (no scale was used in Session 12), but he keeps it close. Same elegiac register. **⚠ Partially superseded — "camps inside the city's outer wall" was corrected to "holds its first ground on the city's edge"; see Canon Correction below.**
- **Party contribution cards** (~lines 455–479): All four replaced. `name`, `classes`, and `role` fields unchanged.
  - **Caleth** — role "The Painter's Fury": Radiance opening the towertop fight; shocking-grasp turned to killing cold; the acid-turned fireball across the gorge that felled a swath of the enemy leadership; folding the strike team behind the army; giving freed prisoners his word and bows ("Archers are always valuable in a war").
  - **Nageru** — role "The Thunder's Reach": punching a schir off the tower; holy-fire fists against the vrock; reading the enemy's critical points and asking to be put behind them; hunting casters and leaders until the army broke; accepting the strengthened life-link with a chuckle ("I'll do my best").
  - **Thane** — role "Shadow of Judgment": the unseen outer-stair climb; the vrock that could see him anyway; the dead-sprint gauntlet of demon and friendly arrows; daggers from behind that dropped the vrock; "Well, that's our next target then" at the cemetery.
  - **Korroc** — role "The Wall That Walks": feeling Thane's wounds bloom in his own chest from the towertop ("Thane is being attacked below!"); thickening the life-link to carry half of Nageru's wounds; turning back into the tentacles and poison-cloud to free Caleth (twice in one day); healing waves over the company; walking into the city his parents' generation built and died losing. **⚠ Last beat superseded — "walked into the city" corrected to "set foot on the edge of the city"; see Canon Correction below.**
- **Status box** (~lines 493–502): title "The Eve of Drezen" → "The Siege Begins"; subtitle "Striking distance · A traitor still unnamed" → "South bank encamped · The cemetery waits"; summary replaced — outer city cleared, watchtower fallen, bridge held under arrows, ~200 prisoners freed and armed (some in reclaimed crusader steel), siege camp raised on the south bank, citadel and cemetery ahead, saboteur still unproven and unnamed. **⚠ Superseded — the siege has NOT begun and the outer city is NOT cleared; see Canon Correction below for the box as it now stands ("A Foothold on the Edge").**
- **Footer** (~lines 524–528): UNCHANGED — Book 2 of 6 | Mythic Tier 1 | Level 7. Verified it still reads exactly this (party did NOT level in Session 12).

### `games/src/app/wrath/page.tsx` — Theater of War / strategic map section (~lines 169–247)

- **Base map swap** (~line 193): `src="/images/wrath/mendev-map2.jpg"` alt "Map of Mendev" → `src="/images/wrath/drezen.jpg"` alt "Tactical map of Drezen". Same `<Image fill className="object-cover" />` inside the `aspect-[16/10]` frame; drezen.jpg is ~3:2, so object-cover is fine — component structure, frame, and hover classes untouched.
- **Hotspots** (~lines 200–219): The two old Mendev-scale pins (Kenabres, Threshold) replaced with **four** Drezen pins, reusing the exact existing pin markup (ping dot + hovered `w-48` label). Coordinates chosen from the map image:
  - **Citadel Drezen** — `top-[28%] left-[41%]` — RED (`bg-red-600`), the walled pentagonal fortress ring, upper-left-center. Label: seat of the city's command, still enemy-held, "the war ends here."
  - **The Bridge** — `top-[56%] left-[40%]` — BLUE (`bg-wardstone-blue`), the central river crossing. Label: taken and held under crusader arrows; the approach is open. **⚠ Superseded — this is the Ahari Bridge and it was NOT taken; now a RED pin. See Canon Correction below.**
  - **Paradise Hill** — `top-[39%] left-[75%]` — BLUE (`bg-wardstone-blue`), the settled circular district on the right rise. Label: ~200 prisoners freed, many now carry bows for the crusade. *(Label now opens left — see Canon Correction, clipping fix.)*
  - **The Cemetery** — `top-[67%] left-[9%]` — RED (`bg-red-600`), the field of regular gravestone marks on the far left. Label: no one who enters returns; unread, next on the list.
- **Sidebar briefing** (~lines 224–245): Mendev-scale entries replaced with Drezen-scale, same markup:
  - Gold header block "Mendevian Borders" → **"Citadel Drezen"** — seventy-five years in demon hands; the citadel is the war, everything else is the road to its gate.
  - Zinc header block "The Sellen River" → **"The Ahari"** — the dry riverbed that carried the army unseen to the walls; its south bank now holds the siege camp. **⚠ Superseded — the Ahari crossing is still demon-held and the camp is elsewhere; see Canon Correction below.**
  - Red "Commander's Note" box kept; quote refreshed to siege register: holding the outer city and camped beside a graveyard no one walks out of, and refusing to sleep the army blind next to it. **⚠ Superseded — the outer city is not held; quote re-refreshed in the Canon Correction below.**
- Section header ("Theater of War"), the "Intelligence Report" subtitle, and the legend dots were NOT touched in the first pass. *(Superseded — see "Follow-up edit" below: subtitle and legend labels updated same day at the user's request.)*

### `games/src/app/wrath/page.tsx` — Vanguard section (~line 126)

- **NOT touched.** Already reads "Level 7 Gestalt • Mythic Tier 1". No level or Mythic Tier change in Session 12. Verified in sync with the status-box footer (Book 2 / Mythic Tier 1 / Level 7).

## Files NOT Touched

- **Vanguard section header (~line 126)** — no level/tier change; already in sync (verified).
- **"From the War Chronicle" section** — auto-loads latest entry from `/api/stories`; no manual edit needed.
- **Theater of War section header ("Theater of War" h2)** — unchanged. *(The subtitle and legend labels beneath it were updated in the follow-up edit below.)*
- **Hero, Worldwound divider, "Kenabres is Burning" transition, image gallery, Vanguard character cards, footer** — no changes relevant to Session 12.

## Guardrails Observed

- **"Nurah" appears nowhere on the page** — the traitor is "unproven / unnamed" only. Confirmed by grep.
- **"blueprint" appears nowhere on the page** — the Drezen blueprints (in-fiction sensitive because of the traitor) were removed from the narrative paragraph and status box that carried them in Session 11. Confirmed by grep.
- No secrets leaked: nothing about Caleth's lineage, the Caleth–Aravashnial connection, or the blueprints' existence.
- Name spellings verified: Drezen, Irabeth, Aron Kir (not named on page but referenced correctly in notes), Terendelev, Korroc, Caleth, Nageru, Thane, schir, vrock.
- REPLACE-not-append honored: the Campaign Arc Status section is a current-state window; no prior-session content accumulated.

## Verification

1. Load `/wrath` locally (`npm run dev` → `localhost:3000/wrath`) or on the live site.
2. Scroll to the Campaign Arc Status section — confirm "Session XII — Sword of Valor" with gold title "The Strain the Smith Takes".
3. Read the narrative paragraph, the Terendelev quote, and all four contribution cards — confirm they reflect Session 12 events.
4. ~~Confirm the status box reads "The Siege Begins" / "South bank encamped · The cemetery waits".~~ **⚠ Superseded — see Canon Correction verification: it now reads "A Foothold on the Edge" / "Paradise Hill sealed · The road west waits".**
5. Confirm the status-box footer reads Book 2 of 6 | Mythic Tier 1 | Level 7.
6. Scroll up to the Vanguard section header — confirm "Level 7 Gestalt • Mythic Tier 1" still matches (no edit needed).
7. ~~Scroll to the Theater of War map — confirm the base image is now the Drezen tactical map, with four hotspots. Hover each: Citadel Drezen (red), The Bridge (blue), Paradise Hill (blue), The Cemetery (red).~~ **⚠ Superseded — there are now SIX pins; see Canon Correction verification.**
8. Confirm the sidebar reads "Citadel Drezen" / "The Ahari" / "Commander's Note", not the old Mendev entries.
9. Confirm the words "Nurah" and "blueprint" appear nowhere on the page.

## Follow-up Edit (same day, 2026-07-12)

### `games/src/app/wrath/page.tsx` — Theater of War header + legend (~lines 176–180)

- **Subtitle** (~line 176): "Intelligence Report: Fifth Crusade Geographic Survey" → **"Intelligence Report: The Siege of Drezen"** — keeps the intelligence-report register but names the current theater. **⚠ Superseded — the siege has not begun; corrected to "Intelligence Report: The Drezen Approach" in the Canon Correction below.**
- **Legend labels** (~lines 179–180): now describe what the pin colors actually mean on a siege map:
  - Blue: "The Front Lines" → **"Crusader Held"**
  - Red: "Abyssal Encroachment" → **"Demon Held"**
- Colors, dot markup, and animation classes untouched.
- Verification: hover legend should read Crusader Held (blue) / Demon Held (red); blue pins are The Bridge and Paradise Hill, red pins are Citadel Drezen and The Cemetery — legend matches pin usage. **⚠ Superseded — pin roster changed in the Canon Correction below (3 blue / 3 red).**

## Canon Correction (same day, 2026-07-12)

**What the error was:** The session writer was confused during play and the first page pass inherited it. Two claims were wrong:

1. **Wrong bridge.** The bridge taken in Session 12 is the **unnamed bridge directly south of Paradise Hill** (the eastern crossing on the map). The **Ahari Bridge** (the western crossing, where the first pass placed its blue "The Bridge" pin) was **NOT** taken — it remains in demon hands. Taking the unnamed bridge seals Paradise Hill (demons can't reach it without flight or magic) and gives the crusade a protected foothold. The routed cultist/tiefling camps were on the far (south) side of that bridge; their captured ground is where Irabeth's army now camps — south of the unnamed bridge, below Paradise Hill.
2. **Siege prematurely declared.** The siege of Drezen has NOT begun. The outer city is NOT cleared. The army still must move west; the cemetery (far west on the map) sits square in that road and is the next target. Known: the toppled towers flanking the south road block that approach with rubble.

The chapter file was corrected on disk first; the page edits below bring `/wrath` in line with it.

### `games/src/app/wrath/page.tsx` — Theater of War map (~lines 186–265)

- **Subtitle** (~line 176): "Intelligence Report: The Siege of Drezen" → **"Intelligence Report: The Drezen Approach"** (the siege has not begun).
- **"The Bridge" pin** (`top-[56%] left-[40%]`): kept in position, converted BLUE → **RED** (`bg-wardstone-blue` → `bg-red-600` on both dots; label border and heading likewise `border-red-600` / `text-red-600`, matching the other red pins exactly). Renamed **"Ahari Bridge"**. Label: "Still in demon hands. The western approach is not yet won."
- **New BLUE pin — "The Unnamed Bridge"** at `top-[62%] left-[82%]` (the eastern crossing south of Paradise Hill). Label: "Taken and held. Paradise Hill sealed at its back — nothing reaches the hill now but wings or magic."
- **New BLUE pin — "Crusader Camp"** at `top-[79%] left-[84%]` (the captured ground between the bridge and the southern channel). Label: "Irabeth's army, camped on ground the enemy held that morning. The road west waits."
- **Label clipping fix:** the map container is `overflow-hidden` and labels opened right (`left-6`). The three far-east pins — Paradise Hill (`left-[75%]`), The Unnamed Bridge (`left-[82%]`), Crusader Camp (`left-[84%]`) — now mirror the label to open LEFT (`left-6` → `right-6` on the label div). All other label markup identical.
- **Final pin roster (six):** 3 BLUE — Paradise Hill (`top-[39%] left-[75%]`), The Unnamed Bridge (`top-[62%] left-[82%]`), Crusader Camp (`top-[79%] left-[84%]`); 3 RED — Citadel Drezen (`top-[28%] left-[41%]`), Ahari Bridge (`top-[56%] left-[40%]`), The Cemetery (`top-[67%] left-[9%]`). Legend (Crusader Held / Demon Held) unchanged and now matches 3/3.

### `games/src/app/wrath/page.tsx` — Sidebar briefing (same section)

- **"Citadel Drezen" entry:** checked — makes no siege claim; unchanged.
- **"The Ahari" entry:** old text said the riverbed carried the army "to the walls" and its south bank "holds the siege camp" → new text: the riverbed carried the army to Drezen's **edge**; its **western crossing remains demon-held**; the camp sits instead **south of the unnamed eastern bridge, below sealed Paradise Hill**.
- **"Commander's Note":** old quote claimed holding the outer city → new quote: "We hold one hill and one bridge — a foothold on the edge, no more. The west is not won, and a graveyard no one walks out of sits square in the road."

### `games/src/app/wrath/page.tsx` — Campaign Arc Status section (~line 451)

- **Narrative paragraph:** geography fixed, "siege begun / outer city cleared" removed. Corrected arc: watchtower taken → ~200 freed at Paradise Hill → the **unnamed bridge south of the hill** seized and the enemy camps on its far side routed → the hill sealed (nothing reaches it without wings or foul magic) → Irabeth's army camped on the captured ground — the Crusade's first foothold on Drezen's edge; the outer city uncleared, the Ahari crossing still demon-held, the cemetery square in the road west as the next target.
- **Terendelev card:** "camps inside the city's outer wall" → "holds its first ground on the city's edge". Rest of the quote unchanged.
- **Korroc card:** "walked, at last, into the city" → "set foot, at last, on the edge of the city". No other card needed changes (Caleth's "across the gorge" and Nageru's field-reading beats are geography-safe; checked all four).
- **Status box:** title "The Siege Begins" → **"A Foothold on the Edge"**; subtitle "South bank encamped · The cemetery waits" → **"Paradise Hill sealed · The road west waits"**; summary rewritten — foothold won and paid for, unnamed bridge held under arrows, hill sealed, prisoners freed and armed, explicitly "It is not the siege — not yet", outer city uncleared, west unwon, cemetery in the road, traitor still unproven and unnamed.
- **Footer and Vanguard line (~126):** untouched — both still Level 7 / Mythic Tier 1, verified in sync.

### Guardrails re-verified after correction

- Grep confirms **"Nurah"** and **"blueprint"** appear nowhere on the page.
- Grep for "siege"/"Siege": exactly one hit remains, in the corrected negated sense — the status-box line "It is not the siege — not yet."
- No secrets; REPLACE-not-append honored.

### Updated verification steps

1. Load `/wrath` — Theater of War subtitle reads "Intelligence Report: The Drezen Approach".
2. Hover all SIX map pins: RED — Citadel Drezen (upper-left-center fortress ring), Ahari Bridge (central-west crossing), The Cemetery (far-left grave field); BLUE — Paradise Hill (right rise), The Unnamed Bridge (eastern crossing south of the hill), Crusader Camp (below it). The three far-east pins' labels open to the LEFT and are not clipped by the map edge.
3. Sidebar: "The Ahari" says the western crossing is demon-held and the camp sits south of the unnamed bridge; Commander's Note reads the "one hill and one bridge" quote.
4. Campaign Arc Status: narrative paragraph ends on the foothold/uncleared-city posture; status box reads "A Foothold on the Edge" / "Paradise Hill sealed · The road west waits" and contains "It is not the siege — not yet."
5. Footer still Book 2 of 6 | Mythic Tier 1 | Level 7; Vanguard line still "Level 7 Gestalt • Mythic Tier 1".
6. "Nurah" and "blueprint" appear nowhere on the page.

## Cross-References

- Design pattern: `wrath-story-book/memory/webpage-session-section.md`
- Chapter: `wrath-story-book/chapters/12-the-strain-the-smith-takes.md` (corrected version)
- Session notes: `wrath-story-book/sessions/session12.md`
- Prior changelog: `wrath-story-book/website/update11.md`
