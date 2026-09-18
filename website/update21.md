# Session 21 — "What Was Lost" / Map 3 / Per-Character Mythic Tiers

**Date:** 2026-09-13
**Driven by:** `chapters/21-what-was-lost.md` (Nageru POV), `sessions/session21.md`, a new map asset (`worldwound-map3.jpg`), and the author's advancement ruling: **Level 10 for the party; Nageru alone to Mythic Tier 4.**
**Live page:** `/wrath`
**Repo:** `G:\Projects\games`

Three things in this pass: the Vanguard section changed to show **per-character mythic tiers**, the Theater of War switched to **map 3** with its pins rebuilt, and the usual Campaign Arc Status replacement.

---

## What changed

### `src/app/wrath/page.tsx` — The Vanguard: tiers are per character now

- **Header:** `Level 9 Gestalt • Mythic Tier 3` → **`Level 10 Gestalt`**. The tier comes out of the header entirely.
- **Card array:** each character now has a `tier` field: Caleth **3**, **Nageru 4**, Thane **3**, Korroc **3**.
- **Each card** renders a small Cinzel line under the class line: *Mythic Tier N*, with the number in `wotr-gold`.
- **The inline sync comment was rewritten.** Level is kept in sync between the header and the milestone footer. Tier is kept in sync between each card and the footer's *range*.

**Why this design:** the tiers will diverge further, since each PC has a personal quest that grants a tier, and they'll converge again later. Putting the tier on the card handles any combination without touching the layout. A single header line would have had to say something like "Tier 3 (Nageru 4)" and get worse with every quest.

### `src/app/wrath/page.tsx` — Theater of War: map 3

- **Image:** `worldwound-map2.jpg` → **`worldwound-map3-1.jpg`** (1000×667, which is 3:2 to within half a pixel, so the existing `aspect-[3/2]` frame fits with no visible crop).
- **Alt text** now also names the Temple of Irori.
- **All pin positions re-derived for the new art** by drawing markers on a copy of the image and checking each one. None of the map2 positions carried over.
- **Seven pins now, up from six.** The Temple of Irori is added.

| Pin | Position | Color | Opens | Tooltip gist |
|---|---|---|---|---|
| Citadel Drezen | `18.7% / 60%` | blue | right | Held and hurt: the six-legged dragon, the fallen tower, Aravashnial and four soldiers taken |
| **Temple of Irori** *(new)* | `29% / 44.5%` | blue | right | A Baphomet temple over a lost house of Irori; it restored itself and is clean; its keepers will wait |
| Delamere's Tomb | `49.5% / 60%` | blue | right | Grave goods untouched; the shared vision of the crystal melting |
| Eagle Rock | `52% / 74%` | blue | left | Unchanged |
| Vilareth Ford | `57.7% / 84.5%` | blue | left | Quiet road; the clan camps beside it under Korroc's man |
| Wintersun Hall | `69% / 67.5%` | blue | right | Empty (trimmed) |
| The Molten Scar | `87% / 42%` | red | right, **anchored `bottom-0`** | Unchanged |

- **Sidebar, "Citadel Drezen" paragraph:** rewritten for the attack. A broken tower over the courtyard, a garrison on shouted orders, and the recovered gear and broken staff laid on the command table.
- **Commander's Note:** replaced. Irabeth orders search parties to go out in threes and back before dark, nobody to climb the ruined tower, every dragon sighting logged, and the five treated as missing until someone brings back a body.

### `src/app/wrath/page.tsx` — Campaign Arc Status (REPLACED)

- **Session header:** `Session XX — The Marchlands` → **`Session XXI — The Lost Fane`**. **Gold title:** **`What Was Lost`**.
- **Narrative paragraph:** the temple of Baphomet, the axe on the rock, the temple *remembering what it had been*, the monk bowed to as an equal and named something nobody has said aloud since, and the return to a broken tower and a snapped staff. **The phrase "Son of Irori" is deliberately not on the page.** It's alluded to, so the reveal stays in the chapter prose.
- **Terendelev card: refreshed.** The Session 20 quote was about her disguise. The new one takes its color from a temple that rebuilt itself and contrasts that with her grave: a swept patch of stone in a Kenabres square that people cross on the way to market. It closes on the four scales carried "a year into the Wound." **Checked against the hard rule:** delete her name and it doesn't read as a session recap.
- **PC cards, all four replaced:**
  - Caleth, **The One Who Went Still**: folding two dwarves out of the upside-down sky, the lightning that ended the glabrezu, the spell the temple wouldn't let work, and silence over the broken staff. *The reason the staff hits him hardest is Caleth's private material and is not on the card.*
  - Nageru, **The One They Waited For**: the grieving stone, the five blows, the monk's bow and *welcome home*, the robes, and not speaking of it.
  - Thane, **The One the Axe Knew**: Fiendsplitter, the map, the mist trap, the door under the idol, *good luck to her*.
  - Korroc, **The One Who Saw It First**: *see, that is what I saw*, the stone in his blood turning two blades, the fire, the snort at "elven."
- **Milestone box:** **`A Temple Found, a Wizard Taken`**, subtitled *"The fane restored · A tower fallen · A bounty on a runaway."* The body covers the fane, the Templar papers (the Ivory Sanctum "somewhere in the Marchlands," the "elven" woman nobody believes in), the 1,000-platinum bounty, and Aravashnial.
- **Footer:** Book **3** of 6 · **Mythic Tier 3–4** · **Level 10**, with a code comment explaining that the tier is a range.

---

## Asset notes for the author

1. ✔ **"Chapel of Sheyln" fixed.** Map 3 was misspelled; the author replaced it with **`worldwound-map3-1.jpg`** (same 1000×667 layout, label now reads "Chapel of Shelyn") and deleted `worldwound-map3.jpg`. The page `src` now points at `map3-1`. All seven pin positions were re-checked on the new file and still land on their features. Map 2's corrected label didn't carry into the new art. **It should read "Chapel of Shelyn."** The pins don't touch that label, so it's safe to swap the image later with no code change, **as long as the new file keeps the same layout.** If the layout moves, the pins need re-deriving.
2. ✔ **"Abandoned Swarm Caverns" is intentional** (confirmed by the author): it is where the party fought the swarms of bugs. Recorded in `lore/worldwound.md`.
3. **The games repo shows `public/images/wrath/Caleth.jpg` deleted.** The page doesn't reference it (the Vanguard uses `caleth1.jpg`), so it's safe. Noted only so the deletion isn't a surprise at commit time.

---

## Files NOT touched

- **`{/* FROM THE WAR CHRONICLE */}`**: auto-loading from the API.
- **Everything above the Vanguard**, the Worldwound rift divider, and the void-fracture transition.
- **Eagle Rock and Molten Scar tooltip text**: still accurate, positions updated only.
- **Mobile pin overflow**: pre-existing and still unfixed. The 192px tooltips overflow the small frame on phones. The recommended fix, `hidden lg:block` on each pin wrapper, was not applied. Logged in `memory/webpage-session-section.md`.

---

## Verification

Measured in the dev server at a forced **1400×950** viewport (the pane otherwise reports 0×0).

- **Map 3 loads**, and the frame is 976×651.
- **All seven tooltips have zero overflow** on all four edges.
- **Vanguard card tiers render 3 / 4 / 3 / 3**; the header reads **Level 10 Gestalt**; no "Level 9" text remains anywhere on the page.
- **Footer** reads Mythic Tier **3–4** and Level **10**.
- **Session XXI — The Lost Fane** and **What Was Lost** present; the new Commander's Note present.
- **No literal HTML entities** on the page, and no inline-span word-jam in the wrapped paragraphs.
- `npx tsc --noEmit`: **no errors in `page.tsx`** (the two pre-existing `merge.test.ts` errors are unrelated).

To spot-check yourself: `npm run dev`, open `/wrath`, hover all seven pins (the Temple of Irori should sit on the walled temple west of Drezen), and check that Nageru's card alone reads **Mythic Tier 4**.

**Commit on `main`.** Remember that `worldwound-map3-1.jpg` is untracked and `worldwound-map2.jpg` shows as deleted.

---

## Canon records updated alongside this pass

- Character files: all four now read **Level 10**; **Nageru Tier 4** (personal quest: the fane); the others Tier 3.
- **New memory:** `memory/mythic-tiers-personal-quests.md` covers the per-character rule, the quest table (Caleth's is a guess, Thane's and Korroc's unstated), and where tier lives on the page.
- `memory/webpage-session-section.md` has the new tier-sync rule and a Theater of War gotchas section (re-deriving pins, `bottom-0` for low pins, the 0×0 viewport, mobile overflow).
- `CLAUDE.md` updates the Cross-Project sync note and Party State → Advancement.

## Cross-references

- Design pattern: `wrath-story-book/memory/webpage-session-section.md`
- Tier rule: `wrath-story-book/memory/mythic-tiers-personal-quests.md`
- Chapter: `wrath-story-book/chapters/21-what-was-lost.md`
- Session notes: `wrath-story-book/sessions/session21.md`
- Previous changelog: `wrath-story-book/website/update20.md`
