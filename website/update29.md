# Session 29 — No More Games

**Date:** 2026-11-08
**Driven by:** `chapters/29-the-center-of-the-fire.md` (Caleth POV) and `sessions/session29.md`
**Live page:** `/wrath` (route served from `G:\Projects\games\src\app\wrath\page.tsx`)

**⚠ Level and tier change: the party is now Level 12, and all four are Mythic 5.** Caleth reached Mythic 5, so the tiers **match again**. The page goes back to the single-header shape last used in Sessions 22–23: the Vanguard header now reads **"Level 12 Gestalt · Mythic 5"**, the per-card `tier` field and its "Mythic Tier" line are removed, and the footer reads **Mythic Tier 5 · Level 12**. The code comments on both say to restore the per-card shape if tiers diverge again.

Before this pass the games repo still had the **uncommitted Session 28 edit** (see `update28.md`). This pass builds on it, and the two go out together in one commit. The untracked `.codex-remote-attachments/` folder was left alone.

---

## What changed

### `G:\Projects\games\src\app\wrath\page.tsx`

**The Vanguard section (~lines 119–160)**
- Header: `Level 11 Gestalt` → **`Level 12 Gestalt · Mythic 5`**
- The `tier: 4/5` fields were removed from all four character entries.
- The per-card `Mythic Tier {character.tier}` line was removed.
- The sync comment was rewritten for the matched-tier state.

**Campaign Arc Status — session header**
- Top label: `Session XXVIII — The Worm's House` → **`Session XXIX — No More Games`**
- Gold title: `Strangers' Faces` → **`The Center of the Fire`**

**Campaign Arc Status — narrative paragraph**
- Fully replaced. It covers the robing room and the lead chamber of runes, the dead thing rising from the water, the invisible shelves only Caleth could see, **Yaniel's armor** and **the Blackwing Library's stolen books**, Vang waiting in the long hall with the woman they had hunted since the Molten Scar, his offer of terms cut off, her turning out to be *"something far bigger than they had believed"* and Nageru sending her home, the worms, Caleth's two sentences, the fire, and the empty robes.
- Highlighted span: *"Xanthir Vang"*, with `{" "}` before it.

**Campaign Arc Status — Terendelev card**
- **Unchanged, after review** (third session running). Session 29's fire is the wardstone's, not hers, and nothing in it ties back to her honestly. If it is still unchanged next session, consider refreshing it for staleness alone.

**Campaign Arc Status — four PC cards**
- **Caleth**: *The One Who Kept the Papers* → **The Center of the Fire**. The invisible shelves and Yaniel's armor (Radiance knew it first), the mark burning on the landing in front of everyone, *"you will stop because you will die,"* Radiance through Vang, *"you killed my father, you killed my mother,"* the fire from his body, and the fireball *"for good measure."*
- **Nageru**: *The One Who Pulled His Punches* → **The One Who Shouted**. Four blows finishing the thanadaemon, the roll under the blue demons, running the hall with his fists alight, *"you will not get away again,"* and sending Jerribeth home.
- **Thane**: *The One Who Didn't Know Their Faces* → **The One Who Read the Joins**. The charcoal on the seams between the runes, the first look into the hall, the arrow from the platinum box missing by a hand's width, recovered and still true, and the look at Caleth *"like a lock he means to come back to."*
- **Korroc**: *The One Who Didn't Let Go* → **The One Who Wouldn't Come Apart**. The shield against the shadows' claws, the staff and his *"Oh,"* refusing Vang's unmaking spell, feeling the mark down the link and saying nothing, standing in the fireball, the worms in his beard, and *"Rooms."*

**Campaign Arc Status — milestone box**
- Status title: `The Stair Down` → **`Rooms`**
- Subtitle: → **`The master destroyed · The mark gone quiet · The front door still to come`**
- Summary fully replaced: still in the Sanctum's long hall, templars and minotaurs dead, the demons banished for a hundred years, the bag heavier by a paladin's armor and a stolen library, nobody certain (Caleth least of all) but nothing moving, the mark gone quiet, and Arueshalae's warning about the rooms and *"the one that guards the front door."*
- Highlighted span: *"front door"*, with `{" "}` before it.
- Footer: **Mythic Tier 4–5 → 5**, **Level 11 → 12**; comment rewritten.

---

## Secrets kept off the page

- **Who Caleth's parents were.** The lines *"you killed my father, you killed my mother"* are now party-public (said aloud in front of everyone) and are on Caleth's card. Their **names, that they were Riftwardens, the note and the uncle** are not mentioned.
- **What the Blackwing was.** The page says only *"the stolen books of the Blackwing Library,"* which is all the party heard. That it was the Riftwardens' library stays Caleth's.
- **The Spiral.** The card says *"a mark on his shoulder"* and that everyone saw it burn. It is not named, and what it means is not mentioned. The milestone box says it *"has gone quiet"* without offering a reason; why is not established.
- **The three-moon book** inside Caleth's coat. Not mentioned.
- **Jerribeth's true nature** is public now (a glabrezu), but the page keeps it as *"something far bigger than they had believed"* and doesn't use the word.
- **The kalavakus** are unnamed in prose and are *"blue horned demons"* here.
- **Whether Vang is truly finished.** The page states the party's belief and Caleth's doubt, matching the chapter. Nothing claims more than that.

---

## Files NOT touched

- **Theater of War map pins and sidebar**: Drezen still doesn't know what happened in the Sanctum. The Drezen pin, the Citadel Drezen briefing and Irabeth's Commander's Note about the axe are all still true. There is still no Green Gate pin (see `update27.md`).
- **`{/* FROM THE WAR CHRONICLE */}`**: auto-loads the latest dispatch.
- **Hero section text, Worldwound Incursion intro, Rules/Resources nav**: static page furniture.

---

## Verification

1. Run the games site with the `games-dev` configuration (port 3000), then open `http://localhost:3000/wrath`.
2. **The Vanguard** header should read **LEVEL 12 GESTALT · MYTHIC 5**, and the four character cards should show **no** Mythic Tier line.
3. **Campaign Arc Status** top label: **SESSION XXIX — NO MORE GAMES**. Gold title: **The Center of the Fire**.
4. Four cards: **THE CENTER OF THE FIRE / THE ONE WHO SHOUTED / THE ONE WHO READ THE JOINS / THE ONE WHO WOULDN'T COME APART**.
5. Milestone box: **ROOMS**. The footer should read **BOOK 3 OF 6 | MYTHIC TIER 5 | LEVEL 12**.
6. Word-jam check: *"all that was left of Xanthir Vang was"* and *"guards the front door."* should read normally.
7. Results this pass: `npx tsc --noEmit` returned **zero errors**, the browser console showed **no errors**, and steps 2–6 were checked against the rendered page text.

---

## Cross-references

- Design pattern and update process: `wrath-story-book/memory/webpage-session-section.md`
- Chapter that drove this: `wrath-story-book/chapters/29-the-center-of-the-fire.md`
- Session notes: `wrath-story-book/sessions/session29.md`
- New canon from this session: `memory/xanthir-vang-and-the-note.md` (Vang destroyed), `memory/the-drake-and-jerribeth.md` (glabrezu), `memory/demons-banished-a-hundred-years.md`, `memory/mythic-tiers-personal-quests.md` (Level 12, all Mythic 5)
- Previous changelog: `wrath-story-book/website/update28.md`
