# Session 22 — The Worm That Walks

**Date:** 2026-09-20
**Driven by:** `chapters/22-the-shadow-that-cast-none.md` (Caleth POV) and `sessions/session22.md`
**Live page:** `/wrath` (route served from `G:\Projects\games\src\app\wrath\page.tsx`)

**Structural change this pass:** mythic tier moves **back to the Vanguard header alongside the level**. Session 21 split tiers per character (only Nageru had finished a personal quest); Session 22 brought all four to Tier 4, so the split is no longer needed and the per-card `tier` field has been removed at the author's request.

---

## What changed

### `G:\Projects\games\src\app\wrath\page.tsx`

**The Vanguard — header (~line 125)**
- Header span now reads **"Level 10 Gestalt · Mythic 4"** (was "Level 10 Gestalt").
- The inline code comment was rewritten. It previously instructed that tiers live on the individual cards and that the footer shows a range. It now records that tiers diverged for exactly one session, that all four match again as of Session 22, and that if they ever diverge again the per-card field and the footer range should both come back.

**The Vanguard — character cards (~lines 132–166)**
- Removed the `tier` property from all four entries in the card array (`Caleth`, `Nageru`, `Thane`, `Korroc`).
- Removed the `<p>` that rendered `Mythic Tier {character.tier}` beneath each character's class line. Cards now show portrait, name, class, and the character-sheet overlay only.

**Campaign Arc Status — session header (~line 468)**
- Top label: `Session XXI — The Lost Fane` → **`Session XXII — The Worm That Walks`**
- Gold title: `What Was Lost` → **`The Shadow That Cast None`**

**Campaign Arc Status — narrative paragraph (~line 475)**
- Fully replaced. Covers the color/breath contradiction, the scrying that located the wizard, Jerribeth taking him and leaving the soldiers for the dragon, the raid, and the second scrying that ends in the dark with something that is not a man.
- Highlighted span: *"somebody is building dragons now"*, wrapped in `{" "}` on both sides per the word-jam rule.
- Deliberately does **not** name the connection between Xanthir Vang and Caleth's parents. That is Caleth's private thread and belongs in chapter prose, not a summary card.

**Campaign Arc Status — Terendelev card (~line 497)**
- **Refreshed** (not left as-is). The previous quote was still accurate but the session's emotional color is loss without a body, which is literally her situation — there was never a body, and Kenabres has a patch of swept stone instead of a grave.
- Checked against the hard rule in `memory/webpage-session-section.md`: the card is about **her** — her absent body, her square, her hundred years of being walked past, her four scales given with no instructions. Exactly one closing clause ties forward to the present.

**Campaign Arc Status — four PC cards (~lines 510–534)**
All four role labels and contribution paragraphs replaced:
- **Caleth** — *The One Who Went Still* → **The One Who Asked the Color**. The two questions, walking out, the page in the study with three lines in a second ink, the kettle, and being pinned to the cave ceiling while his friend was carried out.
- **Nageru** — *The One They Waited For* → **The One Who Broke the Dragon**. Going with Caleth unasked, searching without questions, two templars in four seconds, and five strikes on the Woundworm.
- **Thane** — *The One the Axe Knew* → **The One Who Saw the Blade**. Arguing against tracking, six templars, the blood-on-the-glaive question, and absolving Caleth of the failed scrying.
- **Korroc** — *The One Who Saw It First* → **The One Who Said Of Course**. The one-word answer, two life-bonds at once, standing in the acid for tied prisoners, three of six claws.

**Campaign Arc Status — milestone box (~lines 546–568)**
- Status title: `A Temple Found, a Wizard Taken` → **`Everything Except the One Thing`**
- Subtitle: → **`The dragon dead · Four soldiers home · A name in the dark`**
- Summary paragraph fully replaced; ends on **Xanthir Vang** as the campaign's named enemy, with a highlighted span on *"a name this company now has to learn how to hunt."*
- Footer: **`Mythic Tier 3–4` → `Mythic Tier 4`**, and its code comment updated to point at the Vanguard header rather than the per-card fields. `Book 3 of 6` and `Level 10` unchanged.

**Theater of War map — pin tooltips (~lines 209–276)**
- **Citadel Drezen** — rewritten. The four soldiers are home, the dragon is dead, the wizard was moved before the party could reach him and the scrying no longer finds him.
- **The Molten Scar** — rewritten and now carries real content instead of a direction-of-travel note: the lava river, the Gray Road on the old levee, four days from Drezen, the Templar cavern above it, and the Abyssal rift that was burning at midday and gone by dark.
- Pin **positions unchanged** — the map art is still `worldwound-map3-1.jpg` and no pins were added or moved. The Molten Scar pin keeps its `bottom-0` tooltip anchor (it sits at 87%, below the ~70% clipping threshold).

**Theater of War — sidebar (~lines 283–293)**
- **Citadel Drezen briefing** rewritten: four men walked back into the infirmary, the staff is still on the table, and somebody puts a kettle of water on that table twice a day.
- **Commander's Note** rewritten: four of five home, the dragon carrion, a name for who holds the fifth and nothing for where. Keeps Irabeth's closing logic from the previous pass — *until someone brings me a body, he is missing, and we look for missing people* — because it still reads as the same commander and the situation has not changed enough to drop it.

---

## Files NOT touched

- **`{/* FROM THE WAR CHRONICLE */}`** — auto-loads the latest dispatch from `/api/stories?campaign=wrath&limit=1`. Nothing to edit by hand.
- **Map art and pin coordinates** — `worldwound-map3-1.jpg` still covers everything the party has visited; the Molten Scar was already pinned from the Session 21 pass, which is exactly where Session 22 happened.
- **Temple of Irori, Delamere's Tomb, Eagle Rock, Vilareth Ford, Wintersun Hall pins** — evaluated and left alone. Nothing in Session 22 changes any of them.
- **Hero section, Worldwound Incursion intro, Rules/Resources nav** — static page furniture.
- **`Book 3 of 6`** — unchanged; the party is still in Book 3.

---

## Verification

1. `npm run dev` in `G:\Projects\games`, then open `http://localhost:3000/wrath`.
2. **The Vanguard** header (right of the section rule) should read **LEVEL 10 GESTALT · MYTHIC 4**.
3. The four character cards below it should show **portrait, name, class only** — no "Mythic Tier" line under any of them.
4. Scroll to **Campaign Arc Status**. Top label **SESSION XXII — THE WORM THAT WALKS**, gold title **The Shadow That Cast None**.
5. Milestone box at the bottom of that section: **EVERYTHING EXCEPT THE ONE THING**, and the footer rule should read **BOOK 3 OF 6 | MYTHIC TIER 4 | LEVEL 10**. The "3–4" range should be gone from the page entirely.
6. Hover the **blue pin on Drezen** and the **red pin at the bottom-left (Molten Scar)**. Both tooltips should show new text; the Molten Scar tooltip should open **upward** and not be clipped by the map frame.
7. Word-jam check: in the narrative paragraph, *"somebody is building dragons now"* and, in the milestone box, *"a name this company now has to learn how to hunt"* should each have normal spaces on both sides — no `nowand` or `huntXanthir`.
8. `npx tsc --noEmit` — the only errors should be the two pre-existing ones in `src/lib/tracker/merge.test.ts`. Anything in `page.tsx` is new and mine.

---

## Cross-references

- Design pattern / update process: `wrath-story-book/memory/webpage-session-section.md`
- Tier tracking rules: `wrath-story-book/memory/mythic-tiers-personal-quests.md` *(updated this pass — the "show a range in the footer" instruction now says to collapse it)*
- Chapter that drove this: `wrath-story-book/chapters/22-the-shadow-that-cast-none.md`
- Session notes: `wrath-story-book/sessions/session22.md`
- New canon from this session: `wrath-story-book/memory/xanthir-vang-and-the-note.md`, `wrath-story-book/memory/the-rift-at-the-molten-scar.md`
- Previous changelog: `wrath-story-book/website/update21.md`
