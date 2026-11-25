# Tibetan Buddhist Obsidian — Claude Skills starter pack

Assumptions:
- One Markdown file per root text.
- A separate Markdown file for each commentary.
- Tibetan source text must be preserved exactly.
- The user manually identifies which commentary location corresponds to which existing root-text block ID.
- Claude proposes edits first and edits only after explicit approval.

## Install
Copy the `.claude` folder into the root of your Obsidian vault (or the project directory Claude Code uses for that vault).

Expected layout:

```text
YourVault/
├── .claude/
│   └── skills/
│       ├── root-commentary-linker/SKILL.md
│       ├── block-id-auditor/SKILL.md
│       ├── transclusion-validator/SKILL.md
│       └── toc-context-reader/SKILL.md
├── Root-Texts/
├── Commentaries/
└── TOC/
```

Change folder names to match your actual vault. The skills do not require these exact folders.

## Suggested workflow
1. Back up the vault or create a Git branch.
2. Use `toc-context-reader` on the TOC and named notes.
3. Manually prepare the mapping table below.
4. Use `block-id-auditor` on the named root-text note.
5. Use `root-commentary-linker` to prepare a proposal.
6. Review and approve the proposal.
7. Ask Claude to apply only approved insertions.
8. Use `transclusion-validator` on the changed files.
9. Review the diff and test the embeds in Obsidian.

## Mapping template

| Commentary file | Exact insertion anchor | Root-text file | Existing block ID |
|---|---|---|---|
| `Commentaries/Commentary A.md` | Below `### Explanation 1` | `Root-Texts/Root Text.md` | `root-ch01-p001` |

## Example embed
```markdown
![[Root Text#^root-ch01-p001]]
```

Use the exact note name/path convention already used in your vault.

## Critical safeguards
- Never let Claude guess passage alignment.
- Never let Claude silently create or change block IDs during linking.
- Never allow the linking skill to edit root-text files.
- Keep the Tibetan wording and source edition intact.
- Use proposal → approval → edit → diff → validation.
