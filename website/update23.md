# Session 23 — The Road North

**Date:** 2026-09-27
**Driven by:** `chapters/23-children-are-not-equations.md` (Caleth POV) and `sessions/session23.md`
**Live page:** `/wrath` (route served from `G:\Projects\games\src\app\wrath\page.tsx`)

**No structural changes this pass.** Level and tier are unchanged (Level 10, all four at Mythic 4), so the Vanguard header and the milestone footer were left alone.

---

## What changed

### `G:\Projects\games\src\app\wrath\page.tsx`

**Campaign Arc Status — session header (~line 460)**
- Top label: `Session XXII — The Worm That Walks` → **`Session XXIII — The Road North`**
- Gold title: `The Shadow That Cast None` → **`Children Are Not Equations`**

**Campaign Arc Status — narrative paragraph (~line 467)**
- Fully replaced. Covers the quasit's one-week ultimatum and the torn journal, the letters in the cover (Caleth read them and has said nothing), the drake raid on the excavation, the opened escape tunnel with no dwarven dead in it, the dead prisoner's testimony, and the four riding north at nightfall with three days left on the deadline.
- Highlighted span: *"the company rode north at nightfall"*, wrapped in `{" "}` on both sides per the word-jam rule.
- ⚠ **It deliberately does not say what the letters contain.** That Aravashnial is Caleth's uncle is known only to Caleth and belongs in chapter prose, not a summary card. The page says only that he read two old letters and has not spoken of them.

**Campaign Arc Status — Terendelev card (~line 484)**
- **Evaluated and left unchanged.** Its subject, *"there was never a body… the kind with no body in it, and no word,"* is still the session's emotional color, and now doubly so: a tunnel full of the wrong bones, and Thane's unfinished *"at least finding bodies would —"*. It still passes the hard rule, since it is about her and not a recap.

**Campaign Arc Status — four PC cards (~lines 503–527)**
All four role labels and contribution paragraphs replaced:
- **Caleth**: *The One Who Asked the Color* → **The One Who Kept the Letters**. The locked drawer, the letters from the cover (contents not named), killing the drake that carried Thane from directly in front of it, and waking on the road with his hand on his shoulder, saying the wizard is trying to reach him.
- **Nageru**: *The One Who Broke the Dragon* → **The One Who Found the Seam**. The second seam in the cover, handed over unasked; three lancers down; dropping under the acid; running beside the horses; his promise to Dagna.
- **Thane**: *The One Who Saw the Blade* → **The One Who Asked the Dead**. Lanced, carried off, free, taken again, and killing the man who put him down. Telling his aunt in person. Four questions to a dead man, one answered "no". *"I need a horse."*
- **Korroc**: *The One Who Said Of Course* → **The One Who Said Nope**. The one-word answer to the ultimatum, his mother's arrival, the boots of speed and the thrown healing, asking the dead where his father went, and getting on a horse for Thane.

**Campaign Arc Status — milestone box (~lines 538–562)**
- Status title: `Everything Except the One Thing` → **`A Day's Ride Among the Dead`**
- Subtitle: → **`An ultimatum refused · The tunnel opened · Three days left on the week`**
- Summary paragraph fully replaced. It covers Drezen fortifying against Vang's deadline, the scrying that now fails every time, and the four camped a few hours north on the dry riverbed, riding for the Khar-Zadûn graveyard and waystation.
- Highlighted span: *"a graveyard for the dwarves who died when Khar-Zadûn fell"*. The comma after it sits on the next line with no `{" "}`, so it renders flush (`fell, a day out`).
- Footer: **unchanged**. Book 3 of 6 · Mythic Tier 4 · Level 10.

**Theater of War map — pin tooltips (~lines 200–268)**
- **Citadel Drezen**: rewritten. Ordered to leave within the week and answered in one word, the tunnel under the eastern bridge open, the wizard still missing and the scrying shut in the company's face every morning.
- All other pins (**Temple of Irori, Delamere's Tomb, Eagle Rock, Vilareth Ford, Wintersun Hall, the Molten Scar**) evaluated and left alone. Session 23 does not touch any of them.
- **No new pin for the Khar-Zadûn graveyard.** It lies a day north of Drezen, which is at or past the top edge of `worldwound-map3-1.jpg`, and the party has not reached it. Add it once it has been visited, and derive its position visually against the art, per `memory/webpage-session-section.md`.

**Theater of War — sidebar (~lines 272–287)**
- **Citadel Drezen briefing** rewritten: the gate reinforced and the watch doubled; a dwarf stonemason who turned out to be Korroc's mother, already correcting the engineers; the tunnel open with no dwarves among its dead; the staff still on the command table.
- **Commander's Note** rewritten in Irabeth's voice: the demon on the wall, Korroc's *"nope"* taken as the citadel's formal reply, and letting four of her best ride north after two men nobody has seen in decades, *"because I would have gone myself."* This replaces the "until someone brings me a body, he is missing" note from Session 22.

---

## Files NOT touched

- **Your uncommitted hero-section change** (`HeroBackground` import and component in place of the static `wrath-hero.jpg` image, ~lines 7 and 88) was already in the working tree before this pass and is **not part of this update.** It was left exactly as found. Commit it with this pass or separately, as you prefer.
- **`{/* FROM THE WAR CHRONICLE */}`**: auto-loads the latest dispatch from `/api/stories?campaign=wrath&limit=1`. Nothing to edit by hand.
- **The Vanguard header and cards**: no level or tier change this session.
- **Map art and pin coordinates**: unchanged; see the graveyard note above.
- **Hero section text, Worldwound Incursion intro, Rules/Resources nav**: static page furniture.

---

## Verification

1. The dev server was already running on port 3000 (`npm run dev` in `G:\Projects\games`). Open `http://localhost:3000/wrath`.
2. Scroll to **Campaign Arc Status**. The top label should read **SESSION XXIII — THE ROAD NORTH** and the gold title **Children Are Not Equations**.
3. Four cards: **THE ONE WHO KEPT THE LETTERS / FOUND THE SEAM / ASKED THE DEAD / SAID NOPE**.
4. Milestone box: **A DAY'S RIDE AMONG THE DEAD**, with the footer still reading **BOOK 3 OF 6 | MYTHIC TIER 4 | LEVEL 10**.
5. Word-jam check: *"So the company rode north at nightfall with"* and *"when Khar-Zadûn fell, a day out"* should read normally. *(Verified in the browser pane during this pass.)*
6. Hover the **blue Drezen pin**. The tooltip should begin *"Held, and ordered to leave."*
7. `npx tsc --noEmit` returned **zero errors** this pass. The two errors in `src/lib/tracker/merge.test.ts` that earlier changelogs mention no longer appear.

---

## Cross-references

- Design pattern / update process: `wrath-story-book/memory/webpage-session-section.md`
- Chapter that drove this: `wrath-story-book/chapters/23-children-are-not-equations.md`
- Session notes: `wrath-story-book/sessions/session23.md`
- New canon from this session: `wrath-story-book/memory/caleth-parents-and-uncle.md` (private to Caleth; deliberately **not** surfaced on the page)
- Previous changelog: `wrath-story-book/website/update22.md`
