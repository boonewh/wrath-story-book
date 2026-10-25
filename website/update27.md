# Session 27 — What the Hand Remembers

**Date:** 2026-10-25
**Driven by:** `chapters/27-false-stone.md` (Korroc POV) and `sessions/session27.md`
**Live page:** `/wrath` (route served from `G:\Projects\games\src\app\wrath\page.tsx`)

**No level or tier change this session.** The party is still **Level 11**: Caleth at Mythic 4, the other three at Mythic 5. The legendary items made this session came from earlier tier bumps (see `memory/legendary-items-and-the-axe.md`). The Vanguard header, the per-card tiers and the footer's **Mythic Tier 4–5 · Level 11** are unchanged. Only the footer's code comment changed, to read "Sessions 24–27."

The games repo was clean when this pass began (Week 26 was committed as `9e1099f`).

---

## What changed

### `G:\Projects\games\src\app\wrath\page.tsx`

**Campaign Arc Status — session header (~line 463)**
- Top label: `Session XXVI — Under My Protection` → **`Session XXVII — What the Hand Remembers`**
- Gold title: `The Hallowed Tower` → **`False Stone`**

**Campaign Arc Status — narrative paragraph (~line 470)**
- Fully replaced. It covers:
  - the briefing: Vang holding the Sanctum while Baphomet's daughter harvests crystals in the Abyss
  - the finger on the map southwest of Drezen
  - the one day of preparation: armor mended beside the prisoner, and three knights sitting a day on the forge floor
  - horses made of smoke, the living forest, the gorge, and the back door through stone that was not stone
- Highlighted span: *"Arueshalae"*, with `{" "}` on both sides.

**Campaign Arc Status — Terendelev card (~line 489)**
- **Refreshed.** Last session's closing clause (about Caleth's protection) had gone stale. The new quote is about **her scales**: a dragon's hoard nobody ever saw, and instead a silver scale each, with no instructions, because she trusted them to know. The one tie to this session: the dwarves still spend theirs drifting down cliffs, as they did into the gorge, *"and she would have laughed at that… and called it exactly what it was for."* It passes the hard rule: delete her name and it is not a session recap.

**Campaign Arc Status — four PC cards (~lines 503–528)**
All four role labels and paragraphs replaced:
- **Caleth**: *The One Who Stood Beside Her* → **The One Who Asked Her Everything**. The questions that put the Sanctum on the map, twenty people carried to the bell in ten folds, the horse working copied into his book, all five up a cliff in one step, and *"so that is where they came from."*
- **Nageru**: *The One Who Said "I'm Here"* → **The One Who Taught Them to Sit**. *"Touched by a goddess,"* the forge-floor sitting with the amulet in his palm, the hundred-foot wall on bare feet, and a construct folded from a deeper stance.
- **Thane**: *The One Who Rang the Bell* → **The One Who Found the Door**. His own knife woke, the night's rest cast, the night spent feeling watched (nothing came), two constructs killed from behind, the door in the blank wall, two derakni, and the last question.
- **Korroc**: *The One Who Said Yes* → **The One Who Left the Axe**. The armor mended beside Joran and the handshake, the shield woken, the axe laid on Irabeth's table (*"coming back for it"*), twice into false stone, lifted in a construct's jaws, and fire.

**Campaign Arc Status — milestone box (~lines 539–563)**
- Status title: `A Demon in Drezen` → **`Three Doors`**
- Subtitle: → **`The Sanctum found · The back way taken · Which one?`**
- Summary fully replaced:
  - the veiled, basilisk-held front gate, and the back way
  - the constructs in the cavern, *"the same kind that once came over a rise outside Drezen"*
  - the stair to a blank wall, and the door it did not admit to
  - the ivory labyrinth room and the goat-headed carving
  - ends: *"There are three doors, and this is the house of Xanthir Vang."*
- Highlighted span: *"Xanthir Vang"*, with `{" "}` before it.
- *"This is the house of"* was chosen deliberately over *"behind one of them is."* Vang holds the Sanctum, but **whether he is in residence is not established.**
- Footer values unchanged; comment updated.

**Theater of War map — pin tooltips**
- **Citadel Drezen** (~line 209): rewritten. Irabeth keeps a silent dwarven axe on her table; half her engineers are far to the west working out how to bring a silver bell home; the knights have gone southwest with a demon to guide them.
- **No pin was added for the Green Gate or the Ivory Sanctum.** The place is *southwest of Drezen*, but nothing establishes where on this map art, and pin positions are percentages of the art. A guessed pin would be invented geography. Add one when the table or the GM's map places it.
- All other pins were evaluated and left alone, including the Temple of Irori (its "walked west for a week" is still true as history).

**Theater of War — sidebar**
- **Citadel Drezen briefing**: rewritten. The demon told them everything in one night and pointed to *the Green Gate*; twenty of Drezen's people have gone west to the Bell of Mercy; the knights rested a day, *"made something of their weapons on the forge floor,"* and left at dawn.
- **Commander's Note**: rewritten in Irabeth's voice, about the axe. *"It talks, in Dwarven, in several voices… I am not to hold it by the haft… not to let it think it had been left… I have hung it where it can see the door. If anything comes over my walls while they are gone, I will find out what it has to say."*

---

## Secrets kept off the page

- **Caleth's third dream** (Vang, the crystals, *"four living examples"*, the chained man). His alone. Not mentioned.
- **The night talk at the Gray Road** and **anything wrong with Aravashnial**. Not mentioned; Aravashnial does not appear on the page this week.
- **That Aravashnial is Caleth's uncle.** Not mentioned.
- **Thane's feeling of being watched** is mentioned as a feeling, and as *"nothing ever came."* It is not explained, because it isn't explained.
- **The legendary items' powers.** No powers are named; *"woke"* is as far as the page goes.

**Now public, and safe to state:** **the Sanctum's location (the Green Gate, southwest of Drezen)** is established in Ch 27 and printed in the chapter, so the page names it.

---

## Files NOT touched

- **`{/* FROM THE WAR CHRONICLE */}`**: auto-loads the latest dispatch from `/api/stories?campaign=wrath&limit=1`.
- **The Vanguard section**: no level or tier change.
- **Map art and pin coordinates**: unchanged (see the Green Gate note above).
- **Hero section text, Worldwound Incursion intro, Rules/Resources nav**: static page furniture.

---

## Verification

1. Run the games site with the `games-dev` configuration in `wrath-story-book/.claude/launch.json` (port 3000), then open `http://localhost:3000/wrath`.
2. Scroll to **Campaign Arc Status**. The top label should read **SESSION XXVII — WHAT THE HAND REMEMBERS** and the gold title **False Stone**.
3. Four cards: **THE ONE WHO ASKED HER EVERYTHING / WHO TAUGHT THEM TO SIT / WHO FOUND THE DOOR / WHO LEFT THE AXE**.
4. Milestone box: **THREE DOORS**. The footer should still read **BOOK 3 OF 6 | MYTHIC TIER 4–5 | LEVEL 11**.
5. Word-jam check: *"the way was Arueshalae —"* and *"the house of Xanthir Vang."* should read normally. *(Both were verified against the rendered page text this pass.)*
6. Hover the **Drezen pin**: it should begin *"Held. Its commander keeps a dwarven axe…"*
7. Results this pass: `npx tsc --noEmit` returned **zero errors**, the browser console showed **no errors**, and the section rendered correctly at 1400×950.

---

## Cross-references

- Design pattern and update process: `wrath-story-book/memory/webpage-session-section.md`
- Chapter that drove this: `wrath-story-book/chapters/27-false-stone.md`
- Session notes: `wrath-story-book/sessions/session27.md`
- New canon from this session: `memory/legendary-items-and-the-axe.md`, `memory/arueshalae-and-the-bell-of-mercy.md` (the Sanctum's location), `memory/aravashnial-taken.md`, `memory/ap-spellings-win.md`
- Place details: `lore/worldwound.md` → *The Green Gate and the Ivory Sanctum*
- Previous changelog: `wrath-story-book/website/update26.md`
