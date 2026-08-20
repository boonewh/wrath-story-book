---
name: webpage-session-section
description: The blog page's "SESSION I: CHARACTER PROGRESS" section is a current-state window, not an accumulating record. Replace its content per update; never append.
metadata:
  type: reference
---

The Wrath of the Righteous campaign blog page lives at `G:\Projects\games\src\app\wrath\page.tsx` (route: `/wrath`). *(Paths corrected 2026-08-16 — this file previously pointed at the pre-reinstall `C:\Users\William Boone\Desktop\…` locations, which no longer exist.)* One of its sections — currently commented `{/* SESSION I: CHARACTER PROGRESS */}` (around line 411) — is the **Campaign Arc Status** block. It is the only part of the page that's expected to evolve session-to-session.

**Design principle: REPLACE, don't ACCUMULATE.** The user explicitly does not want this section to grow over time. Each update REPLACES the content while keeping the structure intact. Older content lives elsewhere (the adventure-log chronicles, the chapter files); this section is a fresh window into the current moment.

## Structure (stable — do not change)

The section always contains, in order:

1. **Session Header** — small abyssal-red top label (e.g. *"Session IV — The Worldwound Incursion"*) + big gold title (the current arc/chapter narrative title, e.g. *"Above the Sunken Sky"*) + decorative diamond divider + one italic narrative paragraph summarizing the current arc.
2. **Fallen Guardian card** — Terendelev. This card can persist across many updates; she remains the campaign's foundational loss. Quote can refresh as her absence is felt differently over time.

   **⚠ HARD RULE — THE SUBJECT IS ALWAYS TERENDELEV.** This card is **a tribute, not a recap.** It may take its *emotional color* from the current session, but it must be **about her** — her choice to live small among people who never knew what she was, her death as a shield, the scales she left, what her absence costs. It must **not** become a paragraph of this week's plot with her name at the top.

   **This has drifted twice and been corrected twice** (Sessions 16 and 17). The failure mode is always the same: the session hands you a strong motif (stolen faces; a demon praying to be made clean), and the card turns into a summary of that motif with Terendelev as a framing device. **If you can delete her name from the quote and it still reads as a coherent recap of the session, you have written the wrong thing.** Rewrite it.

   Test before shipping: *is more than one sentence of this about someone other than Terendelev?* If yes, cut back until it isn't. One closing clause tying to the present moment is plenty.
3. **Four Party Contribution cards** — one per PC (Caleth, Nageru, Thane, Korroc). Each has a role label (e.g. *"Arcane Vanguard"*), name, class line, and a short paragraph (3-4 sentences) describing **what defines that character at this current moment**. NOT a full history; just the most recent / most defining beats.
4. **Current Status milestone box** — one gold-bordered box with a status title (e.g. *"The Underground Cleared"* or *"The Library After the Fight"*), a short subtitle line, one summary paragraph, and the Book / Mythic Tier / Level footer.

## Update cadence

**Per session.** Each session writes a new chapter; the same update should refresh this section. Sessions accumulate in the chronicle (the auto-loading "From the War Chronicle" section below pulls the latest entry from the API). This section, by contrast, shows ONE current state.

## Update process

When a session ends and a new chapter is written:

1. Read the latest chapter file in `chapters/`
2. Read the latest session notes in `sessions/`
3. Update **all four** PC contribution cards to reflect the new session's defining beats for each character (replace the text; don't append)
4. Update the **narrative paragraph** to summarize the current arc state (may carry brief context from prior sessions; do not enumerate every event)
5. Update the **status box** to reflect where the party is right now
6. Update the **session header** (the small top label) — bump the session number
7. Possibly update the **big gold title** — match the most recent chapter title, or use a narrative title that captures the current arc moment
8. The **Terendelev card** can usually stay, but check whether its quote still feels current; refresh if needed
9. **CHECK THE VANGUARD SECTION'S LEVEL/MYTHIC TIER LINE.** Earlier in the same page (under `{/* THE VANGUARD (CHARACTERS) */}`, around line 125) there is a span reading something like *"Level 3 Gestalt • Mythic Tier 0"*. This number must **stay in sync** with the Book/Tier/Level footer in the Campaign Arc Status milestone box. If a session levels the party up or grants a new Mythic Tier, **both places must update together.** There is an inline code comment at the Vanguard line warning about this; honor it.
10. **Write a per-session update note to `website/updateN.md`** (where N matches the session number). After landing the page edits, create a markdown file in `wrath-story-book/website/` that serves as the user's personal changelog of live-site changes. **Always write one when the section is updated.** Filename is `updateN.md` matching the session number; if a session has multiple edits over time, append to the existing file rather than creating new ones.

   **Format pattern** (set by `website/update4.md` — use this as the template):
   - **Top matter**: H1 title with session number + theme, date, what drove the update, live page route
   - **What changed**: grouped by file path + section, each location getting a bulleted list of specific edits. Note that *unchanged-but-considered* elements (e.g. "Terendelev card unchanged") are worth calling out so the user knows you actually evaluated them.
   - **Files NOT touched**: a short section listing the relevant adjacent sections that were intentionally left alone, with why (e.g. "auto-loading section pulls from API")
   - **Verification**: concrete steps the user can take to visually confirm the changes on the live or local site
   - **Cross-references**: paths to the design-pattern memory, the chapter that drove the update, and the session notes

   The format should be **useful as a real changelog** — file paths so the user can navigate, verification steps so they can spot-check, what-NOT-touched notes so they don't wonder if something was missed. Avoid Claude-jargon ("post-edit recap"); write it as if for a developer reading their own changelog months later.

## Technical gotchas in `page.tsx`

**⚠ Inline `<span>` word-jam — this recurs every time and has burned three sessions.**

In the wrapped prose paragraphs (narrative paragraph, Terendelev quote, status-box summary), a highlighted span written with a plain space around it will render **glued to the adjacent word** — *"the Sword of Valorhanging"*, *"himself.He wrote"*. JSX strips whitespace adjacent to a tag when a line break is involved, and these paragraphs are hard-wrapped, so a literal space next to `</span>` is not reliable.

**Always use explicit `{" "}` on both sides, with the span on its own line:**

```jsx
company found{" "}
<span className="text-zinc-300">the Sword of Valor</span>{" "}
hanging in an iron frame — and it was a joke.
```

Do this for **every** inline span you add to a wrapped paragraph, even when the source looks like it has a space. Grep `</span> [a-zA-Z]` after editing to catch strays. *(The hero title around line 99 is an exception — it is a single unwrapped line and renders fine.)*

**Other page.tsx notes:**
- Apostrophes in **JSX text** must be escaped as `&apos;`; apostrophes inside the **card-array JS strings** are ordinary string content and need no escaping (typographic `’` is used there).
- `npx tsc --noEmit` is worth running after a pass. Two errors in `src/lib/tracker/merge.test.ts` are **pre-existing and unrelated** — ignore them; anything in `src/app/wrath/page.tsx` is yours.
- **Commit on `main`.** Work committed to a side branch never reaches Vercel (Session 12's lesson).

## Voice and theme

The page uses Cinzel headers, Spectral italics, and a tight palette: `wotr-gold` (warm gold), `wardstone-blue` (cool blue), `abyssal-red` (deep red), `parchment` (off-white), `zinc-*` neutrals. Tone is medieval crusader military with mystical/sacred overtones — "Intelligence Report", "Commander's Note", "From the War Chronicle". Card text is sparse, weighted, sentence-fragmenty when appropriate. PC contribution paragraphs should sound like brief war-chronicle entries, not bullet lists.

## What NOT to do

- Do NOT add more cards over time (no fifth PC card; no "previous sessions" archive within this section)
- Do NOT make the contribution paragraphs longer with each update
- Do NOT label session beats by chapter number in the prose (a casual reader doesn't know what Chapter 4 is)
- Do NOT reveal explicit secrets that belong to specific characters' private threads (e.g. Caleth's Riftwarden origin, Thane's Eagle Watch contract specifics, Aravashnial's identity). It's fine to ALLUDE — *"Caleth carries a secret about an old wizard he's only beginning to understand"* — but the page is reader-facing and the secret should land in chapter prose, not in a summary card

## Cross-references

- Chapter files: `G:\Projects\wrath-story-book\chapters\`
- Session notes: `G:\Projects\wrath-story-book\sessions\`
- Character files (for voice/role consistency): `G:\Projects\wrath-story-book\characters\`
- The page itself (whole file): `G:\Projects\games\src\app\wrath\page.tsx`
- The auto-loading chronicle below this section is `{/* FROM THE WAR CHRONICLE */}` — that pulls from `/api/stories?campaign=wrath&limit=1` and shows the most recent dispatch. This is the running record; the Session section above it is the snapshot.
