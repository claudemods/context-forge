---
name: forge
description: Main entry point for Context Forge. Routes a request to the right built-in capability - coding guidelines, designing or restructuring an ICM workspace, running a ready-made ICM pipeline (script-to-animation, voice-driven-animation, course-deck-production, workspace-builder), or the Elephant-Goldfish idea/design/review workflow. Use when the user says "forge", asks what this toolkit can do, or describes a task that could fit more than one of them.
license: MIT
---

# Context Forge

One toolkit, four sources. Pick the row that matches the request, read that skill's `SKILL.md`, and follow it. If it is ambiguous, ask one question.

| The user wants to... | Capability | Skill |
|---|---|---|
| Code carefully: state assumptions, keep it simple, make surgical diffs, verify | Karpathy guidelines | `karpathy-guidelines` |
| Turn a process, idea, repo or vault into an ICM workspace; audit or restructure a folder; build a context map, knowledge bundle or system map | ICM Architect | `icm-architect` |
| Run or extend a ready-made ICM pipeline (animation, course decks, a new workspace) | ICM workspaces | `icm-workspaces` |
| Explore an idea with fresh-eyes reviewers | EGM | `egm-brainstorm` |
| Draft a design document from a brief | EGM | `egm-draft` |
| Review a design doc or plan with independent reviewers | EGM | `egm-review`, `egm-review-loop` |
| Apply review findings | EGM | `egm-resolve` |
| Document an existing codebase (READMEs per package) | EGM | `egm-bootstrap` |
| Check whether code still matches its design | EGM | `egm-drift-report` |

## Rules

- `karpathy-guidelines` is a baseline: apply it alongside any other capability whenever code is written or changed.
- EGM skills have `disable-model-invocation: true`, so the `Skill` tool refuses them. Read the target `SKILL.md` and follow it in the same thread. They need a harness that can spawn fresh subagents; see `docs/egm/claude.md` under the plugin root (`${CLAUDE_PLUGIN_ROOT}`).
- Typical chain for a feature: `icm-architect` (if a workspace is wanted) -> `egm-brainstorm` -> `egm-draft` -> `egm-review` -> `egm-resolve` -> implement under `karpathy-guidelines` -> `egm-drift-report`.
- Say which capability you chose and why, in one line, before starting it.
