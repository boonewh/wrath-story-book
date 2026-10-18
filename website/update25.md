# Session 25 — Someone Who Might Listen

**Date:** 2026-10-13
**Driven by:** `chapters/25-the-bell-of-mercy.md` (Nageru POV) and `sessions/session25.md`
**Live page:** `/wrath` (route served from `G:\Projects\games\src\app\wrath\page.tsx`)

**No level or tier change this session.** The party is still **Level 11**, with Caleth at Mythic 4 and the other three at Mythic 5. The Vanguard header, the per-card tiers and the footer's **Mythic Tier 4–5 · Level 11** are all unchanged. Only the footer's code comment was touched, to read "Sessions 24–25."

---

## What changed

### `G:\Projects\games\src\app\wrath\page.tsx`

**Campaign Arc Status — session header (~line 463)**
- Top label: `Session XXIV — Two Humans Came Back` → **`Session XXV — Someone Who Might Listen`**
- Gold title: `The Graves at Sesker's Gully` → **`The Bell of Mercy`**

**Campaign Arc Status — narrative paragraph (~line 470)**
- Fully replaced. It covers:
  - the late dawn attack (drakes as a distraction, one glabrezu through the courtyard wall unseen, a second in the north range)
  - the wizard's story (cage, chain, key, days walking east) and that every spell said it was true
  - that he cannot cast with the collar off, and nothing finds out why
  - the dream: Arueshalae hunted in a ruined fortress far west, calling Nageru by name
- Highlighted span: *"Arueshalae"*, with `{" "}` on both sides.
- **First time Arueshalae is named on the page.** Session 17 kept her unnamed so the name would land in prose first. It has now been in four chapters, and the whole session turns on her.

**Campaign Arc Status — Terendelev card (~line 492)**
- **Refreshed.** The Session 24 quote was about being carried home by strangers. The new one is about her hundred years among people who never knew what she was, and her never asking them to decide. They knew her for about four seconds, and the scales are what remain of that. One closing clause ties it to the session: *"a voice from the far west asked for what she never had to: to be seen before anyone decided what she was."* It passes the hard rule: with her name deleted, it does not read as a session recap.

**Campaign Arc Status — four PC cards (~lines 506–530)**
All four role labels and paragraphs replaced:
- **Caleth**: *The One Who Showed the Mark* → **The One Who Asked the Questions**. He suspected the escape first, asked every question at the bedside himself, searched the wizard with every spell he had, threw his strongest unmaking at whatever holds him and found nothing ("Nothing"), and folded five travelers and four horses west within the hour.
- **Nageru**: *The One at His Shoulder* → **The One She Called by Name**. He read the drakes as a distraction, broke the second glabrezu alone, and had the dream. He wonders whether something has changed her, and is going to see.
- **Thane**: *The One Who Read the Fifth Stone* → **The One Who Cast It Himself**. The glabrezu saw him invisible and he cut it anyway; he said "I'll do it" and cast the lie-detection himself, caught no lies but won't swear the spell worked, and brought a prisoner from the forge to the map table on a hunch.
- **Korroc**: *The One the Ghost Knew* → **The One Who Went Over the Wall**. He stepped off the tower and drifted down on the dragon's scale, took half the commander's wounds, spent the day on his knees in the infirmary, and asked his mother for the map nobody had.

**Campaign Arc Status — milestone box (~lines 540–565)**
- Status title: `He Walked Home` → **`West, Toward the Bell`**
- Subtitle: → **`The attack came late · The wizard cannot cast · A voice asked to be found`**
- Summary fully replaced:
  - Drezen is short of soldiers and bolts.
  - A prisoner at the forge pointed to a near-empty corner of the map, past the Gray Road. The hunters there fear the bell, and a hag leads them.
  - The company folded to the temple of Irori and rides from there.
  - Aravashnial rides with them, with no staff and no spells.
  - Ends: *"three of the four heard something in the way he said it that they could not name. Nobody said a word."*
- Highlighted span: *"Bell of Mercy"*, with `{" "}` on both sides.
- Footer values unchanged. The comment now reads "Sessions 24–25."

**Theater of War map — pin tooltips**
- **Citadel Drezen** (~line 209): rewritten for the dawn attack. Two glabrezu, both gone; *"Nobody knows how the first one got so close."*
- **Temple of Irori** (~line 219): rewritten. Its ghostly keepers are gone, a handful of pilgrims have come, and the knights folded there with their horses on the way west.
- All other pins evaluated and left alone.
- **No pin for the Bell of Mercy fortress.** It lies a week or more west, off the edge of `worldwound-map3-1.jpg`, and no map in canon locates it precisely. The sidebar mentions it instead.

**Theater of War — sidebar**
- **Citadel Drezen briefing**: rewritten. The attack came late and the walls held; Dagna has rebuilt the broken wall better than before; the citadel is short of soldiers and bolts; the wizard has gone west with the knights; and *"Somewhere past the Gray Road, a bell hangs in a ruined tower."*
- **Commander's Note**: rewritten in Irabeth's voice from the session. It has *"They were late"*, the soldiers and bolts line taken nearly word for word from the session notes, her questions for the wizard that can wait, and *"I have stopped betting against them."*

---

## Secrets kept off the page

- **That Aravashnial is Caleth's uncle** is not stated or hinted at. Caleth's card shows only the investigator.
- **What is wrong with Aravashnial** is not named or explained. The page says only that three of the four heard something they could not name. The GM was deliberately vague, and the page is no more specific than the prose.
- **What sent the dream, or what "answered" Arueshalae,** is not mentioned.
- **Which three noticed** is not named on the page.

---

## Files NOT touched

- **`{/* FROM THE WAR CHRONICLE */}`**: auto-loads the latest dispatch from `/api/stories?campaign=wrath&limit=1`.
- **The Vanguard section**: no level or tier change.
- **Map art and pin coordinates**: unchanged.
- **Hero section text, Worldwound Incursion intro, Rules/Resources nav**: static page furniture.

---

## Verification

1. Run the games site. This pass used the `games-dev` configuration in `wrath-story-book/.claude/launch.json`, on port 3000. Open `http://localhost:3000/wrath`.
2. Scroll to **Campaign Arc Status**. The top label should read **SESSION XXV — SOMEONE WHO MIGHT LISTEN** and the gold title **The Bell of Mercy**.
3. Four cards: **THE ONE WHO ASKED THE QUESTIONS / SHE CALLED BY NAME / WHO CAST IT HIMSELF / WHO WENT OVER THE WALL**.
4. Milestone box: **WEST, TOWARD THE BELL**. The footer should still read **BOOK 3 OF 6 | MYTHIC TIER 4–5 | LEVEL 11**.
5. Word-jam check: *"in a dream. Arueshalae — the demon"* and *"the dream says the Bell of Mercy hangs"* should read normally. *(Both were verified against the rendered page text.)*
6. Hover the **Drezen pin**: it should begin *"Held, and struck."* Hover the **Temple of Irori pin**: it should begin *"A lost house of Irori."*
7. `npx tsc --noEmit` returned **zero errors**, and the browser console showed no errors.

---

## Cross-references

- Design pattern and update process: `wrath-story-book/memory/webpage-session-section.md`
- Chapter that drove this: `wrath-story-book/chapters/25-the-bell-of-mercy.md`
- Session notes: `wrath-story-book/sessions/session25.md`
- New canon from this session: `memory/arueshalae-and-the-bell-of-mercy.md` and `memory/aravashnial-taken.md`
- Previous changelog: `wrath-story-book/website/update24.md`
