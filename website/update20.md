# Session 20 — "The Kind One" / The Marchlands map

**Date:** 2026-09-06
**Driven by:** `chapters/20-the-kind-one.md` (Caleth POV) and `sessions/session20.md`, plus a new map asset supplied by the author.
**Live page:** `/wrath` — https://…/wrath
**Repo:** `G:\Projects\games`

Two things in this pass: **the Theater of War map replaced** with the new regional art (and all six of its hotspots rewritten to match), and the usual per-session Campaign Arc Status replacement.

---

## What changed

### `src/app/wrath/page.tsx` — Theater of War: MAP REPLACED

**The regional map replaces the Drezen tactical map inside the existing "Theater of War" section.** It is not a new section — an earlier draft of this pass added one, and it was removed. Nothing else on the page gained or lost a section.

- **Image swapped:** `/images/wrath/drezen.jpg` → `/images/wrath/worldwound-map2.jpg`. The old Drezen art is now unreferenced by the page (file left in place).
- **Frame aspect: `aspect-[16/10]` → `aspect-[3/2]`.** The new art is 1200×800, which is exactly 3:2. With `object-cover` on a 16:10 frame the map would have been cropped top and bottom — fatal for a map, since Wintersun Hall and the Molten Scar sit low in the frame. At 3:2 the fit is exact: no crop, no letterbox.
- **`sizes` and `priority` added** to the `next/image` so Next serves an appropriately-sized file for the 4/5-column container.
- **Long descriptive `alt`** naming the labeled locations.
- **Section subtitle:** *"Intelligence Report: The Drezen Approach"* → *"Intelligence Report: The Marchlands"*.
- **The `Crusader Held` / `Demon Held` legend is unchanged — and is finally accurate.** Every one of the six old pins was blue, so the red half of that legend had nothing to point at. The new set uses it.

### `src/app/wrath/page.tsx` — Theater of War: all six hotspots rewritten

The old pins were city-scale (Ahari Bridge, Paradise Hill, The Unnamed Bridge, Crusader Camp, The Cemetery) and their percentage positions were meaningless on a regional map. All six replaced:

| Pin | Position | Color | Tooltip opens |
|---|---|---|---|
| Citadel Drezen | `top-[19%] left-[60%]` | blue | right |
| Delamere's Tomb | `top-[50%] left-[60%]` | blue | right |
| Eagle Rock | `top-[53%] left-[75%]` | blue | left |
| Vilareth Ford | `top-[57%] left-[85%]` | blue | left |
| Wintersun Hall | `top-[68%] left-[68%]` | blue | right |
| **The Molten Scar** | `top-[87%] left-[43%]` | **red-600** | right |

**Positions were verified, not estimated.** Each percentage was rendered as a marker onto a copy of the 1200×800 source art and visually checked against the icon it names; the Molten Scar pin was moved from `80%/46%` to `87%/43%` because the first position sat on top of its own baked-in label. Tooltip side (`left-6` vs `right-6`) is chosen per pin so the 192px panel never runs off the right edge — the two rightmost pins open leftward.

**Tooltip copy is current-state, matching the section's existing register:** Drezen held and the forge renamed; Vilareth Ford at double size with the Kellids camped beside it; Eagle Rock as the only wagon road west, reported occupied and scouted to nothing; Wintersun Hall empty with its chieftain ash outside the door; Delamere's tomb still holding its grave goods because nobody had the right to open it; and the Molten Scar as the direction the Queen's order points.

### `src/app/wrath/page.tsx` — Campaign Arc Status (REPLACED, per the section's rules)

- **Session header:** `Session XIX — The Wounded Lands` → **`Session XX — The Marchlands`**.
- **Gold title:** `Twenty Feet of Stone` → **`The Kind One`** (matches the chapter title).
- **Narrative paragraph:** fully rewritten. Built around the bone-spike reversal — the crusade's description of the raiders was accurate-sounding and wrong, the spikes come off in your hand, only the chieftain grew them — then the village, then the duel that was won too well. Highlight span on the "drilled, pegged through the leather and lashed down with sinew" clause.
- **Terendelev card:** **refreshed** (it had been about the ledgers being revised in the direction of hope, which was Session 19's motif and is now stale). The new quote takes its emotional color from Session 20's disguise theme but stays entirely about *her*: a hundred years in a plain face, not to be spared but so the market could stay a market, and the moment she dropped it in the street. Checked against the hard rule in `memory/webpage-session-section.md` — delete her name from it and it does not read as a session recap.
- **All four PC cards replaced**, roles and prose:
  - Caleth — *The One Who Read the Name* → **The One Who Won It Too Well**. The language learned out of spite at nineteen; a real bloodless offer won three times over without cutting anybody; the oath broken by the man who swore it; and Caleth's own smaller failure — an hour spent on the man in the chair and not one glance at the people in the ring.
  - Nageru — *The One With Farther to Go* → **The One Who Turned Back**. The horse's head; then going back to Drezen so the atonement would not slide down a list. Ends on "it does not require an audience; it requires a witness."
  - Thane — *The One Who Knew the Look* → **The One Who Remembered Her**. The bebilith kill; *watching Caleth* turn the bone and getting there himself three seconds later by a different road; remembering Jestak; being singled out as the first throat to cut; and going still at "a man can be forgiven and still owe."
  - Korroc — *The Hand on the Wall* → **The One They Turned To**. The bursting ice, the two hammer blows, inheriting a tribe he never asked for, and the evening on his knees in the mud.
- **Milestone box:** `The Trail Begins in a Riverbed` → **`A Dwarf Has a Tribe`**. Subtitle now *"The raids stopped · The clan resettled · One vial that undoes a death."* Body covers the resettlement at Vilareth Ford, Korroc's promise, Jesker leaving to earn his absolution, the unopened chest, and the true resurrection potion. Highlight span moved to the philosopher's-stone clause.
- **Book / Tier / Level footer: UNCHANGED at Book 3 · Mythic Tier 3 · Level 9.** Session 20 granted no advancement.

### `src/app/wrath/page.tsx` — Commander's Note (sidebar, ~line 272)

**Replaced.** This sits outside the Campaign Arc Status block and had gone two sessions stale — it was still the Session 18 order about the four missing Nahyndrian vials. It now addresses the thing that will actually cause friction in the camp this month: four dozen Kellids at Vilareth Ford who were raiding that road a month ago, and a standing order that they get work, rations, and the ordinary courtesy of the camp. Closing line deliberately echoes Irabeth's verdict in the chapter.

*(The four vials are still an open campaign thread — they are simply no longer this week's standing order.)*

---

## Design decision: the map keeps its pins

The author asked whether to mark the map with dots. **It keeps them** — because the map is going into the Theater of War section, which is built around hover hotspots and has been since the page was written. Stripping the pins would have removed the only interactive element on the page and left a static image inside a frame designed for markers.

*(An earlier draft of this pass misread the request as "add a new standalone map section" and argued against pins on the grounds that the artwork is already labeled. That reasoning holds for a decorative map; it does not hold for this section, where the pins are the feature. The standalone section was removed.)*

**Why pins still work even though the art is labeled:** the baked-in labels say *where* things are; the pins say *what is true there this month*. Those are different jobs, and the tooltips are where the per-session state lives. Updating them next session is a text edit in six places — no art re-export.

## Asset correction made before publishing

The first version of the map labeled the chapel **"Chapel of Sheyln."** Flagged to the author; a corrected `worldwound-map2.jpg` was supplied and **verified at pixel level before this pass** — the label now reads **"Chapel of Shelyn."** All other labels were re-checked against canon in the same pass:

| Map label | Canon | OK |
|---|---|---|
| Chapel of Shelyn | Shelyn | ✔ (fixed) |
| Vilareth Ford | `Vilareth` — 53/53 occurrences in repo | ✔ |
| Wintersun Hall | Wintersun Hall | ✔ |
| Delamere's Tomb | Delamere | ✔ |
| Keeper's Canyon | Keeper's Canyon | ✔ |
| The Gray Wastes | American `Gray` per style guide | ✔ |

---

## Files NOT touched

- **`{/* FROM THE WAR CHRONICLE */}`** — auto-loading; pulls the latest dispatch from `/api/stories?campaign=wrath&limit=1`. Nothing to edit by hand.
- **The Vanguard level/tier line (line 126)** — checked and **correct as-is** at `Level 9 Gestalt • Mythic Tier 3`. It must stay in sync with the milestone footer, and both were already right because Session 20 granted no advancement. No edit was needed; it was verified, not skipped.
- **The "Citadel Drezen" sidebar paragraph** — still true. The room-by-room work and the two shrines being scrubbed continue.
- **`public/images/wrath/worldwound-map.jpg`** and **`public/images/wrath/drezen.jpg`** — both now unreferenced by the page. Left in place rather than deleted; `drezen.jpg` in particular may be wanted again if a city-scale map is ever restored.
- **Everything above the Worldwound rift divider** — hero, Vanguard cards, Kenabres sections. Unchanged.

---

## Bug caught during verification

Nageru's card initially rendered the literal text **`He was at the horse&rsquo;s head`** on the live page. Cause is the gotcha documented in `memory/webpage-session-section.md`: the four PC entries are **JS strings inside a card array, not JSX text**, so HTML entities are not decoded and React escapes the ampersand. Fixed by using the typographic character `’` directly. Grepped the whole card array afterward — no entities remain in any `contribution:` string.

The same pass also confirmed **no inline-span word-jam** in any of the three wrapped prose paragraphs; all highlight spans use explicit `{" "}` on both sides.

---

## Verification

Dev server: `npm run dev` in `G:\Projects\games`, then visit http://localhost:3000/wrath.

1. **Theater of War** — near the top of the page, under the Vanguard cards. The map should now be the regional **Marchlands** art, not the old Drezen city map, and the subtitle should read *Intelligence Report: The Marchlands*.
2. **Hover every pin.** Six of them. Confirm each sits on the feature it names (Drezen's castle, the tomb building, the rock, the bridge, the ruin, the lava), and that the two rightmost tooltips open *leftward* and stay inside the frame.
3. **The Molten Scar pin should be red**, and it is the only red one — which is what makes the *Demon Held* half of the legend mean something for the first time.
4. **Nageru's card** — confirm it reads `horse's head` and *not* `horse&rsquo;s head`. This is the specific bug that was fixed.
5. **Highlight spans** — check the three highlighted phrases (in the narrative paragraph, and in the milestone box) have a real space on both sides and are not glued to the neighboring word.
6. **Level/tier sync** — the Vanguard line near the top and the milestone footer at the bottom must **both** read Level 9 / Mythic Tier 3.
7. **Commander's Note** — in the Drezen sidebar, should now be about the Kellids at Vilareth Ford, not about four missing vials.

Typecheck: `npx tsc --noEmit` — clean for `page.tsx`. **Two pre-existing unrelated errors in `src/lib/tracker/merge.test.ts` are expected and were present before this pass; ignore them.**

**Commit on `main`.** Work committed to a side branch never reaches Vercel (Session 12's lesson).

---

## Corrections applied after the author's review

Four factual errors were caught by the author reading the finished cards and canon, and fixed everywhere they appeared. Recorded here so they are not reintroduced.

1. **Clan size — "four hundred" was wrong, badly.** The Grunhuld-Wintersun are **about four dozen people** ("about a dozen warriors, a few dozen more who are not"). "Four hundred" had propagated into eleven places across the canon files, memory, `CLAUDE.md` and the Caleth card. All corrected, and `lore/factions.md` now carries a **⚠ HOW MANY THEY ARE — GET THIS RIGHT** note so it cannot drift again. *(The author had already fixed every instance in the chapter itself.)*

2. **Marhevok's death was framed as Caleth's fault. It is not.** The card said he *"made it impossible for the man to keep his word, and a man died who did not have to."* Wrong reading of the scene. **Caleth's offer was real and he won it without drawing blood; Marhevok broke his own oath because of what he was** — demon-touched, chaotic evil, and already the murderer of three of his own brothers. Canon now states this explicitly, with a standing note that **this campaign argues for redemption often (Joran Vhane, Jesker Helton) and this was deliberately not one of those** — so no later pass retro-fits a redemption reading or has a character mourn him. What survives is Caleth's actual, smaller failure: he spent the whole hour on the man in the chair and never looked at the frightened people in the ring, which is exactly what Korroc did instead.

3. **Nageru did not ride to Drezen.** The card said he *"rode back a hundred and forty miles."* **Caleth teleported all three of them** — the whole round trip took under an hour, which is a point the chapter makes deliberately. Fixed on the card and in the changelog.

4. **The drake's breath is a burst, not a cone.** It detonates like a fireball made of ice — the chapter's phrase is *"a blossoming explosion of glittering white"* — and sheets the ground where it lands. **Do not write it as a dragon's cone.** Fixed on Korroc's card and in `characters/caleth.md`, `characters/korroc.md` and `characters/npcs.md`, where the drake entry now carries an explicit ⚠ note.

Also corrected on **Thane's card**: the bone-spike discovery was **Caleth's**, crouched over the body at dawn. Thane arrives at the same place three seconds later by his own road, and his contribution is the *recognition of Jestak*, not the discovery. The card now reads that way.

✔ **The chapter sentence was fixed too, with the author's approval.** The same framing appeared once in chapter prose at `chapters/20-the-kind-one.md:915`; a replacement was proposed and approved, and the swap is made. **Chapter and canon now agree.** The line now runs: *"… spent the whole of the next hour on the one man in it who was past reaching … And the thing in the chair had broken its word anyway, because that was what it was — and in all of it Caleth had not once looked at the people standing in the ring."* One sentence, minimum-touch, per the chapter-prose rule.

---

## Cross-references

- Design pattern + update process: `wrath-story-book/memory/webpage-session-section.md`
- Chapter that drove this: `wrath-story-book/chapters/20-the-kind-one.md`
- Session notes: `wrath-story-book/sessions/session20.md`
- Canon for the clan (bone spikes worn, not grown): `wrath-story-book/lore/factions.md` → Grunhuld-Wintersun
- Map geography: `wrath-story-book/lore/worldwound.md` → Places West of Vilareth Ford
- Previous changelog: `wrath-story-book/website/update19.md`
