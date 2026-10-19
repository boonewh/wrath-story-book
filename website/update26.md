# Session 26 — Under My Protection

**Date:** 2026-10-18
**Driven by:** `chapters/26-the-hallowed-tower.md` (Caleth POV) and `sessions/session26.md`
**Live page:** `/wrath` (route served from `G:\Projects\games\src\app\wrath\page.tsx`)

**No level or tier change this session.** The party is still **Level 11**, with Caleth at Mythic 4 and the other three at Mythic 5. The Vanguard header, the per-card tiers and the footer's **Mythic Tier 4–5 · Level 11** are unchanged. Only the footer's code comment was touched, to read "Sessions 24–26."

⚠ **The games repo still had the Session 25 pass uncommitted** when this pass began (last commit there: `9f13f57 Week 24 plus an audit`). This pass was made on top of it. Both sessions' changes go live together whenever `page.tsx` is next committed on `main`.

---

## What changed

### `G:\Projects\games\src\app\wrath\page.tsx`

**Campaign Arc Status — session header (~line 463)**
- Top label: `Session XXV — Someone Who Might Listen` → **`Session XXVI — Under My Protection`**
- Gold title: `The Bell of Mercy` → **`The Hallowed Tower`**

**Campaign Arc Status — narrative paragraph (~line 470)**
- Fully replaced. It covers:
  - the week's walk west behind Nageru
  - the Gray Road crossing, fold by fold
  - the stone forest and the ruined fortress of Desna
  - Thane ringing the bell, and the tower becoming holy ground
  - the hunt broken and the hag dead
  - Arueshalae unharmed inside, and Desna waking the woman she used to be
- Highlighted span: *"Arueshalae"*, with `{" "}` on both sides.

**Campaign Arc Status — Terendelev card (~line 489)**
- **Refreshed.** The new quote is about her never asking Kenabres for leave to guard it: nobody vouched for her, and she stood between the city and the fire without explaining herself. One closing clause ties it to this session: one of the knights *"learned what she knew all along: what it costs to stand in front of something and say, this one is mine to keep."* It echoes Caleth's protection without naming him or recapping the plot, and it passes the hard rule.

**Campaign Arc Status — four PC cards (~lines 503–528)**
All four role labels and paragraphs replaced:
- **Caleth**: *The One Who Asked the Questions* → **The One Who Stood Beside Her**. Thirty-six folds through the Gray Road, the wand refilled, fire turned to winter, the bebilith sent home, the holy ground noticed, *"why should we not send you home,"* the vow to kill the man behind it all, and the protection named before Drezen's commanders.
- **Nageru**: *The One She Called by Name* → **The One Who Said "I'm Here"**. A week leading the horses, Desna's runes, *"I'm here,"* the hag's claws, and staying behind with her alone.
- **Thane**: *The One Who Cast It Himself* → **The One Who Rang the Bell**. Up the tower on the scale, the bell rung, first to meet her, the hag killed unseen, and the question that got the Ivory Sanctum answer.
- **Korroc**: *The One Who Went Over the Wall* → **The One Who Said Yes**. The half-bonds on three at dawn, armor torn off, living gold, feeling the wizard bleed, *"she's not evil,"* *"Yes we can,"* and the axe stuffed in his pack.

**Campaign Arc Status — milestone box (~lines 539–563)**
- Status title: `West, Toward the Bell` → **`A Demon in Drezen`**
- Subtitle: → **`The bell was rung · The hag is dead · She knows the way`**
- Summary fully replaced:
  - home by folds the same night, with the horses lost
  - the wizard found up a stone tree
  - the bell left behind, bound and house-heavy
  - Caleth's protection and Irabeth's reply
  - ends: *"a demon in a citadel of three hundred paladins, and she knows the way to the Ivory Sanctum."*
- Highlighted span: *"Ivory Sanctum"*, with `{" "}` before it.
- Footer values unchanged; the comment now reads "Sessions 24–26."

**Theater of War map — pin tooltips**
- **Citadel Drezen** (~line 209): rewritten. *"Held, and mended."* The wall is rebuilt, and *"a demon, walking in under a knight's protection."*
- **Temple of Irori** (~line 219): its last two sentences were rewritten. The pilgrims tend it now, and the knights rested there a night, then walked west for a week.
- **The Molten Scar** (~line 269): **removed the clause calling the Gray Road a levee along the lava river.** Per Will (Session 26), **the whole dead river is the Gray Road**; the pin now just reads *"A river of lava, four days from Drezen on foot."* The rest of the pin is unchanged.
- All other pins evaluated and left alone. **Still no pin for the Bell of Mercy fortress**: it lies a week west of the fane, off the edge of the map art.

**Theater of War — sidebar**
- **Citadel Drezen briefing**: rewritten. The walls are mended and the bolts are still being made. The knights came back with no horses, a wounded wizard, and a demon who walks the citadel under a knight's protection. *"She has been to the Ivory Sanctum. She knows the way."*
- **Commander's Note**: rewritten in Irabeth's voice, opening with her own line from the session, *"What are they doing to me?"*, then the three hundred paladins, *"He will not be the only one they answer to,"* and *"Then she had better be worth it."*

---

## Secrets kept off the page

- **The night talk at the Gray Road** (Aravashnial pressing Caleth to doubt Nageru) is not mentioned. Only Caleth knows it.
- **Nageru's private talk with Arueshalae** (her distrust of the dwarves) is not mentioned.
- **That Aravashnial is Caleth's uncle**, and **what is wrong with him**, are still off the page.
- **Where the Ivory Sanctum is** is not stated anywhere, because it isn't established. The page says only that she knows the way.
- **What sent the dream** is not mentioned.

---

## Files NOT touched

- **`{/* FROM THE WAR CHRONICLE */}`**: auto-loads the latest dispatch from `/api/stories?campaign=wrath&limit=1`.
- **The Vanguard section**: no level or tier change.
- **Map art and pin coordinates**: unchanged.
- **Hero section text, Worldwound Incursion intro, Rules/Resources nav**: static page furniture.

---

## Verification

1. Run the games site with the `games-dev` configuration in `wrath-story-book/.claude/launch.json` (port 3000), then open `http://localhost:3000/wrath`.
2. Scroll to **Campaign Arc Status**. The top label should read **SESSION XXVI — UNDER MY PROTECTION** and the gold title **The Hallowed Tower**.
3. Four cards: **THE ONE WHO STOOD BESIDE HER / WHO SAID "I'M HERE" / WHO RANG THE BELL / WHO SAID YES**.
4. Milestone box: **A DEMON IN DREZEN**. The footer should still read **BOOK 3 OF 6 | MYTHIC TIER 4–5 | LEVEL 11**.
5. Word-jam check: *"burned her, was Arueshalae —"* and *"the way to the Ivory Sanctum."* should read normally. *(Both were verified against the rendered page text this pass.)*
6. Hover the **Drezen pin**: it should begin *"Held, and mended."* Hover the **Molten Scar pin**: it should begin *"A river of lava, four days from Drezen on foot."*
7. `npx tsc --noEmit` returned **zero errors**, and the browser console showed no errors.

---

## Cross-references

- Design pattern and update process: `wrath-story-book/memory/webpage-session-section.md`
- Chapter that drove this: `wrath-story-book/chapters/26-the-hallowed-tower.md`
- Session notes: `wrath-story-book/sessions/session26.md`
- New canon from this session: `memory/arueshalae-and-the-bell-of-mercy.md`, `memory/aravashnial-taken.md`, `memory/caleth-enduring-armor.md`
- Gray Road ruling: `lore/worldwound.md` → *The Gray Road*
- Previous changelog: `wrath-story-book/website/update25.md`
