# Session 19 Web Update — Twenty Feet of Stone

**Date:** 2026-08-30
**Driven by:** `chapters/19-twenty-feet-of-stone.md` (Thane POV) and `sessions/session19.md`
**Live route:** `/wrath`
**Repo:** `G:\Projects\games`

The Campaign Arc Status block moves off Session 18's *Sword of Valor* moment and onto Session 19: Aravashnial's reconstruction of what actually happened to the Stonevein fathers, the letters from home, and the rescue of Jesker Helton from Delamere's tomb.

---

## What changed

### `src/app/wrath/page.tsx` — Campaign Arc Status → Session Header
- Top label: **"Session XVIII — Sword of Valor"** → **"Session XIX — The Wounded Lands"**
- Gold title: **"The Mark It Chose"** → **"Twenty Feet of Stone"** (matches the chapter title)
- Decorative diamond divider left alone.

### `src/app/wrath/page.tsx` — Campaign Arc Status → Narrative paragraph
- Fully replaced. Was the black room, the six fake crystals, Thane's possession and the Banner going up.
- Now: the four-source reconstruction at the war table, the company of forty and the eight who came home, the fathers put to work on walls they had helped build, the twenty feet, the letters read in a gateway with nothing said afterward, and the missing Erastilian priest.
- One inline highlight span, on `they were brought here, to Drezen, and put to work on the walls they had helped build`, with `{" "}` on both sides.

### `src/app/wrath/page.tsx` — Campaign Arc Status → Terendelev card
- **Quote replaced** (card structure, heading and subtitle untouched).
- Deliberate check against the hard rule in `memory/webpage-session-section.md`: **the card is still about her.** The session's motif — the record turning out to be wrong in the direction of hope — is one opening sentence of setup only. The body is Terendelev: the plain face, the century in Kenabres, the street, the fall she spent herself to slow. It fails the "delete her name and it still reads as a session recap" test in the right direction.

### `src/app/wrath/page.tsx` — Campaign Arc Status → Four PC contribution cards
All four role labels and paragraphs replaced.

| PC | Old role label | New role label |
|---|---|---|
| Caleth | The One Who Picked It Up | **The One Who Read the Name** |
| Nageru | The One Who Said No | **The One With Farther to Go** |
| Thane | The Blade He Wiped Clean | **The One Who Knew the Look** |
| Korroc | The Smith Who Stood Aside | **The Hand on the Wall** |

- **Caleth** — identifying Delamere off the altar, the fireball on four swarms, banishing the derakni, the hold person that flushed the possession out by accident, and the slowed dodge-and-kill on the shachath; closes on the deliberately visible night-march light.
- **Nageru** — the lightning javelin that did nothing, the switch to cold iron, the smite poured into a javelin because nothing was in reach, the single-step crossing, his ruling that left Delamere's grave goods alone, and an unexplained task from his order.
- **Thane** — reading the table before the wizard spoke, the solitary search of the riverbed that found nothing, naming Jesker's possession off the man's stance, the punch dagger, and wiping three clean blades twice in one day.
- **Korroc** — shaping the bridge stone, his mother's errand at the wall, hauling Jesker back over the ledge, and naming the lingering aura correctly and out loud.

### `src/app/wrath/page.tsx` — Campaign Arc Status → Milestone box
- Status title: **"Drezen Is Taken"** → **"The Trail Begins in a Riverbed"**
- Subtitle: → *"The fathers survived · The priest recovered · The Queen turns them south and west"*
- Summary paragraph replaced: the Queen's mandate arriving with reinforcements, the tomb rescue, the untouched grave, and the dry riverbed east of the walls that an engineer's crew is about to open. Closes on the two threads still hanging — four loose vials, and the unexplained whispering.
- One inline highlight span with `{" "}` on both sides.

### Spelling
- New card text is written in **American English** per the rule added to `style-guide.md` this session. Incidentally, replacing the Nageru and Korroc cards removed the page's last British spellings (`apologised`, `armour` ×2). **`page.tsx` now greps clean** for `grey / colour / armour / humour / recognis- / apologis- / civilis-`.

---

## Checked and deliberately NOT changed

- **Level / Mythic Tier — verified in sync, no edit needed.** Session 19 granted **no advancement**. The Vanguard line (`page.tsx:126`, *"Level 9 Gestalt • Mythic Tier 3"*) and the milestone footer (`page.tsx:549–553`, *Book 2 · Mythic Tier 3 · Level 9*) already agree and both stay as they are.
- **Book number stays at 2 of 6.** Drezen is held, but the party is still operating out of it; no book transition has been called at the table.
- **Terendelev card structure** — heading, subtitle, divider and classes untouched; quote only.
- **The Vanguard section** (`page.tsx:121–`) — portraits, classes and character-sheet links unchanged.
- **`{/* FROM THE WAR CHRONICLE */}`** — untouched. It auto-loads the most recent dispatch from `/api/stories?campaign=wrath&limit=1`; the Arc Status block above it is the snapshot, the chronicle is the running record.
- **The hero, intro narrative, map legend and miniature gallery** — untouched.
- **No new cards added.** Still four PCs, still one Terendelev card, still one milestone box. Section length is unchanged.

---

## Secrets check

Nothing on the page reveals a private thread. Specifically held back:
- **Caleth's letters are not characterized at all** beyond "letters came up the road from home." The foster-parent framing stays off a reader-facing page.
- **Nageru's task is alluded to and not described** — *"a letter came from his order with a task in it he has not explained to anyone."* The fane, its age, and what its founders were waiting for stay off the page.
- **Thane's own possession in Session 18 is not connected to Jesker's** anywhere in the copy, because no character has said it out loud. The card says only that nobody asked him how he knew.
- Aravashnial is *"an old wizard"* in the narrative paragraph; no Riftwarden material.

---

## Verification

1. `cd G:\Projects\games && npm run dev`, then open `http://localhost:3000/wrath`.
2. Scroll to the Campaign Arc Status band (black section, gold title, below the map). Confirm the red top label reads **Session XIX — The Wounded Lands** and the gold title reads **Twenty Feet of Stone**.
3. **Word-jam check** — the two highlighted phrases must have clean spaces on both sides: *"…most of the rest were not killed — they were brought here, to Drezen, and put to work on the walls they had helped build thirty years before."* and *"…there is a mile and a half of dry riverbed and an engineer's crew about to open the ground where a tunnel came out forty years ago."*
4. Confirm all four PC cards show the new role labels in gold small-caps and that the paragraphs are all roughly the same length (they should sit level in the 4-across grid on desktop).
5. Confirm the Vanguard line at the top of the page and the milestone footer **both** still read Level 9 / Mythic Tier 3.
6. `npx tsc --noEmit` — the only errors should be the two pre-existing ones in `src/lib/tracker/merge.test.ts`. Anything in `src/app/wrath/page.tsx` is new and mine.

**⚠ Not committed.** The edits are in the working tree on `main` and have not been staged or pushed. Nothing reaches Vercel until they are committed on `main` — see the Session 12 lesson in the design-pattern memory.

---

## Cross-references

- Design pattern and update process: `wrath-story-book/memory/webpage-session-section.md`
- Chapter that drove this: `wrath-story-book/chapters/19-twenty-feet-of-stone.md`
- Session notes: `wrath-story-book/sessions/session19.md`
- Letters (source text for the gateway scene): `wrath-story-book/characters/chapter19-letters.md`
- Previous update: `wrath-story-book/website/update18.md`
- Canon updated the same day: `characters/thane.md`, `characters/korroc.md`, `characters/caleth.md`, `characters/nageru.md`, `characters/npcs.md`, `lore/timeline.md`, `lore/items.md`, `lore/worldwound.md`, and four new files in `memory/`
