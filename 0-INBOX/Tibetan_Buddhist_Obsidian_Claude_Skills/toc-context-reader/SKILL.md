---
name: toc-context-reader
description: Read the user's TOC and produce a navigation map for named Tibetan root-text and commentary notes without editing or matching passages.
---

# TOC Context Reader

## Purpose
Read the existing TOC and report the hierarchy needed to navigate the root-text note and separate commentary notes.

## Rules
1. Read-only. Never rewrite or reorganise the TOC.
2. Preserve Tibetan titles exactly as written.
3. Do not invent titles, section boundaries, numbering, or relationships.
4. TOC proximity is not proof of passage correspondence.
5. Mark unclear or missing structure for human review.

## Workflow
1. Read only the TOC and notes named by the user.
2. Extract work title, volume, root-text sections, commentary titles, chapters, and nested sections as written.
3. Build a navigation outline with source file references.
4. Identify missing files or unresolved entries.
5. Return the outline for user confirmation before any linking task.

## Output
List work/edition only if stated, root-text hierarchy, each commentary hierarchy, corresponding note paths, missing or ambiguous entries, and this reminder: TOC structure is navigation context, not proof of passage alignment.
