# Contributing

- **Add a skill:** create `skills/<name>/SKILL.md` with `name` and `description` frontmatter (description says *when* to use it). Add a row to `skills/forge/SKILL.md` and the README table.
- **Keep upstream material recognisable:** bundled projects (EGM, ICM, icm-architect, Karpathy, social-ai-team) keep their license headers. If you edit an Apache-2.0 (EGM) file, add a "Modified by" note.
- **Paths:** reference bundled files with `${CLAUDE_PLUGIN_ROOT}/...`, and other skills as `/context-forge:<name>`.
- **Check before a PR:** every `SKILL.md` has valid frontmatter, relative links resolve, and `claude --plugin-dir .` lists your skill.
- Updating from upstream: diff the upstream repo against the matching folder here, port changes, keep the `/context-forge:` rename.
