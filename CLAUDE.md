# Tales of Eriador: Session Summary Instructions

These instructions apply every time a session transcript is summarized. Follow them in order. Do not skip steps, even for a short session.

## Source of truth: the campaign folder

**All campaign files live in the user's local folder, and that folder is the source of truth:**

```
C:\Users\jermi\Documents\DND\Tales of Eriador\
├── CLAUDE.md                          ← these instructions
├── Reference\
│   ├── Glossary.md                    ← spelling authority for all names and terms
│   └── Style_Guide.md                 ← the summary style the user chose
├── Summaries\
│   ├── Session_Index.md               ← one row per session
│   └── Session_NN_Summary.md          ← the summaries (Session_01_Summary.md, ...)
└── Recordings\
    └── Session NN\
        ├── Session_NN_YYYY-MM-DD.mp3  ← audio (not needed for summarizing)
        ├── Session_NN_Readable.md     ← the transcript to read (primary)
        └── Session_NN.json            ← segment-level transcript (for checking)
```

- Always read from and write to this folder. The claude.ai project only holds a pointer to it.
- If the folder can't be reached (the chat isn't linked to the computer, or the computer is offline), **stop and tell the user**. Don't work from old copies or from memory, and don't save summaries anywhere else.
- Edit existing files in place (read the current version first, then write back the full updated file). Never recreate a file from memory.
- When saving files to the folder by copying them over from the cloud workspace, copy from a **new file name each time** (a file name that was already used can send the old version again). Then read the saved file back from the folder and confirm it matches before telling the user it's done.

## The campaign

- **Setting:** Middle-earth, the Third Age, year **2981** (T.A.), in and around **Eriador**.
- **Game Master:** Andre (the DM).
- **Players and characters:**

| Player | Character | Race | Class |
|---|---|---|---|
| Jeremie | **Hanarr** | Dwarf | Barbarian |
| Dominic | **Thalion** | Elf | Unknown (check the glossary) |
| Alex | **Nihla** | Halfling (Hobbit) | Cleric |
| Benoit | **Osric** | Human | Rogue |
| Andre | DM (voices all NPCs, narrates the world) | | |

`Reference\Glossary.md` has the current character details and wins if this table is out of date.

## The transcripts

Each session's folder under `Recordings\` holds two transcript files:

- **`Session_NN_Readable.md`: the one to read.** A header gives the duration, the language split, and the number of speakers detected. The body is grouped into paragraphs, each formatted like this:

  `**[00:00:30] [FR] SPEAKER_01** C'est commencé...`

  That is the start timestamp, the detected language (`[EN]` or `[FR]`), the diarization speaker label, then the text. Paragraphs break on pauses, speaker changes and language switches.
- **`Session_NN.json`: the segment-level data** (`segments` list, each entry with `start`, `end`, `text`, `language` and `speaker`). Use it to check a doubtful attribution or pin down a precise time inside a long paragraph. Don't read it in place of the Readable file.

The language tags and speaker labels are both machine guesses. See the language section and Step 4.

## Language: a bilingual table

The group is bilingual in **English and Canadian (Québécois) French** and switches between the two throughout a session, sometimes mid-sentence. The transcription tries to detect which language is being spoken, so the transcript contains both.

- **Read and understand both languages fully.** French passages carry just as much of the story as English ones, including actions, rolls, decisions, NPC dialogue and jokes. Never skip or skim a line because it's in French.
- **Expect Québécois speech:** informal and spoken forms (for example *tsé*, *pis*, *ben*, *chu*, *icitte*, *là*), anglicisms, and Québécois swearing. Interpret what was meant, not the literal words.
- **Expect language-detection errors.** The `[EN]`/`[FR]` tag can be wrong, and the transcriber sometimes renders French as garbled English or English as garbled French. When a line reads as nonsense, try reading it as the other language spoken aloud, and use context.
- **Names are almost always spoken in English**, even inside French sentences. So:
  - A name that looks French-ified or phonetically mangled is probably a transcription error for the English name. Check the glossary.
  - Default to the English/Tolkien spelling when resolving names. Still ask the user about anything you're not sure of (Step 5).
  - Record these French-mode mangles as "heard as" variants in the glossary.
- **Language switches can also confuse diarization,** since the speaker segmentation may break or relabel at a switch. Be extra careful with attribution around them (Step 4).
- **The summary is written in English only** (Step 6). Translate everything said in French into natural English. Don't include French text in the summary, even in quotes.

---

## Workflow

### Step 1. Ask who attended. Do this before opening the transcript.

Do not read the transcript until you have asked this. Use a multiple-choice question (multi-select) listing all four players plus the DM, and ask in the same message:

- The **session number** and **real-world date** of the session, if they aren't clear from the file name.
- If anyone was absent: **what happened to their character** (played by the DM, in the background, absent in-story, or played by another player).
- Whether any **guests or extra people** were at the table.

Attendance matters because a diarized transcript only shows speaker labels, and knowing who was there determines who each label can be. Compare the attendance with the number of speakers in the transcript header. A mismatch is normal (the diarizer may split or merge people) but tells you where to be careful.

### Step 2. Load context

Before reading the transcript, read:

1. `Reference\Glossary.md` in full.
2. `Reference\Style_Guide.md`.
3. The **most recent one or two summaries** in `Summaries\`, for continuity: open threads, NPCs already met, where the party is.

### Step 3. Read the entire transcript slowly and take in every part of it

**This is the most important step.** The goal is a complete understanding of the session, not the broad strokes.

- **Read every line of `Session_NN_Readable.md`, from start to finish, in order,** in both English and French. Read in sequential chunks (a few hundred lines at a time) until the whole file is covered. Do not skim, sample, jump ahead, or search for keywords in place of reading. Before moving on, confirm that the number of lines read equals the length of the file.
- **Keep running working notes as you read, in English,** each with its timestamp. Capture:
  - Every scene change and location, including travel and time passing in-world.
  - Every NPC met or mentioned: name, how they were described, what they said and wanted, and their attitude to the party.
  - Every action a character took, and **which character took it**.
  - Every notable roll and its result: skill checks, saves, attacks, critical successes and failures, and what they changed.
  - Combat, blow by blow: who fought what, key hits, who went down, how it ended.
  - Every piece of lore, rumour, clue, prophecy, song, or piece of history the DM gave.
  - Decisions, plans, deals, promises, and disagreements within the party.
  - Loot, rewards, purchases, items lost or given away, and injuries or conditions.
  - Quest hooks and **unresolved threads and open questions**.
  - Memorable lines, whether in character or genuinely funny table moments.
  - Any word whose spelling you are not sure of (see Step 5).
- **Tell in-character speech apart from out-of-character talk.** Rules discussion, snack breaks and off-topic chat do not belong in the story. Note them only if they matter, such as a rules ruling that changed an outcome or a memorable table moment. The start of a recording is often pre-game chatter; find where play actually begins.
- **Remember the DM speaks for many voices.** The DM narrates, voices NPCs, and describes consequences. Work out which NPC is speaking each time.
- The transcript is machine-generated. Expect misheard names, wrong words, wrong language tags and merged speakers. Use context and the glossary to correct them, and never quietly invent a spelling.

### Step 4. Map speakers and attribute every action correctly

**Wrong attribution is the error to avoid most.**

> **Diarization is not perfect.** The speaker labels (`SPEAKER_00`, `SPEAKER_01`, ...) come from automatic diarization and will sometimes be wrong. Common errors:
> - A line is assigned to the wrong speaker, especially when people talk over each other, speak briefly ("yeah", "I'll do it", "ouais"), or have similar voices.
> - Two people are merged into one label, or one person is split across several labels.
> - Labels swap partway through the recording (after a break, for example).
> - The DM voicing an NPC, or a player putting on a character voice, gets a different label.
> - Segmentation breaks or relabels when a speaker switches between English and French.
>
> **Treat a speaker label as a strong hint, not a fact.** Always check it against context: who the DM is addressing, which character name comes up, what was said just before and after, race and class clues, and what makes sense in the scene. When the label and the context disagree, go with the context. When they disagree and the context doesn't settle it, ask the user rather than guess.

Before writing:

1. **Build a speaker map** (for example `SPEAKER_00 → Andre (DM)`, `SPEAKER_01 → Jeremie (Hanarr)`). Use attendance, character names used in speech, the DM addressing players by name, and each speaker's patterns. If any label is uncertain, show the map to the user and ask them to confirm it. Even with a confirmed map, check individual lines against context as you go, since single lines can still be mislabeled.
2. **Attribute actions to characters, not players.** In the summary, "Jeremie says he draws his axe" becomes "**Hanarr** drew his axe." Use player names only for out-of-character moments.
3. **Resolve every "you"** (or *tu*/*vous*). When the DM says "you see..." or "you take 6 damage", work out which character is meant from context (who just acted, who was addressed, who rolled). If it can't be determined, ask the user. Do not guess.
4. **Use race and class as clues.** The DM or other players may call characters "the dwarf", "the elf", "the hobbit"/"the halfling" or "the human" (or *le nain*, *l'elfe*, *le hobbit*, *le humain*), or refer to class abilities (rage for the barbarian, spells and healing for the cleric, sneak attack for the rogue). Use these to confirm who acted. Don't assume, though: an NPC can be a dwarf too, and some abilities overlap between classes.
5. **Do a separate attribution pass.** Before writing, go through your notes line by line and check who did each thing: who spoke each notable line, who rolled, who found each clue, who carries each item. Flag any line where the speaker label and the context disagree, and include those in your questions to the user if the context doesn't settle them. The JSON's segment-level speakers can help here.

### Step 5. Ask about spelling before writing

Before writing any part of the summary, collect **every word you are unsure of** (names, places, items, Elvish or Dwarvish words, anything not in the glossary) and ask the user about all of them in **one batched question**. For each word give:

- the word as the transcript has it,
- the timestamp,
- one line of context (who said it, about what),
- your best guess at the spelling, including the canonical Tolkien spelling if it looks like a canon name.

Names are nearly always spoken in English, so base your best guess on the English/Tolkien form even if the transcript rendered the word in French. Canon names follow Tolkien's spelling, with diacritics (for example Dúnedain, Amon Sûl, Annúminas). Don't assume a canon name is meant if the DM might have invented one. Ask.

Once the attendance, speaker map, any uncertain attributions, and spelling answers are all in, write the summary.

### Step 6. Write the summary

**The summary is in English only.** Translate French dialogue and narration into natural, idiomatic English that keeps the meaning and tone (including humour). Quotes are translated too. Don't leave French words or phrases in the summary.

**Timestamps are required.** Every bullet point and every section or paragraph starts with the transcript timestamp where that moment happens, in the transcript's `[HH:MM:SS]` format:

- A single moment: `[01:23:45]`
- A span: `[01:23:45–01:41:10]`
- Section headers carry the span they cover.

**Style:**

- **Session 1 (first summary ever):** write the summary in **as many styles as possible** so the user can pick what they like. Deliver them together in one document, each clearly labeled. See "First-summary style menu" below. Every style still follows the timestamp and English-only rules. Afterwards, ask the user which style or mix they prefer, and record the answer in `Reference\Style_Guide.md` (structure, sections, length, voice, formatting, and anything they said they did or didn't like).
- **Every later session:** follow `Reference\Style_Guide.md`, and match the structure, length, tone and formatting of the most recent summaries. When the user asks for a style change, update the style guide so the change sticks.

**Content rules:**

- Stay faithful to what happened at the table. Do not import canon events or lore the DM did not bring up, and do not invent details to fill gaps.
- Use past tense for story events, unless the chosen style says otherwise.
- Bold character names on first mention in each section.
- Name NPCs exactly as spelled in the glossary.
- End with **open threads** (unresolved questions, active quests, promises made) unless the chosen style omits them.

### Step 7. Save the summary

- Save to `Summaries\Session_NN_Summary.md` (zero-padded, for example `Session_03_Summary.md`).
- Start the file with: session number, real-world date, attendance (and how absent characters were handled), and in-world date or season if known.
- Add a row to `Summaries\Session_Index.md`.

### Step 8. Update the glossary

After every summary, update `Reference\Glossary.md`:

- **Add every new term** from the session: NPCs, places, factions, items, creatures, in-world words. Include the confirmed spelling, type, first appearance (`Session N [timestamp]`), a short description, and **"heard as"** variants (how the transcript mangled it, including French-mode renderings), so future transcripts are easier to correct.
- **Update existing entries** with new facts, such as an NPC's changed status, a place's new meaning, or an item that changed hands.
- **Fill in character details** that come up in play, such as Thalion's class, subclasses, homelands or notable gear, in the Players and characters table.
- Correct any glossary spelling the user fixed.

### Step 9. Final check before handing over

- [ ] Attendance was asked before the transcript was read.
- [ ] The whole transcript was read, every line, English and French.
- [ ] The speaker map is confirmed, speaker labels were checked against context rather than trusted blindly, and every action is attributed to the right character.
- [ ] Every unknown spelling was asked about and resolved.
- [ ] The summary is entirely in English, with no untranslated French.
- [ ] Every bullet and section has a timestamp.
- [ ] The style matches the style guide (or, for Session 1, the full multi-style set is there).
- [ ] The summary, session index and glossary are all saved in the campaign folder.

---

## First-summary style menu (Session 1 only)

Write all of these, each under its own heading, and each with timestamps:

1. **Chronological log.** Timestamped bullets in order, grouped under scene headers. Dense and factual.
2. **Scene-by-scene recap.** One headed section per scene: a short paragraph of what happened, then key bullets (NPCs, clues, loot).
3. **Chronicle of the West (in-world prose).** The session retold as narrative in a restrained, Tolkien-flavoured chronicler's voice, like an entry in a hobbit's Red Book. Each paragraph starts with its timestamp.
4. **"Previously on..." recap.** 150–250 words, written to be read aloud at the start of the next session.
5. **Character spotlights.** One section each for Hanarr, Thalion, Nihla and Osric: what they did, said, decided and gained or lost.
6. **Campaign ledger.** Reference tables and lists: quests and threads (new, advanced, resolved), NPCs met, places visited, loot and rewards, clues and lore, decisions made, open questions.
7. **TL;DR.** 3–5 lines.
8. **Quotes and table moments.** Best in-character lines and funniest out-of-character moments, attributed correctly and translated into English.

End the document by asking which style or combination the user wants from now on.
