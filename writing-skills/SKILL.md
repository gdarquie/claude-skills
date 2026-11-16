---
name: writing-skills
description: Rules to write/edit personal Claude Code skills (SKILL.md). Use before creating/changing any skill.
---

# Writing skills

Goal: min tokens, zero ambiguity for Claude. Concision > grammar/spelling.

- EN only, even if user speaks FR.
- Telegraphic style OK: drop articles/verbs, use abbrevs (e.g. cfg, deps, repo, msg, w/, w/o, →), symbols, fragments. Only if meaning stays unambiguous.
- Bullets > prose. No filler, no repetition, no explaining what Claude already knows.
- 1 example > rules paragraph. Examples of expected output stay in full correct prose.
- `description`: 1 line, what + when.

## Location

- Create in `~/dev/gdarquie/claude-skills/<name>/SKILL.md`, never in project repo.
- Link: `ln -s ~/dev/gdarquie/claude-skills/<name> ~/.claude/skills/<name>`
- Add to skill list in `~/.claude/CLAUDE.md`.
