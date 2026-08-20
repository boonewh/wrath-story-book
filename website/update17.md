# Session 17 — Every Name But Two
**Date:** 2026-08-16
**Driven by:** Chapter 17 written (Thane POV). The aftermath in the map room — Jordan Vhane's Droskar text, and **Staunton Vhane's journal** — then the descent into the chambers below: prison rows and two risen paladins, the antimagic interrogation block, **Arueshalae's abandoned cell**, six caged vampire spawn left alive, a torture chamber, the vampire **Nul** destroyed and the crusader **Idrian Vosner** rescued, the corruption forge, **Chorussina's ritual broken**, **Jordan's healing lost**, and the **decoy Sword of Valor** at the end of a hall of murdered gods. **No level-up this session.**
**Live page:** `/wrath`

## What Changed

### `games/src/app/wrath/page.tsx` — Vanguard section (~line 126)

- **Level/Mythic line UNCHANGED: "Level 9 Gestalt • Mythic Tier 2."** Verified against the session notes and the player's after-action report — Session 17 granted no level and no tier. Checked deliberately per the keep-in-sync comment; the status-box footer likewise unchanged. **Both still agree.**

### `games/src/app/wrath/page.tsx` — Theater of War / strategic map section (~lines 186–277)

- **Citadel Drezen pin** (top-[28%] left-[41%]): **stays RED.** Label rewritten — the company is now several levels beneath the cleared halls, the city-destroying ritual is broken, and the Banner at the bottom of the deepest hall was a fake. Still not taken.
- **Sidebar "Citadel Drezen"** rewritten around the session's real discovery: the place has two natures. Above it is a fortress; below it is prison rows, a magic-warded interrogation block, a relic-corrupting forge, and halls of murdered gods — none of it dwarven work, all of it cut into dwarven work afterward.
- **Sidebar "Commander's Note"** re-quoted to the chapter's emotional center: the traitor's ledger, the relics he catalogued, the invitation to *read every name* — and the two names that are not in it. Ends on *"it will not be an answer."*
- **Unchanged pins:** Ahari Bridge, Paradise Hill, The Unnamed Bridge, Crusader Camp, The Cemetery. All still accurate; the army's situation on the field did not change on-page this session (the four were underground the whole time). Tally remains 5 blue / 1 red; legend needs no change.
- **Map image and all pin coordinates unchanged** — the entire session took place inside and beneath one pin.

### `games/src/app/wrath/page.tsx` — Campaign Arc Status section (~line 444)

- **Session header:** "Session XVI — Sword of Valor" → **"Session XVII — Sword of Valor"**; gold title → **"Every Name But Two"**.
- **Narrative paragraph:** replaced entirely. The journal and its three loadbearing admissions (he took the Sword himself; Minagho gave the opportunity and the choice was his; the ledger, and the invitation to read every name in it), then the descent — standing paladins in their cells, the warded block, the butterfly cell and the thing that prayed its way out, the vampire, the forge, the conjurer six words into a ritual meant to level half the city. Closes on the whispering that did not stop.
- **Terendelev card:** quote refreshed — **and then rewritten**, because the first attempt had drifted into recounting the session's plot (the butterfly cell, Jordan's hands) instead of being about Terendelev. **This card is a tribute, not a recap.** The shipped version is entirely about her: that she could have been anywhere and chose a city and a plain grey face, that she did not leave when the sky opened, that she spent the last thing she had slowing four strangers' fall — and that those four are underground in a fortress that has not heard her name in seventy-five years, still carrying her scales and still spending them one at a time, the way she spent herself. **Guideline going forward: the Fallen Guardian card may take its emotional color from the current session, but its subject is always Terendelev.**
- **Party contribution cards:** all four replaced. `name` and `classes` unchanged; **all four `role` labels changed:**
  - **Caleth** — *The Answering Blade* → **The Case for Mending.** The forge argument (unfinished, deliberately), the antimagic cell he would not go near, and the mythic lightning that ended the ritualist.
  - **Nageru** — *The Word Before the Fist* → **The One Who Makes Sure.** Found the journal; gave the day its four-word prophecy; the full stake-axe-holy-water liturgy on Nul. Ends on the crystal crack nobody noticed.
  - **Thane** — *The Patient Dark* → **The Name Not Written.** Wanted answers, got a diary; the ledger, the three shields and the filed-off breastplate; then the snapped pick and the trap that beat him — and the last door he opened anyway.
  - **Korroc** — *The Open Hand* → **The Smith's Patience.** Stopped the book-burning, carried the journal to the brother it insulted, offered Torag with a death sentence attached to keep it honest — and then reached for his god over a wound and got nothing back.
- **Status box:** title "The Traitor Is Dead" → **"Something Is Still Whispering"**; subtitle → "The city saved · The Banner still missing · A door nobody was meant to find"; summary replaced. The ritual broken, the whisper that was never the ritual and did not stop, the decoy Banner turning black in its frame, and the seam twenty feet up a blank wall with a second door behind it.
- **Footer UNCHANGED:** Book 2 of 6 | Mythic Tier 2 | Level 9. In sync with the Vanguard line.

## Files NOT Touched

- **"From the War Chronicle" section** — auto-loads the latest entry from `/api/stories`; no manual edit needed. (Chapter text is entered through the website and stored in Vercel storage, not in this repo.)
- **Theater of War header, subtitle ("Intelligence Report: The Drezen Approach"), legend labels** — still accurate.
- **Hero, intro narrative, Worldwound divider, transition, gallery, Vanguard character cards and images, page footer** — nothing in Session 17 touches them.
- **Vanguard Level/Mythic line and status-box footer** — evaluated and correctly left alone; no advancement this session.
- **Map pin coordinates** — deliberately unchanged; see above.

## Guardrails Observed

- Grep-verified **0 hits** on the page for: `Nurah`, `Riftwarden`, `blueprint`, `Kiranda`, `Arueshalae`, `Eustoyriax`, `Chorussina`, `Vosner`.
  - **Arueshalae is described but not named** — "a thing born of the Abyss… begging a goddess of stars for a spirit made clean." She is a major future NPC; the page keeps its cast tight and lets the name land in prose first. Same reasoning applies to **Eustoyriax** (the shadow demon keeping the true Banner), who is not mentioned at all, and to **Idrian Vosner**, the rescued crusader.
  - **Chorussina** appears only as "the conjurer" / "the ritualist." Style choice, consistent with prior sessions; no spoiler reason.
- **Caleth's dread of the antimagic cell is shown and NOT explained** — the card says he walked wide around it *and would not say why.* His Chapter 15 wound is still unspoken in-fiction and stays unspoken here.
- **Jordan Vhane's lost healing is stated without a cause**, matching canon: claw, ritual, crystal, or god — the table has not decided and the page does not guess.
- **The crystal-crack causation is presented as unnoticed, not as fact** — "and nobody noticed" is true of the party either way.
- REPLACE-not-append honored throughout; no cards added, no archive block.
- Name spellings verified: Staunton Vhane, Jordan Vhane, Korroc, Caleth, Nageru, Thane, Iomedae, Radiance, Torag, Minagho, Drezen.

## Verification

1. Load `/wrath` (dev server, or the live site after deploy).
2. Vanguard header still reads **"Level 9 Gestalt • Mythic Tier 2"** — unchanged this session, by design.
3. Theater of War: still five blue pins and one red. Hover **Citadel Drezen** — should read *ritual broken, Banner at the bottom was a fake, still not taken.*
4. Sidebar "Citadel Drezen" describes the fortress-above / prison-and-forge-below split.
5. Sidebar Commander's Note carries the ledger quote, ending *"it will not be an answer."*
6. Campaign Arc Status header reads **"Session XVII — Sword of Valor"** / **"Every Name But Two"**.
7. All four contribution cards show the new role labels: **The Case for Mending, The One Who Makes Sure, The Name Not Written, The Smith's Patience.**
8. Status box: **"Something Is Still Whispering"**; footer reads **Book 2 of 6 | Mythic Tier 2 | Level 9**.
9. Confirm the eight guardrail terms above appear nowhere on the page.
10. **Commit on `main`** — work committed to a side branch never reaches Vercel (Session 12's lesson).

## Build Status

- `node_modules` **is** installed in `G:\Projects\games` this time (unlike the Session 16 pass).
- `npx tsc --noEmit` run after the edits. **No errors in `src/app/wrath/page.tsx`.** Two pre-existing errors remain in `src/lib/tracker/merge.test.ts` (optional-property strictness in test fixtures) — unrelated to this pass and present before it.
- All edits confined to JSX text and string literals; no structural or import changes. Apostrophes in JSX text escaped as `&apos;`; apostrophes inside the card-array JS strings are typographic `’` and need no escaping.

### ⚠ JSX whitespace — the recurring `<span>` word-jam

Twice this pass, highlighted spans rendered glued to the following word (*"the Sword of Valorhanging"*, *"himself.He wrote"*) even though a literal space was present in the source. **JSX strips whitespace adjacent to tags when a line break is involved, so a plain space next to `</span>` is not reliable in this file's wrapped-prose formatting.**

**The fix, which this file already established in the Session 16 pass, is an explicit `{" "}`:**

```jsx
company found{" "}
<span className="text-zinc-300">the Sword of Valor</span>{" "}
hanging in an iron frame — and it was a joke.
```

**Rule for future sessions: any inline `<span>` inside a wrapped prose paragraph gets `{" "}` on both sides, on its own line.** Do not rely on a literal space. Both Session 17 spans (the narrative paragraph's *He took the Sword of Valor himself* and the status box's *the Sword of Valor*) now use this form. Audited the rest of the page: the only other `</span> word` pattern is the hero title on line 99, which is a single unwrapped line and renders correctly.

## Cross-References

- Design pattern: `wrath-story-book/memory/webpage-session-section.md` — **updated this pass.** Three additions promoted into it so they stop recurring: (1) the **hard rule that the Fallen Guardian card is a tribute to Terendelev, not a session recap**, with the "delete her name and see if it still reads as a recap" test; (2) a new **Technical gotchas** section covering the `<span>` word-jam and the mandatory `{" "}` form; (3) **its dead pre-reinstall paths corrected** to `G:\Projects\games` and `G:\Projects\wrath-story-book`.
- Chapter: `wrath-story-book/chapters/17-every-name-but-two.md`
- Session notes: `wrath-story-book/sessions/session17.md`
- Prior changelog: `wrath-story-book/website/update16.md`
