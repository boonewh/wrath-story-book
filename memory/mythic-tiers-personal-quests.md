---
name: mythic-tiers-personal-quests
description: Level 10, and as of Session 22 ALL FOUR are Mythic Tier 4 - the divergence closed. Tiers are still granted per character by personal quest, so track them per character and never assume they stay matched.
metadata:
  type: project
---

**Rule (from Session 21): the party shares a level, but mythic tier is per character.**

## ✔ STATUS AFTER SESSION 22: ALL FOUR ARE TIER 4. THE DIVERGENCE IS CLOSED.

| PC | Level | Mythic Tier | Personal quest |
|---|---|---|---|
| **Nageru** | 10 | **4** | ✔ **The lost fane of Irori** (Ch 21). Done. |
| **Caleth** | 10 | **4** | ✔ **Granted in Session 22 for killing the Woundworm**, the six-legged dragon that took Aravashnial. ⚠ **NOT for rescuing Aravashnial — that attempt failed.** The earlier guess in this file was wrong; see below. |
| **Thane** | 10 | **4** | Not stated. **The GM brought him up with the others in Session 22** to level the party. |
| **Korroc** | 10 | **4** | Not stated. **The GM brought him up with the others in Session 22** to level the party. |

**Why:** the GM runs a personal quest per character, and completing it grants that character a tier. Nageru got his in Session 21. **In Session 22 the dragon's death was Caleth's key — and rather than leave three characters staggered, the GM granted Korroc and Thane the tier as well and brought everyone level.** Said by Will, 2026-09-20.

⚠ **THE DIVERGENCE CLOSING IS NOT THE RULE CHANGING.** Tiers are still granted per character, and Thane's and Korroc's quests are still unstated and still out there. **Do not assume the four stay matched**, and do not write a single party tier as a permanent fact — write what each character currently is.

### ⚠ A guess in this file was wrong, and it is worth remembering why
This file previously recorded *"Caleth's quest is probably rescuing Aravashnial"* as Will's guess. **The session that granted Caleth his tier was the session the rescue failed.** The tier came off **the dragon**, which nobody had flagged as anyone's quest. **This is the case for the standing instruction below: ask, do not assume.**

## How to apply

- **Never write "the party is Mythic Tier N" again.** Say "Level 10" for the party, and give tiers per character.
- **Do not invent the other quests.** Thane's and Korroc's are still unstated. The obvious candidates (the Stonevein fathers for the cousins) are exactly the kind of thing to **ask about, not assume** — see the Caleth misfire above. When a session looks like one of them paying off, flag it and confirm before recording a tier change.
- **Personal quests line up with POV-by-stakes.** A session that completes a character's quest is almost certainly that character's POV chapter — Ch 21 for Nageru, Ch 22 for Caleth. Weigh that when recommending POV.
- **In prose, a new tier is not announced.** Mythic power shows in what the character can do. Nothing in Ch 22 remarks on anyone's advancement and nothing should.

## Where tier lives now

- **Character files:** the `Level · Mythic Tier` line in each file's Current State.
- **CLAUDE.md:** Party State → Advancement.
- **Website (`games/src/app/wrath/page.tsx`):**
  - **Vanguard header** shows **level only** ("Level 10 Gestalt").
  - **Each Vanguard card** shows **its own tier** via a `tier` field in the card array.
  - **Milestone footer** shows **the tier range** plus the level. ⚠ **After Session 22 the range collapses: it should read "Mythic Tier 4", not "3–4".** If it ever diverges again, go back to a range.
  - When any tier changes, update **that card and the footer** together. **Session 22 changes all four cards** — Caleth, Korroc and Thane from 3 to 4 — plus the footer.

Related: [[fane-of-irori]], [[aravashnial-taken]], [[webpage-session-section]].
