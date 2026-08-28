# Session 18 — The Mark It Chose
**Date:** 2026-08-23
**Driven by:** Chapter 18 written (Korroc POV). The last two hidden rooms below the citadel — the marilith pit, the chamber where light did not work, six fake crystals and a real one — the shadow demon **Eustoyriax**, Thane possessed and freed, and the **true Sword of Valor** recovered from a marble slab. Then the Banner over the tall tower, the rout, and **Citadel Drezen taken.** Followed by a week of aftermath: the armour's mark, the forge redeemed, Nurah dead, the two dungeon debts paid.
**Advancement:** **MYTHIC TIER 2 → 3.** Level unchanged at 9. *(Tier confirmed by the user; level was not mentioned and has been held at 9 — see Open Question below.)*
**Live page:** `/wrath`

## What Changed

### `games/src/app/wrath/page.tsx` — Vanguard section (line 126)

- **`Level 9 Gestalt • Mythic Tier 2` → `Level 9 Gestalt • Mythic Tier 3`.** Updated together with the status-box footer per the keep-in-sync code comment. **Both agree.**

### `games/src/app/wrath/page.tsx` — Theater of War / strategic map (~lines 186–280)

- **⚠ CITADEL DREZEN PIN FLIPPED RED → BLUE.** This is the structural change of the session. Four class swaps on the pin: `bg-red-600` ×2, `border-red-600`, `text-red-600` → their `wardstone-blue` equivalents. Label rewritten: taken, the Banner down the tower, every road out closed at once, gates in within the hour, forge below cleansed and renamed.
- **Tally is now 6 blue / 0 red.** First time in the campaign's map history with no demon-held pin. **Legend left unchanged** — it is a key, not a scoreboard, and "Demon Held" needs to stay defined for future targets.
- **Crusader Camp pin** rewritten — the old text said *"A bound prisoner waits here for the Queen's judgment,"* which is no longer true on two counts (the camp is emptying into the citadel, and the prisoner is dead). New text covers both without naming her.
- **Sidebar "Citadel Drezen"** replaced. Old text described the fortress-above / dungeon-below split; that was the Session 17 discovery and is now history. New text is the aftermath: room-by-room clearing, the forge argued back into an honest tool over four days and renamed, and the two shrines being scrubbed on two sides of one courtyard with nobody having given the order.
- **Sidebar "Commander's Note"** re-quoted. Dropped the ledger quote (Session 17's) for the standing order about the **four missing Nahyndrian elixirs** — the session's live unresolved thread, and the most in-character thing a commander says the morning after a victory.
- **Unchanged pins:** Ahari Bridge, Paradise Hill, The Unnamed Bridge, The Cemetery. Still accurate.
- **Map image and all pin coordinates unchanged.**

### `games/src/app/wrath/page.tsx` — Campaign Arc Status section (~line 444)

- **Session header:** "Session XVII" → **"Session XVIII"** (arc label "Sword of Valor" retained — still Book 2). Gold title "Every Name But Two" → **"The Mark It Chose."**
- **Narrative paragraph:** replaced entirely. The second hidden door, the pit four times deeper than it looked, the room where light did not work, six fakes that produced real things anyway, the soul-grab, the possession and what it cost to break it, then the red cloth going off like a dam breaking. Closes on the whisper stopping **with the explicit statement that nobody can say why.**
- **Terendelev card:** quote replaced. **Checked against the hard rule** — subject is Terendelev throughout (the oldest thing in Kenabres, the grey face, the small life kept for longer than most kingdoms last, dying in the street she had walked in that face). **Exactly one closing clause touches the present:** the banner is up because those four went on falling in the direction she pointed them. Ran the deletion test — strip her name and it does not read as a session recap.
- **Party contribution cards:** all four replaced. `name` and `classes` unchanged; **all four `role` labels changed:**
  - **Caleth** — *The Case for Mending* → **The One Who Picked It Up.** Right about the stone and wrong about what it was doing; the deduction about the seventh crystal; picking up cloth that told him nothing; unfurling it from the tower. Notes that the forge argument was **taken off him, not won.**
  - **Nageru** — *The One Who Makes Sure* → **The One Who Said No.** The refused soul-draw and his two words; pulling every strike against a possessed friend; the killing blow; the six caged crusaders and the unhurried liturgy.
  - **Thane** — *The Name Not Written* → **The Blade He Wiped Clean.** The trap that picked him out of four; the possession; and the wiped clean knife. Includes the Stonevein rule in the card, because it is the beat that tells the reader he is back.
  - **Korroc** — *The Smith's Patience* → **The Smith Who Stood Aside.** The soul-grab; cutting every thread to his cousin; breaking the crystal on a wizard's word; the armour's mark at dawn; and standing aside on the forge cleansing.
- **Status box:** title "Something Is Still Whispering" → **"Drezen Is Taken."** Subtitle → "The Banner recovered · The citadel held · Four vials unaccounted for." Summary replaced: the banner down the tower, the hole in the noise, the closed escape-roads, the gates — then the week of unglamorous work, and the two things still open.
- **Footer:** Book 2 of 6 | **Mythic Tier 3** | Level 9. In sync with the Vanguard line.

## Files NOT Touched

- **"From the War Chronicle" section** — auto-loads the latest entry from `/api/stories`; no manual edit needed. Chapter text is entered through the website and stored in Vercel storage, not this repo.
- **Theater of War header, subtitle, legend labels** — legend deliberately retained despite 0 red pins; see above.
- **Hero, intro narrative, Worldwound divider, transition, gallery, Vanguard character cards and images, page footer** — untouched.
- **Map pin coordinates** — unchanged.

## Guardrails Observed

- Grep-verified **0 hits** on the page for: `Nurah`, `Riftwarden`, `blueprint`, `Kiranda`, `Arueshalae`, `Eustoyriax`, `Chorussina`, `Vosner`, `Joran`, `Staunton`, `Irabeth`, `Aravashnial`. **The page still names no NPCs at all** — only gods (Torag, Iomedae), the four PCs, and Terendelev. That is the established house style and this pass holds it.
  - **Eustoyriax** appears as "a shadow demon." **Joran Vhane** is not referenced this pass. **Nurah** is "one prisoner" who "chose to run, and then chose to fight." **Irabeth** is "a commander." **Aravashnial** is absent; the forge cleansing is described without an agent.
- **THE THREE UNRESOLVED THREADS ARE STATED AS UNRESOLVED, NOT EXPLAINED:**
  - **The whisper stopped and the page says outright that nobody can say why** — in both the narrative paragraph and the status box. Deliberate: the table has not resolved the source, and "it stopped" must not read as "it was solved."
  - **The four elixirs** are the Commander's Note and the status-box closer. Still missing.
  - **Joran Vhane's lost healing** is not mentioned this pass at all — no cause stated anywhere, matching canon.
- **Korroc's armour is explained only as far as the session explained it** — "armour that reads the man inside it and decides." No origin, no prior owner, no connection to his father. That remains open.
- **The Purity Forge is referred to by function, not by name** ("given a new name," "it has a new name now") — the naming belongs to the chapter prose first, consistent with how the page has handled every proper noun.
- REPLACE-not-append honored throughout; no cards added, no archive block.
- Name spellings verified: Korroc, Caleth, Nageru, Thane, Torag, Iomedae, Drezen, Terendelev, Kenabres.

## Verification

1. Load `/wrath` (dev server, or the live site after deploy).
2. Vanguard header reads **"Level 9 Gestalt • Mythic Tier 3."**
3. **Theater of War: all six pins are now blue.** Citadel Drezen should pulse blue, not red. Hover it — *taken, Banner down the tower, gates in within the hour.*
4. Legend still shows both "Crusader Held" and "Demon Held" even though nothing is red.
5. Hover **Crusader Camp** — should describe the camp emptying into the citadel, no bound prisoner waiting.
6. Sidebar "Citadel Drezen" describes the aftermath and the two shrines.
7. Sidebar Commander's Note is the standing order about the four vials.
8. Campaign Arc Status header reads **"Session XVIII — Sword of Valor"** / **"The Mark It Chose."**
9. All four contribution cards show the new role labels: **The One Who Picked It Up, The One Who Said No, The Blade He Wiped Clean, The Smith Who Stood Aside.**
10. Status box: **"Drezen Is Taken"**; footer reads **Book 2 of 6 | Mythic Tier 3 | Level 9.**
11. Confirm the twelve guardrail terms above appear nowhere on the page.
12. **Commit on `main`** — work committed to a side branch never reaches Vercel (Session 12's lesson).

## Build Status

- `npx tsc --noEmit` run after the edits. **No errors in `src/app/wrath/page.tsx`.** The two pre-existing errors in `src/lib/tracker/merge.test.ts` (optional-property strictness in test fixtures) remain and are unrelated to this pass — same two as Session 17.
- All edits confined to JSX text, string literals, and four Tailwind class swaps on the Drezen pin. No structural or import changes.
- **JSX `<span>` word-jam:** both new inline spans (*the true Sword of Valor* in the narrative paragraph; *every escape-road the demons had simply closed* in the status box) use the mandatory `{" "}`-on-both-sides-with-span-on-its-own-line form. Grep for `</span> [a-zA-Z]` returns four hits, all pre-existing and all safe: the hero title (line 99, unwrapped), the two legend spans (lines 179–180, unwrapped), and "Book 2 of 6" (line 548, unwrapped).
- Apostrophes in JSX text escaped as `&apos;` / `&ldquo;` / `&rdquo;`; apostrophes inside the card-array JS strings are typographic `’` and need no escaping.

## Open Question for the Next Pass

- **Did the party gain a character level this session, or only the mythic tier?** The user specified Mythic Tier 3 and did not mention a level. Level is held at **9** in both synced locations. Taking Drezen is the classic mythic-ascension trigger, so a tier-only advancement is entirely plausible — but if Level 10 also landed, it is a one-word change in exactly two places: `page.tsx` line 126 and line 552. The canon-pass character files (all four say "Level 9 · Mythic Tier 2") will need the same correction either way.

## Cross-References

- Design pattern: `wrath-story-book/memory/webpage-session-section.md` — **no changes needed this pass.** The Terendelev hard rule and the `{" "}` gotcha were both promoted into it during Session 17 and both worked as written.
- Chapter: `wrath-story-book/chapters/18-the-mark-it-chose.md`
- Session notes: `wrath-story-book/sessions/session18.md`
- Prior changelog: `wrath-story-book/website/update17.md`
