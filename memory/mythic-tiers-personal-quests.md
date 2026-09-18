---
name: mythic-tiers-personal-quests
description: As of Session 21 the party is Level 10 but mythic tiers DIVERGE - each PC gains a tier by completing a personal quest. Nageru is Tier 4 (the fane); the others are Tier 3. Track tier per character everywhere.
metadata:
  type: project
---

**Rule (from Session 21): the party shares a level, but mythic tier is per character.**

| PC | Level | Mythic Tier | Personal quest |
|---|---|---|---|
| **Nageru** | 10 | **4** | ✔ **The lost fane of Irori** (Ch 21). Done. |
| Caleth | 10 | 3 | ⚠ **Probably rescuing Aravashnial.** Will's guess, not the GM's confirmation. |
| Thane | 10 | 3 | Not stated. |
| Korroc | 10 | 3 | Not stated. |

**Why:** the GM is running a personal quest for each character, and completing it grants that character a mythic tier. **The divergence is temporary.** It evens out as the others finish theirs. Said by Will, 2026-09-13.

## How to apply

- **Never write "the party is Mythic Tier N" again.** Say "Level 10" for the party, and give tiers per character.
- **Do not invent the other quests.** Thane's and Korroc's are unstated, and Caleth's is a guess. The obvious candidates (the Stonevein fathers for the cousins, Aravashnial for Caleth) are exactly the kind of thing to **ask about, not assume.** When a session looks like one of them paying off, flag it and confirm before recording a tier change.
- **Personal quests line up with POV-by-stakes.** A session that completes a character's quest is almost certainly that character's POV chapter, as Ch 21 was for Nageru. Weigh that when recommending POV.
- **In prose, a new tier is not announced.** Mythic power shows in what the character can do. Don't have anyone remark that Nageru is now "stronger than the rest."

## Where tier lives now

- **Character files:** the `Level · Mythic Tier` line in each file's Current State.
- **CLAUDE.md:** Party State → Advancement.
- **Website (`games/src/app/wrath/page.tsx`):**
  - **Vanguard header** shows **level only** ("Level 10 Gestalt").
  - **Each Vanguard card** shows **its own tier** via a `tier` field in the card array.
  - **Milestone footer** shows **the tier range** ("Mythic Tier 3–4") plus the level. When everyone matches again, collapse the range to a single number.
  - When any tier changes, update **that card and the footer range** together.

Related: [[fane-of-irori]], [[aravashnial-taken]], [[webpage-session-section]].
