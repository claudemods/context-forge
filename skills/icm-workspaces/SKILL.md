---
name: icm-workspaces
description: Run or adapt the ready-made ICM (Interpretable Context Methodology) workspaces bundled with Context Forge - script-to-animation, voice-driven-animation, course-deck-production, and workspace-builder. Use for "make a course deck from this material", "turn this script into an animation", "build a new workspace for X with the workspace-builder", or "run setup/status in a workspace".
license: MIT
---

# ICM Workspaces

Bundled, self-contained pipelines live under `${CLAUDE_PLUGIN_ROOT}/workspaces/`. Shared conventions live in `${CLAUDE_PLUGIN_ROOT}/_core/`.

| You want to... | Go to |
|---|---|
| Content idea -> animated video | `workspaces/script-to-animation/CLAUDE.md` |
| Voice-driven research -> script -> voice -> animation -> render | `workspaces/voice-driven-animation/CLAUDE.md` |
| Unstructured material -> course PowerPoints | `workspaces/course-deck-production/CLAUDE.md` |
| Build a new workspace for any domain | `workspaces/workspace-builder/CLAUDE.md` |
| Read the specification | `_core/CONVENTIONS.md` |
| Placeholder syntax | `_core/placeholder-syntax.md` |
| Templates for a new workspace | `_core/templates/` |

## How to run one

1. Work on a **copy** of the workspace in the user's project (outputs are per-run artifacts and must not be written into the plugin cache): copy `workspaces/<name>/` and, if its files reference `_core/`, the `_core/` folder beside it.
2. Read that workspace's `CLAUDE.md`; it takes over from here. Keywords `setup` (onboarding) and `status` (pipeline completion) work inside any workspace.
3. Each stage reads its own `CONTEXT.md` and writes to `output/`; stop at the human edit surface between stages.

## Relationship to `icm-architect`

`icm-architect` designs a *new* workspace from dialogue or restructures an existing folder, using a newer, more compact set of invariants and scripts. `workspaces/workspace-builder` is the older staged pipeline for the same goal. Prefer `icm-architect` unless the user asks for the workspace-builder.
