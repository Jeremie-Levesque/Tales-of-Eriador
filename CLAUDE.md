# Tales of Eriador: Session Recap Instructions

[Home](README.md)

These instructions apply every time a session transcript is summarized. Follow them in order. Do not skip steps, even for a short session.

## Source of truth: the campaign folder

**All campaign files live in the user's local folder, and that folder is the source of truth:**

```
C:\Users\jermi\Documents\DND\Tales of Eriador\
├── README.md                          ← GitHub landing page; links to every recap and file
├── CLAUDE.md                          ← these instructions
├── .gitignore                         ← excludes *.mp3 (audio is never pushed)
├── Reference\
│   └── Glossary.md                    ← spelling authority for all names and terms
├── Summaries\
│   ├── Previously_On\
│   │   └── Session_NN_Previously_On.md
│   ├── Scene_Recaps\
│   │   └── Session_NN_Scene_Recap.md
│   ├── Character_Spotlights\
│   │   └── Session_NN_Character_Spotlights.md
│   └── Campaign_Ledger\
│       └── Session_NN_Campaign_Ledger.md
└── Recordings\
    └── Session NN\
        ├── Session_NN_YYYY-MM-DD.mp3  ← audio (not needed for summarizing; git-ignored)
        ├── Session_NN_Readable.md     ← the transcript to read (primary)
        └── Session_NN.json            ← segment-level transcript (for checking)
```

- Always read from and write to this folder. The claude.ai project only holds a pointer to it.
- **The folder is a git repository** pushed to GitHub (`https://github.com/Jeremie-Levesque/Tales-of-Eriador`) so the recaps can be shared with the DM, who reads them on GitHub. So:
  - `README.md` is the landing page. Keep it up to date (Step 7) so every recap and reference file is one click away.
  - All links between files must be **relative** (for example `Summaries/Scene_Recaps/Session_02_Scene_Recap.md`), use forward slashes, and write spaces as `%20` (for example `Recordings/Session%2002/Session_02_Readable.md`), so they work on GitHub.
  - Do not commit, push, or change git settings unless the user asks. When you finish, list the files you added or changed so the user can commit and push them.
  - Never add audio files to the repository.
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
| Dominic | **Thalion** | Elf | Fighter |
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

The group is bilingual in **English and Canadian French** and switches between the two throughout a session, sometimes mid-sentence. The transcription tries to detect which language is being spoken, so the transcript contains both.

- **Read and understand both languages fully.** French passages carry just as much of the story as English ones, including actions, rolls, decisions, NPC dialogue and jokes. Never skip or skim a line because it's in French.
- **Expect informal spoken Canadian French:** casual and spoken forms (for example *tsé*, *pis*, *ben*, *chu*, *là*), anglicisms, and swearing. Interpret what was meant, not the literal words.
- **Expect language-detection errors.** The `[EN]`/`[FR]` tag can be wrong, and the transcriber sometimes renders French as garbled English or English as garbled French. When a line reads as nonsense, try reading it as the other language spoken aloud, and use context.
- **Names are almost always spoken in English**, even inside French sentences. So:
  - A name that looks French-ified or phonetically mangled is probably a transcription error for the English name. Check the glossary.
  - Default to the English/Tolkien spelling when resolving names. Still ask the user about anything you're not sure of (Step 5).
  - Record these French-mode mangles as "heard as" variants in the glossary.
- **Language switches can also confuse diarization,** since the speaker segmentation may break or relabel at a switch. Be extra careful with attribution around them (Step 4).
- **The recaps are written in English only** (Step 6). Translate everything said in French into natural English. Don't include French text in the recaps, even in quotes.

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
2. **Every previous session's recap files, all of them, from Session 01 onward**, not just the last few. Read all four formats for every past session, in order. This gives you:
   - **the full story context:** who every NPC is, what they've said and done, how relationships between the characters have developed, which promises and threads are still open, and callbacks to early sessions that may matter again;
   - **the established style:** so the new recaps match the structure, length, tone and formatting the group is used to.

   Pay special attention to the **most recent Campaign Ledger**: its open threads, NPCs and quest statuses are carried forward into the new ledger. If an older session raised a thread that later ledgers dropped by mistake, restore it.

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
2. **Attribute actions to characters, not players.** In the recaps, "Jeremie says he draws his axe" becomes "**Hanarr** drew his axe." Use player names only for out-of-character moments.
3. **Resolve every "you"** (or *tu*/*vous*). When the DM says "you see..." or "you take 6 damage", work out which character is meant from context (who just acted, who was addressed, who rolled). If it can't be determined, ask the user. Do not guess.
4. **Use race and class as clues.** The DM or other players may call characters "the dwarf", "the elf", "the hobbit"/"the halfling" or "the human" (or *le nain*, *l'elfe*, *le hobbit*, *le humain*), or refer to class abilities (rage for the barbarian, spells and healing for the cleric, sneak attack for the rogue, Second Wind or Action Surge for the fighter). Use these to confirm who acted. Don't assume, though: an NPC can be a dwarf too, and some abilities overlap between classes.
5. **Do a separate attribution pass.** Before writing, go through your notes line by line and check who did each thing: who spoke each notable line, who rolled, who found each clue, who carries each item. Flag any line where the speaker label and the context disagree, and include those in your questions to the user if the context doesn't settle them. The JSON's segment-level speakers can help here.

### Step 5. Ask about spelling before writing

Before writing any part of the recaps, collect **every word you are unsure of** (names, places, items, Elvish or Dwarvish words, anything not in the glossary) and ask the user about all of them in **one batched question**. For each word give:

- the word as the transcript has it,
- the timestamp,
- one line of context (who said it, about what),
- your best guess at the spelling, including the canonical Tolkien spelling if it looks like a canon name.

Names are nearly always spoken in English, so base your best guess on the English/Tolkien form even if the transcript rendered the word in French. Canon names follow Tolkien's spelling, with diacritics (for example Dúnedain, Amon Sûl, Annúminas). Don't assume a canon name is meant if the DM might have invented one. Ask.

Once the attendance, speaker map, any uncertain attributions, and spelling answers are all in, write the recaps.

### Step 6. Write the four recaps

**The recaps are in English only.** Translate French dialogue and narration into natural, idiomatic English that keeps the meaning and tone (including humour). Quotes are translated too. Don't leave French words or phrases in the recaps.

**Timestamps are required.** Every bullet point and every section or paragraph starts with the transcript timestamp where that moment happens, in the transcript's `[HH:MM:SS]` format:

- A single moment: `[01:23:45]`
- A span: `[01:23:45–01:41:10]`
- Section headers carry the span they cover.

**Formats:** every session gets **four separate recap files**, chosen by the DM after Session 1:

1. **Previously On**: a 150–250 word recap to read aloud at the start of the next session.
2. **Scene-by-Scene Recap**: one section per scene, a short paragraph plus NPC/place/clue/roll/loot bullets.
3. **Character Spotlights**: one section per character (Hanarr, Thalion, Nihla, Osric).
4. **Campaign Ledger**: quests and leads, NPCs, places, loot, notable rolls, decisions, and all open threads.

Match the structure, length, tone and formatting of all the previous sessions' recap files you read in Step 2 (the Session 01 files are the original examples), and follow the layout below. When the user asks for a style change, update this section so the change sticks.

**Layout of every recap file:**

1. Title: `# Session NN: <Format name>`.
2. Navigation line: `[Home](../../README.md) · Session NN: ` followed by the four formats in this order: Previously On · Scene-by-Scene Recap · Character Spotlights · Campaign Ledger. The current format is in bold; the other three link to that session's other files.
3. A table with the real date, the in-world date, and attendance (player and character, and how any absent character was handled).
4. An italic line linking the transcript: `*Timestamps such as [01:23:45] point to the [session transcript](../../Recordings/Session%20NN/Session_NN_Readable.md).*`
5. `---`, the body, `---`, then the navigation line again.

**What goes in each format:**

- **Previously On:** 150–250 words to read aloud at the start of the next session. Opens with "Previously, on Tales of Eriador…", short paragraphs with a timestamp at the start of each beat, character names in bold on first mention, and a one-line hook for where the next session begins.
- **Scene-by-Scene Recap:** one `### Scene N: <Title> [start–end]` section per scene, in order. Each has a 3–6 sentence paragraph, then timestamped bullets as relevant: **NPCs**, **Places**, **Clues**, **Rolls** (notable ones only), **Loot**/**Items**.
- **Character Spotlights:** one `### <Character> (<Race> <Class>, <Player>)` section each, in this order: Hanarr, Thalion, Nihla, Osric. Timestamped bullets on what the character did, said, decided and noticed, notable rolls, and relationships, ending with a **Gained:** line (items, money, conditions, Shadow points). If a character was absent or played by the DM, say so at the top of their section.
- **Campaign Ledger:** these sections in order: **Quests and leads** (table: Lead | Source | Status, with statuses such as New, Accepted, Advanced, Resolved, Deferred), **NPCs met** (table: NPC | Who | First seen), **Places** (table: Place | Notes), **Loot, rewards and conditions**, **Notable rolls**, **Decisions**, and **Open threads and questions**. Every row and bullet has a timestamp.

**Content rules:**

- Stay faithful to what happened at the table. Do not import canon events or lore the DM did not bring up, and do not invent details to fill gaps.
- Use past tense for story events, unless the chosen style says otherwise.
- Bold character names on first mention in each section.
- Name NPCs exactly as spelled in the glossary.
- **Open threads live in the Campaign Ledger.** Carry forward every still-open thread from the previous ledger, add new ones, and mark any that were resolved or advanced this session.
- The four files must agree with each other: same spellings, same facts, same attributions.

### Step 7. Save the recaps and update the README

- Save the four files (zero-padded session number, for example `03`):
  - `Summaries\Previously_On\Session_NN_Previously_On.md`
  - `Summaries\Scene_Recaps\Session_NN_Scene_Recap.md`
  - `Summaries\Character_Spotlights\Session_NN_Character_Spotlights.md`
  - `Summaries\Campaign_Ledger\Session_NN_Campaign_Ledger.md`
- Each file starts with the title, navigation line, metadata table (real date, in-world date, attendance and how absent characters were handled) and transcript link described in Step 6.
- **Update `README.md`:** add a row to the "Session recaps" table linking all four recaps and the transcript for the new session. Update the party table if a character's details changed (for example, a new title, home or subclass), and add links to any new reference files.
- Check every link you wrote points to a file that exists, with spaces written as `%20`.

### Step 8. Update the glossary

After every session, update `Reference\Glossary.md`:

- **Add every new term** from the session: NPCs, places, factions, items, creatures, in-world words. Include the confirmed spelling, type, first appearance (`Session N [timestamp]`), a short description, and **"heard as"** variants (how the transcript mangled it, including French-mode renderings), so future transcripts are easier to correct.
- **Update existing entries** with new facts, such as an NPC's changed status, a place's new meaning, or an item that changed hands.
- **Fill in character details** that come up in play, such as subclasses, homelands or notable gear, in the Players and characters table.
- Correct any glossary spelling the user fixed.

### Step 9. Final check before handing over

- [ ] Attendance was asked before the transcript was read.
- [ ] Every previous session's recap files were read, all four formats, from Session 01 onward.
- [ ] The whole transcript was read, every line, English and French.
- [ ] The speaker map is confirmed, speaker labels were checked against context rather than trusted blindly, and every action is attributed to the right character.
- [ ] Every unknown spelling was asked about and resolved.
- [ ] The recaps are entirely in English, with no untranslated French.
- [ ] Every bullet and section has a timestamp.
- [ ] All four recap files exist, follow the layout in Step 6, and agree with each other.
- [ ] The Campaign Ledger carries forward every still-open thread from the previous session.
- [ ] The four recaps, the README and the glossary are all saved in the campaign folder, and every link works.
- [ ] You've told the user which files were added or changed, so they can commit and push them to GitHub.
