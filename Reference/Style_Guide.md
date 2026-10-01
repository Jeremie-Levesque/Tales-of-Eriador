# Tales of Eriador: Summary Style Guide

[Home](../README.md)

## Status: style chosen (2026-10-01)

After seeing Session 1 written in eight styles, the DM chose **four recap formats**. Every session gets all four, **each in its own file and folder**:

| # | Format | Folder | File name |
|---|---|---|---|
| 1 | Previously On | `Summaries/Previously_On/` | `Session_NN_Previously_On.md` |
| 2 | Scene-by-Scene Recap | `Summaries/Scene_Recaps/` | `Session_NN_Scene_Recap.md` |
| 3 | Character Spotlights | `Summaries/Character_Spotlights/` | `Session_NN_Character_Spotlights.md` |
| 4 | Campaign Ledger | `Summaries/Campaign_Ledger/` | `Session_NN_Campaign_Ledger.md` |

**Reference examples:** the Session 01 files in those folders. Match their structure, length, tone and formatting.

---

## Common layout (every recap file)

1. Title: `# Session NN: <Format name>`
2. Navigation line: `[Home](../../README.md) · Session NN: ` followed by links to the other three formats for the same session, with the current one in bold instead of linked. Order: Previously On · Scene-by-Scene Recap · Character Spotlights · Campaign Ledger.
3. A metadata table: Real date | In-world date | Attendance (player and character, and how any absent character was handled).
4. An italic line linking the session transcript: `*Timestamps such as [01:23:45] point to the [session transcript](../../Recordings/Session%20NN/Session_NN_Readable.md).*` (spaces in paths must be written as `%20`).
5. `---`, then the body, then `---`, then the navigation line again.

---

## The four formats

### 1. Previously On
- **Purpose:** read aloud at the start of the next session.
- **Length:** 150–250 words.
- **Voice:** narrator's voice, past tense, dramatic but plain. Opens with "Previously, on Tales of Eriador…" and ends with a one-line hook pointing to where the next session begins.
- **Format:** short paragraphs; timestamps placed inline at the start of each beat; character names in bold on first mention.

### 2. Scene-by-Scene Recap
- **Structure:** one `### Scene N: <Title> [start–end]` section per scene, in order.
- **Each scene:** a short paragraph (3–6 sentences) of what happened, then bullets as relevant: **NPCs**, **Places**, **Clues**, **Rolls** (notable ones only), **Loot**/**Items**. Each bullet carries a timestamp.
- **Voice:** factual, past tense, light touch of flavour.

### 3. Character Spotlights
- **Structure:** one `### <Character> (<Race> <Class>, <Player>)` section per character, in this order: Hanarr, Thalion, Nihla, Osric.
- **Content:** timestamped bullets on what that character did, said, decided, noticed and felt; notable rolls; relationships with other characters and NPCs; ends with a **Gained:** line (items, money, conditions, Shadow points), each with a timestamp.
- If a character was absent or played by the DM, say so at the top of their section.

### 4. Campaign Ledger
- **Sections, in order:**
  - **Quests and leads:** table (Lead | Source | Status), with statuses such as New, Accepted, Advanced, Resolved, Deferred.
  - **NPCs met:** table (NPC | Who | First seen).
  - **Places:** table (Place | Notes).
  - **Loot, rewards and conditions:** bullets.
  - **Notable rolls:** bullets (natural 1s and 20s, very high or very low results that mattered).
  - **Decisions:** bullets.
  - **Open threads and questions:** bullets. This is where **all** unresolved threads live; carry forward any thread from earlier ledgers that is still open, and mark ones resolved this session.
- Every row and bullet carries a timestamp.

---

## Non-negotiables (apply to every format)

- **English only.** The table speaks English and Québécois French; translate everything into natural English, quotes included.
- A timestamp on every bullet point and every section, in `[HH:MM:SS]` format.
- Actions attributed to **characters** (Hanarr, Thalion, Nihla, Osric), not players, except for out-of-character moments.
- Spellings follow `Reference/Glossary.md`.
- Links are relative so they work on GitHub; spaces in paths are written as `%20`.

---

## Feedback log

- **2026-10-01:** The DM prefers Styles 2, 4, 5 and 6 from the Session 1 sampler (Scene-by-scene recap, Previously on, Character spotlights, Campaign ledger). Not chosen: Chronological log, Chronicle of the West (in-world prose), TL;DR, Quotes and table moments. Jeremie asked for each format to be a separate file in its own folder, shared through GitHub with a README for navigation.
