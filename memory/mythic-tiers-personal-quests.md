---
name: mythic-tiers-personal-quests
description: As of Session 26 (no change since 24) - LEVEL 11; Nageru 5 (since S22, fane), Thane + Korroc 5 (the fathers' plotline, S24), Caleth 4 (next; Will expects Vang). Granted per character by personal quest; track per character and never assume they stay matched.
metadata:
  type: project
---

**Rule (from Session 21): the party shares a level, but mythic tier is per character.**

## ⚠⚠ STATUS AFTER SESSION 27: LEVEL 11. CALETH 4, EVERYONE ELSE 5.

*(Session 27: no advancement, Will, 2026-10-24. The **legendary items** made that session, Korroc's shield, Thane's punch dagger and Nageru's amulet, are mythic abilities **gained at earlier tier bumps** and only ritualized now. **A new mythic ability on the page is NOT a tier change.** See [[legendary-items-and-the-axe]].)*

*(Session 26: no advancement — confirmed by Will, 2026-10-18. Session 25: none either, 2026-10-11.)*

| PC | Level | Mythic Tier | Personal quest |
|---|---|---|---|
| **Nageru** | **11** | **5** | ✔ **The fane of Irori** (Ch 21) put him one tier ahead of everyone. **He has been Tier 5 since Session 22** — he went up again when the rest went to 4. |
| **Thane** | **11** | **5** | ✔ **The fathers' plotline** — completed at Sesker's Gully (Ch 24). |
| **Korroc** | **11** | **5** | ✔ **The fathers' plotline** — completed at Sesker's Gully (Ch 24). |
| **Caleth** | **11** | **4** | **Next.** Will expects **Vang** to be what his next tier takes. ⚠ *That is Will's expectation, not a stated quest — don't write it as fact or pre-empt it.* |

*(Will, 2026-10-04. Caught after the Session 24 web pass had shipped with Level 10 / Mythic 4. The session notes do not mention advancement, so ask about levels and tiers at every session pass.)*

### ⚠ Correction to the Session 22 record below
Will, 2026-10-04: **Nageru was Mythic 5 from Session 22, not 4.** He went one tier ahead with the fane (Ch 21), then went up again when the other three reached 4. The table below, and the Session 22–23 website passes (*"Level 10 Gestalt · Mythic 4"* for everyone), had him wrong. The old changelogs (`website/update22.md`, `update23.md`) are left as written records.

**The pattern:** each completed personal quest puts that character one ahead, and the GM periodically brings the others up. Nageru's fane (S21) → +1. Caleth's Woundworm (S22) → the other three came up with him, so Nageru reached 5. The cousins' fathers (S24) → 5.

## Session 22 record (superseded, and wrong about Nageru, who was 5 — see the correction above)

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

- **Never write "the party is Mythic Tier N" again.** Say "Level 11" for the party, and give tiers per character.
- **⚠ Ask about level and tier at every session pass.** The session notes don't carry advancement; Session 24's was missed until the web update was done.
- **Do not invent the other quests.** Thane's and Korroc's are still unstated. The obvious candidates (the Stonevein fathers for the cousins) are exactly the kind of thing to **ask about, not assume** — see the Caleth misfire above. When a session looks like one of them paying off, flag it and confirm before recording a tier change.
- **Personal quests line up with POV-by-stakes.** A session that completes a character's quest is almost certainly that character's POV chapter — Ch 21 for Nageru, Ch 22 for Caleth. Weigh that when recommending POV.
- **In prose, a new tier is not announced.** Mythic power shows in what the character can do. Nothing in Ch 22 remarks on anyone's advancement and nothing should.

## Where tier lives now

- **Character files:** the `Level · Mythic Tier` line in each file's Current State.
- **CLAUDE.md:** Party State → Advancement.
- **Website (`games/src/app/wrath/page.tsx`):**
  - **⚠ As of Session 24 the per-card shape is BACK:** **Vanguard header** shows **level only** ("Level 11 Gestalt").
  - **Each Vanguard card** shows **its own tier** via a `tier` field in the card array.
  - **Milestone footer** shows **the tier range** plus the level — **"Mythic Tier 4–5 · Level 11"** as of Session 24. *(Sessions 22–23 had it collapsed to "4" with the tier in the header.)*
  - When any tier changes, update **that card and the footer** together. **Session 22 changes all four cards** — Caleth, Korroc and Thane from 3 to 4 — plus the footer.

Related: [[fane-of-irori]], [[aravashnial-taken]], [[webpage-session-section]].
