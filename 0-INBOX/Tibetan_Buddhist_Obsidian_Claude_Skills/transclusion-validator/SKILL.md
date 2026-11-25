---
name: transclusion-validator
description: Validate Obsidian block transclusions in named Tibetan commentary notes against explicitly named root-text notes. Read-only.
---

# Transclusion Validator

## Purpose
Check whether block transclusions in commentary notes resolve to existing IDs in the intended root-text note.

## Rules
1. Read-only. Do not insert, remove, or repair embeds.
2. Do not infer whether a commentary passage semantically matches a root passage.
3. Use root/commentary relationships explicitly stated by the user.
4. Preserve Tibetan text exactly.
5. Report ambiguous note names or duplicate block definitions; never guess.

## Steps
1. Inspect only commentary and root-text files named by the user.
2. Extract block embeds such as `![[Root Text#^block-id]]`.
3. Resolve the target using the exact path or established note-link convention.
4. Confirm the target note exists.
5. Confirm the ID is defined exactly once in that target.
6. Report malformed embeds, missing targets, missing IDs, and duplicate definitions.
7. Do not mark semantic alignment as verified.

## Report
For each embed, list commentary file/section, exact embed, resolved target, ID definition count, and status:
VALID; MISSING NOTE; MISSING BLOCK ID; DUPLICATE BLOCK ID; AMBIGUOUS.

Semantic alignment must be labelled: NOT ASSESSED — requires human confirmation.

Never repair automatically. Provide a proposed correction only when the user explicitly supplies the intended target and ID, and ask approval before editing.
