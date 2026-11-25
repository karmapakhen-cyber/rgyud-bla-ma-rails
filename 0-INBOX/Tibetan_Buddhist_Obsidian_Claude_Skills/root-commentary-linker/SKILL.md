---
name: root-commentary-linker
description: Insert Obsidian block transclusions into Tibetan commentary notes using an explicit human-supplied passage mapping. Never infer passage matches.
---

# Root–Commentary Linker

## Purpose
Link a commentary note to the authoritative Tibetan root-text note using block transclusions. The user supplies the exact mapping between commentary locations and root-text block IDs.

## Vault model
- One Markdown file per root text.
- Each commentary is a separate Markdown file.
- The root-text file is authoritative.
- Commentary text must remain unchanged except for approved transclusion insertions.
- The user's mapping is the sole authority for passage correspondence.

## Non-negotiable rules
1. Never translate, transliterate, normalise, correct, punctuate, or rewrite Tibetan text.
2. Never decide which root passage a commentary explains.
3. Never infer matches from similar wording, chapter order, doctrine, or proximity.
4. If the mapping is incomplete or ambiguous, stop and ask. Do not guess.
5. Use only existing block IDs. Do not create, rename, or change IDs.
6. Do not delete, reorder, or rewrite commentary text, headings, footnotes, citations, or existing embeds.
7. Do not edit the root-text file.
8. Work only on files explicitly named by the user.
9. Work on a backup or Git branch. If neither exists, request a backup before editing.

## Required mapping
Every requested insertion must specify:
- Exact commentary file path.
- Exact insertion anchor (for example, immediately below a named heading).
- Exact root-text file path.
- Exact existing root-text block ID.

Example:

| Commentary file | Exact insertion anchor | Root-text file | Existing block ID |
|---|---|---|---|
| Commentaries/Commentary A.md | Below `### Explanation 1` | Root-Texts/Root Text.md | `root-ch01-p001` |

## Workflow

### Phase 1 — Read-only inspection
1. Read only the named files.
2. Confirm each requested block ID exists exactly once in the named root-text file.
3. Confirm each commentary insertion anchor exists and is unambiguous.
4. Check whether the identical transclusion already exists at that location.
5. Report missing IDs, duplicate IDs, missing anchors, and existing embeds.
6. Do not edit.

### Phase 2 — Proposal
Show a proposal listing the commentary file, insertion anchor, exact transclusion, validation result, and warnings. Use:
`![[Root Text#^root-ch01-p001]]`
Use the exact note path/name convention already used in the vault. Do not invent paths.
Ask for approval before writing.

### Phase 3 — Apply approved edits
1. Insert only approved transclusion lines at approved anchors.
2. Preserve surrounding text and formatting.
3. Do not modify root-text files.
4. Make no unrelated changes.
5. Show a diff for every modified file.

### Phase 4 — Verify
Check that every inserted ID exists exactly once, every embed uses the approved target, no surrounding content was removed or rewritten, and every requested mapping was completed or reported as blocked.

## Output report
List files inspected, proposed changes, approved changes applied, validation results, and items requiring human decision.

## Stop conditions
Stop without editing if an ID is absent or duplicated, an anchor is missing or ambiguous, a conflicting embed exists, or the file/edition appears incorrect.
