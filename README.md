# ScriptFlip Companion – User Guide

This guide covers the main user-facing features available in ScriptFlip Companion. Each section maps to the primary tabs in the app plus the Settings menu so you can reference how to work with scripts, passes, QC, and exports.

## Script Tab
- Import and open: use `Import File` or the recent files dropdown to load a VoiceQ snapshot. The header shows the active filename plus quick stats (total duration, total words, QC issue count, and current (and selectable) primary language).
- Editing the script table: each row shows the start and end timecodes, duration (in timecode), character, primary language script, and secondary language (non-English) script. 

Scene headers include a scene title field and an inline pass selector; click the arrow icon to collapse/expand a scene.
- Scene management: right-click a dialogue line to create a new scene starting there. Right-click a scene header to merge with the previous or next scene.
- Pass assignment: select a pass from the header button; rows inherit the chosen pass color so you can see coverage at a glance.
- Search: press ⌘F to focus search, choose `Contains` or `Exact`, and filter by field (character, script, secondary, scene title). Use the up/down arrows to move between matches.
- Export and undo: `Export JSON` saves the current script; `Export Plan` saves an `.sfplan` with your latest edits; `Undo` backs up recent actions.

## Passes Tab
- View per-pass rollups: see total duration, words, WPM (words per minute), density, and the most word-heavy character for each pass.
- Track progress: check `Done` when a pass is complete and set the pass date inline to keep a lightweight schedule log.

## Characters Tab
- Character totals: per character you can see scene count, dialogue duration (timecode and mm:ss), line count, word count, WPM relative to the whole script and to their own dialogue, plus a density label for heuristic insight on dialogue density.

## QC Tab
- Automated checks: the QC table automatically detects and highlights punctuation, typo, spelling, grammar, capitalization, conjugation, repetition, reaction tags, and cue alignment issues. Rows show start and end timecodes, character, the dialogue containing the error, and issue details. Each issue is highlighted at a word-level.
- Fixing text: click a script cell to edit in-line. Issues re-evaluate automatically and resolved items are removed from the QC list when toggled with the `Resolved` checkbox.
- Export and maintenance: use `Export QC List` to generate a spreadsheet of open issues, `Wipe Markers` to globally clear VoiceQ markers, and `Refresh QC` to rerun checks across the script.
- Dictionary shortcuts: select or right-click a word/phrase in the QC table to add it to your Dictionary (as a word, proper noun, or phrase). Dictionary additions immediately suppress false positives and trigger a re-QC.

## MIDI Flipper Tab
- The core function is to batch-generate MIDI files for each character, with MIDI notes for each of their lines, at the proper start and end timecodes and with the proper durations.
- Character selection: every character with dialogue appears with a checkbox and a master `Select All` toggle.
- Timing options: pick the FPS that matches your session (23.976, 24, 25, or 30).
- Export: `Export MIDI Files` creates a ZIP containing one MIDI file per selected character, with a note for every line timed to the script.

## Settings Menu
- General: choose whether ⌘S saves as `.sfplan` or `.json` by default.
- Passes: set the color used for each pass via the fixed palette; colors flow through the Script and Passes tabs.
- QC:
  - Ignored characters: add/remove names to skip QC checks, with `Exact` (JOHN) or `Contains` ([SPEAKING ITALIAN]) matching.
  - Global ignores: toggle `Ignore Walla`, `Ignore FN`, and `Ignore Singing` to mute common non-dialogue cues.
  - Dictionary: review and remove entries you have added. Changes trigger an immediate QC refresh.
