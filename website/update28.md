# Session 28 — The Worm's House

**Date:** 2026-11-07 (catch-up pass, done at the start of the Week 29 session; the Week 28 web update was skipped)
**Driven by:** `chapters/28-strangers-faces.md` (Thane POV) and `sessions/session28.md`
**Live page:** `/wrath` (route served from `G:\Projects\games\src\app\wrath\page.tsx`)

**No level or tier change this session.** The party is still **Level 11**: Caleth at Mythic 4, Nageru, Thane and Korroc at Mythic 5. The Vanguard header, the per-card tiers and the footer's **Mythic Tier 4–5 · Level 11** are unchanged. Only the footer's code comment changed, to read "Sessions 24–28."

The games repo was clean when this pass began (Week 27 was committed as `b0f0dab`, followed by a Vercel retrigger, `a6d9ccb`). An untracked `.codex-remote-attachments/` folder was already there and was left alone.

---

## What changed

### `G:\Projects\games\src\app\wrath\page.tsx`

**Campaign Arc Status — session header (~line 463)**
- Top label: `Session XXVII — What the Hand Remembers` → **`Session XXVIII — The Worm's House`**
- Gold title: `False Stone` → **`Strangers' Faces`** (the chapter title)

**Campaign Arc Status — narrative paragraph (~line 470)**
- Fully replaced. It covers:
  - Caleth's offer to locate Vang with one spell, and the choice to check every door instead
  - the study's seven-armed rune in iron that everyone walked around
  - the worm sarcophagus Korroc broke to gravel
  - the hidden bag: books, *"an elf's stolen spellbook,"* and unnamed trophies
  - soldiers, templars, the black-robed smith, two demons banished
  - ends: *"the one thing they did not find was Xanthir Vang."*
- Highlighted span: *"Xanthir Vang"*, with `{" "}` before it.

**Campaign Arc Status — Terendelev card**
- **Unchanged, after review.** It was refreshed last session and is about her scales. Its closing clause (the dwarves still spend theirs drifting down cliffs) is a general truth, not a Session 27 recap, so it has not gone stale. Session 28 offered nothing that would tie back to her honestly.

**Campaign Arc Status — four PC cards (~lines 500–525)**
All four role labels and paragraphs replaced:
- **Caleth**: *The One Who Asked Her Everything* → **The One Who Kept the Papers**. Offered the locating spell and was overruled. Found Vang's spellbook and Aravashnial's. Froze the swarm rather than burn the war-room papers (agents, elixir routes). *"I understand."*
- **Nageru**: *The One Who Taught Them to Sit* → **The One Who Pulled His Punches**. Through the soldiers and the hezrou. *"Nearly everything in it was magic,"* and the fireball flask he still carries. Knifed by Thane, hit back twice and held back both times.
- **Thane**: *The One Who Found the Door* → **The One Who Didn't Know Their Faces**. Read the floor wear to Vang's door, found the sarcophagus compartment, confused by the coloxus, came back with his knife in his cousin's side, inked the runes safe, and looked at each face before the last door.
- **Korroc**: *The One Who Left the Axe* → **The One Who Didn't Let Go**. Holy fire through the door, *"sleep in that,"* every wound down the link, *"because you're on it,"* his boots and hammer sending the hezrou home, and the master's tools.

**Campaign Arc Status — milestone box (~lines 535–557)**
- Status title: `Three Doors` → **`The Stair Down`**
- Subtitle: → **`His rooms searched · One man missing · The master not found`**
- Summary fully replaced: still inside the Sanctum, a short rest in the smokeless forge, Caleth's bag heavy with plunder, nine beds and nine of the garrison dead, the one man nobody saw leave (*"someone knows they are here"*), and the unwalked stair down off the north hallway.
- Highlighted span: *"somewhere deep"*, with `{" "}` before it.
- Footer values unchanged; comment updated.

---

## Secrets kept off the page

- **The three-moon book** (Aravashnial's mark with the middle moon full). Caleth took it in silence and Thane noticed. Not mentioned; whose it is is not established.
- **The coded Abyssal journal** Caleth slammed shut, and **the collar sketchbook**. Not mentioned.
- **"That's twice" / "Yes. Twice."** Private between Thane and Nageru, and it points at the unspoken Ch 18 possession. Nageru's card says only that he held back; Thane's card does not say he was aware during the confusion.
- **The weight under Caleth's "I understand."** The two words are on the card, and nothing about what is under them.
- **The empty purple-stained vials** (the elixirs). Not mentioned. The elixirs appear only as *"the roads the elixirs travel"* in the war-room papers, which the party read openly.
- **Whether the robed casters are Blackfire adepts.** Not stated; the smith is just *"a smith in black robes."*
- Aravashnial's spellbook being recovered is party-public, so it is mentioned.

---

## Files NOT touched

- **Theater of War map pins and sidebar**: nothing happened at Drezen or anywhere else on the map this session, and Drezen does not yet know what the knights found. The Drezen pin (*"The knights have gone southwest, with a demon to show them the way"*), the Citadel Drezen briefing and Irabeth's Commander's Note about the axe (still lent, still in Drezen) remain true. There is still no Green Gate pin (see `update27.md`).
- **`{/* FROM THE WAR CHRONICLE */}`**: auto-loads the latest dispatch from `/api/stories?campaign=wrath&limit=1`.
- **The Vanguard section**: no level or tier change.
- **Hero section text, Worldwound Incursion intro, Rules/Resources nav**: static page furniture.

---

## Verification

1. Run the games site with the `games-dev` configuration in `wrath-story-book/.claude/launch.json` (port 3000), then open `http://localhost:3000/wrath`.
2. Scroll to **Campaign Arc Status**. The top label should read **SESSION XXVIII — THE WORM'S HOUSE** and the gold title **Strangers' Faces**.
3. Four cards: **THE ONE WHO KEPT THE PAPERS / WHO PULLED HIS PUNCHES / WHO DIDN'T KNOW THEIR FACES / WHO DIDN'T LET GO**.
4. Milestone box: **THE STAIR DOWN**. The footer should still read **BOOK 3 OF 6 | MYTHIC TIER 4–5 | LEVEL 11**.
5. Word-jam check: *"did not find was Xanthir Vang."* and *"from somewhere deep."* should read normally. *(Both were verified against the rendered page text this pass.)*
6. Results this pass: `npx tsc --noEmit` returned **zero errors**, and the browser console showed **no errors**.

---

## Cross-references

- Design pattern and update process: `wrath-story-book/memory/webpage-session-section.md`
- Chapter that drove this: `wrath-story-book/chapters/28-strangers-faces.md`
- Session notes: `wrath-story-book/sessions/session28.md`
- New canon from this session: `memory/the-three-moon-mark.md`, `memory/thane-unspoken-possession.md` ("That's twice"), `memory/aravashnial-taken.md` (the recovered spellbook)
- Place details: `lore/worldwound.md` → *The Green Gate and the Ivory Sanctum*
- Previous changelog: `wrath-story-book/website/update27.md`
