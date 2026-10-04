# Session 24 — Two Humans Came Back

**Date:** 2026-10-04
**Driven by:** `chapters/24-the-graves-at-seskers-gully.md` (Thane POV) and `sessions/session24.md`
**Live page:** `/wrath` (route served from `G:\Projects\games\src\app\wrath\page.tsx`)

**No structural changes this pass.** Level and tier are unchanged (Level 10, all four at Mythic 4), so the Vanguard header and the milestone footer were left alone.

---

## What changed

### `G:\Projects\games\src\app\wrath\page.tsx`

**Campaign Arc Status — session header (~line 460)**
- Top label: `Session XXIII — The Road North` → **`Session XXIV — Two Humans Came Back`**
- Gold title: `Children Are Not Equations` → **`The Graves at Sesker's Gully`**

**Campaign Arc Status — narrative paragraph (~line 467)**
- Fully replaced. Covers Sesker's Gully and the Khar-Zadûn graveyard, the crusader's ghost shut out of his family's tomb, the cleared crypt and the ghost laid in his own empty coffin, and the five graves. Borin died there and his brother buried him; two strangers later carried Thorek back. Ends with Dagna's ruling that they stay.
- Highlighted span: *"Thorek and Borin"*, wrapped in `{" "}` on both sides per the word-jam rule.
- It deliberately leaves Aravashnial's return to the milestone box, so the paragraph stays on the graves.

**Campaign Arc Status — Terendelev card (~line 484)**
- **Refreshed.** The old quote (*"There was never a body… the kind with no body in it, and no word"*) was built on the fathers having no graves, and this session found them. The new quote stays on her: nobody carried her home, Kenabres keeps swept stone where a grave should be, and the scales are *"the nearest thing she has to a headstone… carried a long way from where she fell by people she never knew."* One closing clause ties it to the session: *"This season the company learned what it is worth, to be carried by strangers."* It passes the hard rule, because without her name it no longer reads as a recap.

**Campaign Arc Status — four PC cards (~lines 503–527)**
All four role labels and contribution paragraphs replaced:
- **Caleth**: *The One Who Kept the Letters* → **The One Who Showed the Mark**. The oath to the ghost, the frozen moment in the square, waking screaming and showing the spiral by the fire (*"he had been told what it was called"*), and crying Aravashnial's name when the hood came back.
- **Nageru**: *The One Who Found the Seam* → **The One at His Shoulder**. Leaving the shadow for the swarm, the hand on Caleth's other shoulder and the night beside him, standing back at the graves both days, and breaking all three constructs.
- **Thane**: *The One Who Asked the Dead* → **The One Who Read the Fifth Stone**. The one question to the ghost, the five graves, the two strangers he can never thank, the collar, and the knives on the step.
- **Korroc**: *The One Who Said Nope* → **The One the Ghost Knew**. *"And now the child comes before me,"* Borin's grave and the morning alone, the screaming axe his cousin threw him, and the bedside.

**Campaign Arc Status — milestone box (~lines 538–562)**
- Status title: `A Day's Ride Among the Dead` → **`He Walked Home`**
- Subtitle: → **`The fathers found · The deadline passed · The wizard home`**
- Summary paragraph fully replaced. Vang's week runs out with nothing. Then the lone figure walks in from the west with three constructs behind him, the knights break them, Thane picks the collar open, and four words are spoken before the wizard sleeps in the infirmary with Korroc at his side. Ends with *"How he got out, nobody knows"* and a note that Caleth now carries the collar and the ivory reliquary.
- Highlighted span: *"Aravashnial"*. The comma after it sits on the next line with no `{" "}`, so it renders flush (`Aravashnial, barefoot`).
- Footer: **unchanged**. Book 3 of 6 · Mythic Tier 4 · Level 10.

**Theater of War map — pin tooltips (~lines 200–268)**
- **Citadel Drezen**: rewritten. The week ran out with nothing; four mornings later the wizard walked in from the west, barefoot and collared, with constructs hunting him; he is asleep in the infirmary.
- All other pins evaluated and left alone. Session 24 does not touch any of them.
- **No pin for Sesker's Gully.** It lies a day north and a little west of Drezen, which on `worldwound-map3-1.jpg` falls in or past the Lake of Mists at the top edge of the art. The sidebar mentions it instead.

**Theater of War — sidebar (~lines 272–287)**
- **Citadel Drezen briefing** rewritten. The deadline passed and the walls were never tested; the tunnel is being shored for use; Korroc's mother is back at her stonework; and at Sesker's Gully two Stonevein brothers lie side by side, where the family has decided to leave them.
- **Commander's Note** rewritten in Irabeth's voice. She tripled the watch and nothing came, and she doesn't trust it. It calls back her Session 22 line: *"until someone brought me a body, the wizard was missing. Nobody brought me a body. He walked here himself."*

---

## Secrets kept off the page

- **That Aravashnial is Caleth's uncle** is never stated or hinted at. Caleth's card shows only what the party saw: a spiral, *"he had been told what it was called,"* and a name cried out loud.
- **What the Spiral means** (a Riftwarden mark) is not named. The page calls it *"a pale spiral he has carried since birth."*
- **The Pauper's Thighbone** appears only as *"an old ivory reliquary"* and is not named.

---

## Files NOT touched

- **`{/* FROM THE WAR CHRONICLE */}`**: auto-loads the latest dispatch from `/api/stories?campaign=wrath&limit=1`. It was already showing *The Graves at Sesker's Gully* during this pass.
- **The Vanguard header and cards**: no level or tier change this session.
- **Map art and pin coordinates**: unchanged. See the Sesker's Gully note above.
- **Hero section text, Worldwound Incursion intro, Rules/Resources nav**: static page furniture.

---

## Verification

1. **Port 3000 on this machine was serving a different project** (the Odessa Symphony Guild site), so this pass ran the games site on **port 3010** using a new `games` configuration in `wrath-story-book/.claude/launch.json`. Open `http://localhost:3010/wrath`, or use your usual port if the games server is the one running there.
2. Scroll to **Campaign Arc Status**. The top label should read **SESSION XXIV — TWO HUMANS CAME BACK** and the gold title **The Graves at Sesker's Gully**.
3. Four cards: **THE ONE WHO SHOWED THE MARK / AT HIS SHOULDER / WHO READ THE FIFTH STONE / THE GHOST KNEW**.
4. Milestone box: **HE WALKED HOME**, with the footer still reading **BOOK 3 OF 6 | MYTHIC TIER 4 | LEVEL 10**.
5. Word-jam check: *"Two of them read Thorek and Borin Stonevein. Borin"* and *"It was Aravashnial, barefoot"* should read normally. *(Both were verified against the rendered page text during this pass.)*
6. Hover the **blue Drezen pin**. The tooltip should begin *"Held. The demon's week ran out."*
7. `npx tsc --noEmit` returned **zero errors**. The browser console showed no errors.

---

## Cross-references

- Design pattern / update process: `wrath-story-book/memory/webpage-session-section.md`
- Chapter that drove this: `wrath-story-book/chapters/24-the-graves-at-seskers-gully.md`
- Session notes: `wrath-story-book/sessions/session24.md`
- New canon from this session: `wrath-story-book/memory/the-fathers-are-buried.md`, `memory/aravashnial-taken.md`, `memory/caleth-parents-and-uncle.md` (the last is private to Caleth and deliberately **not** surfaced on the page)
- Previous changelog: `wrath-story-book/website/update23.md`
