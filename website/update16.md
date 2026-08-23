# Session 16 — Two Brothers of the Same Forge
**Date:** 2026-08-09
**Driven by:** Chapter 16 written (Korroc POV). The upper citadel finished — brimoraks on the northern parapet, a nabasu feeding on its own garrison's dead, a staged "rescue" that was the succubus Kiranda all along, thoxels at the arrow slits, fiendish minotaurs, babaus — and then the map room: **Staunton Vhane killed**, Kiranda destroyed, and **Joran Vhane surrendered** to Korroc in exchange for the Sword of Valor's location. **Party leveled: Level 9, Mythic Tier 2.**
**Live page:** `/wrath`

## What Changed

### `games/src/app/wrath/page.tsx` — Vanguard section (~line 126)

- **Level/Mythic line UPDATED:** "Level 8 Gestalt • Mythic Tier 2" → **"Level 9 Gestalt • Mythic Tier 2"**. Changed together with the status-box footer (see below) per the keep-in-sync comment. Tier unchanged.

### `games/src/app/wrath/page.tsx` — Theater of War / strategic map section (~lines 186–286)

- **Citadel Drezen pin** (top-[28%] left-[41%]): **stays RED.** The upper halls are cleared and its master is dead, but the fortress is not taken — everything that matters is below. Label rewritten to say exactly that.
- **Crusader Camp pin** label updated: the army now has the upper hand on the field, and the camp holds **a bound prisoner awaiting the Queen's judgment** (Nurah, unnamed on the page — see Guardrails).
- **Sidebar "Citadel Drezen"** rewritten: upper halls cleared, the traitor who held them dead, the fortress still not taken, and the real object below in "chambers no dwarf ever drew."
- **Sidebar "Commander's Note"** re-quoted to the session's actual lesson: Vhane is dead, and the cost was two stolen faces — a goddess's and a rescued man's — one of which **fought at the company's own side for two rooms before it struck.** Closes on the unmapped halls below: *"Trust the work of a thing, not the face of it."*
- **Unchanged pins:** Ahari Bridge, Paradise Hill, The Unnamed Bridge, The Cemetery (all blue, all still accurate). Pin tally remains 5 blue / 1 red; legend needs no change.
- **Map image and all pin coordinates unchanged** — no territory changed hands on the map this session; the fighting was interior.

### `games/src/app/wrath/page.tsx` — Campaign Arc Status section (~line 444)

- **Session header:** "Session XV — Sword of Valor" → **"Session XVI — Sword of Valor"**; gold title → **"Two Brothers of the Same Forge"**.
- **Narrative paragraph:** replaced entirely — the northern-wall fight, the thing feeding on its own garrison, the chained man freed and armed who came apart into a demon with a blade already in Caleth's back, and then the map room: Staunton Vhane named in the open, the killing blow the stone refused, the traitor dead, and **every name he could have given up dying with him.** Ends on the brother who knelt.
- **Terendelev card:** quote refreshed. Advances the face-motif into a three-lie tally — a demon in a goddess's face, a demon in a rescued man's, and a traitor who wore a crusader's face for seventy-five years — against her one plain grey face that was a gift. Same elegiac register.
- **Party contribution cards:** all four replaced. `name` and `classes` unchanged; **all four `role` labels changed** this session (they had gone stale against the new material):
  - **Caleth** — *The Painter's Fury* → **The Answering Blade.** Took the ice blade in the back, killed the demon that dealt it, then ended Staunton Vhane with three thrusts of Radiance.
  - **Nageru** — *The Thunder's Reach* → **The Word Before the Fist.** Told to talk instead of strike mid-fight, and did — the offer that is the only reason a man knelt at the end instead of dying. Paid three glaive-thrusts for it and rose.
  - **Thane** — *Shadow of Judgment* → **The Patient Dark.** Distrusted the chained man and was overruled and proved right the worst way; five blades into Staunton from behind; asked for him alive and was refused by his own cousin.
  - **Korroc** — *The Wall That Walks* → **The Open Hand.** The mercy that cost them, the mercy he offered anyway, the second burning of his life, the killing blow the stone in his blood would not let through, and a judgment offered instead of a grave.
- **Status box:** title "Toward the Dark Below" → **"The Traitor Is Dead"**; subtitle → "A debt three generations old · The way down still ahead"; summary replaced — the kill, the cost (the Templar chain died with him, over one cousin's objection), the brother who knelt and agreed to lead them, the decoy Banner, and the unmapped chambers below where a sorceress is said to wait.
- **Footer UPDATED:** Book 2 of 6 | Mythic Tier 2 | **Level 9** (was Level 8). In sync with the Vanguard line.

## Files NOT Touched

- **"From the War Chronicle" section** — auto-loads the latest entry from `/api/stories`; no manual edit needed. (The chapter text itself is entered through the website and stored in Vercel storage, not in this repo.)
- **Theater of War header, subtitle ("Intelligence Report: The Drezen Approach"), legend labels** — still accurate.
- **Hero, intro narrative, Worldwound divider, transition, gallery, Vanguard character cards and images, footer** — nothing in Session 16 touches them.
- **Map pin coordinates** — deliberately unchanged; see above.

## Guardrails Observed

- **"Nurah" appears nowhere on the page** — she is "a bound prisoner… for the Queen's judgment" only. Verified by grep (0 hits). Note that her guilt is now *proven* in canon, so naming her would no longer be a spoiler — this is a style choice to keep the page's cast tight, and can be revisited.
- **"blueprint" — 0 hits.** Confirmed.
- **"Riftwarden" — 0 hits.** Confirmed. No secrets: nothing about Caleth's lineage, the Caleth–Aravashnial connection, or the unanswered "we should talk later."
- **"Kiranda" — 0 hits.** The succubus is described by what she did, not named; the party never learned her name aloud on-page.
- **Korroc's armor mystery is referenced but NOT explained** (per GM instruction), and only in the prior session's framing — the Session 16 cards do not re-litigate it.
- REPLACE-not-append honored throughout.
- Name spellings verified: Staunton Vhane, Korroc, Caleth, Nageru, Thane, Ahari, Iomedae, Radiance.

## Verification

1. Load `/wrath` (dev server, or the live site after deploy).
2. Vanguard header reads **"Level 9 Gestalt • Mythic Tier 2"**.
3. Theater of War: still five blue pins and one red. Hover **Citadel Drezen** — it should read *upper halls cleared, master dead, still not taken, everything below.* Hover **Crusader Camp** — army has the upper hand, bound prisoner held.
4. Sidebar Commander's Note carries the Vhane-is-dead / trust-the-work-not-the-face quote.
5. Campaign Arc Status header reads **"Session XVI — Sword of Valor"** / **"Two Brothers of the Same Forge"**.
6. All four contribution cards show the new role labels: The Answering Blade, The Word Before the Fist, The Patient Dark, The Open Hand.
7. Status box: **"The Traitor Is Dead"**; footer reads **Book 2 of 6 | Mythic Tier 2 | Level 9**.
8. Confirm "Nurah", "blueprint", "Riftwarden", and "Kiranda" appear nowhere on the page.
9. **Commit on `main`** — work committed to a side branch never reaches Vercel (Session 12's lesson).

## Known Gaps

- **`update14.md` and `update15.md` were never written.** The page *was* updated for both sessions; only the changelogs are missing, and they were lost with the drive. They can be reconstructed from git history of `page.tsx` plus chapters 14–15 if wanted — flagged, not done.
- **`node_modules` is not installed in `G:\Projects\games`**, so this pass was not type-checked or built. Changes were confined to JSX text and string literals (no structural or import changes); `<span>` tags in the edited region were verified balanced and all apostrophes in JSX text are escaped as `&apos;`. **Run `npm install && npm run build` before deploying.**

## Cross-References

- Design pattern: `wrath-story-book/memory/webpage-session-section.md`
- Chapter: `wrath-story-book/chapters/16-two-brothers-of-the-same-forge.md`
- Session notes: `wrath-story-book/sessions/session16.md`
- Prior changelog: `wrath-story-book/website/update13.md` (14 and 15 missing — see Known Gaps)
