---
name: block-id-auditor
description: Audit existing Obsidian block IDs in Tibetan root-text notes without changing files.
---

# Block ID Auditor

## Purpose
Perform a read-only audit of block IDs in user-named Tibetan root-text Markdown files.

## Rules
1. Read-only. Never edit files.
2. Never create, rename, renumber, or delete IDs.
3. Do not alter Tibetan characters or whitespace.
4. Audit only files explicitly named by the user.
5. Treat IDs as exact strings; do not silently normalise spelling or case.
6. Distinguish confirmed issues from possible issues.

## Steps
1. Read the named root-text files.
2. Find block ID definitions, normally written at the end of a paragraph as `^block-id`.
3. Record file, heading context, line number if available, and exact ID.
4. Detect repeated definitions in the audited scope.
5. If commentary files are included in scope, find embeds such as `![[Root Text#^block-id]]`.
6. Compare references with definitions in the named root-text file.
7. Report unused IDs as informational, not automatically erroneous.

## Report
| Status | File | Heading/context | Block ID | Finding |
|---|---|---|---|---|

Statuses: OK; DUPLICATE DEFINITION; MISSING DEFINITION; POSSIBLE MALFORMED ID; UNUSED DEFINITION (informational).

If an ID cannot confidently be distinguished from ordinary text, mark it for manual review. Never repair automatically.
