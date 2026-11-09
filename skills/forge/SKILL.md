---
name: forge
description: Main entry point for Context Forge. Understands a goal, asks at most two clarifying questions, then picks and chains the right capabilities - Karpathy coding guidelines, ICM workspace design and pipelines, the Elephant-Goldfish idea/design/review workflow, or the social media team (brand, calendar, captions, posts, publishing, review). Use when the user says "forge", asks what this toolkit can do, or describes a task that could fit more than one capability.
license: MIT
---

# Context Forge

One toolkit, five sources, 21 skills. Your job: turn the user's goal into the shortest correct chain of skills, say the plan in one line, then run it.

## Step 1: Classify

Match the request to a row. Ask **at most two** short questions, only if the answer changes which skill runs (for example: "new idea or an existing design doc?"). Never ask what you can read from the folder.

| The user wants to... | Skill |
|---|---|
| Write or change code carefully | `karpathy-guidelines` |
| Turn a process, repo, vault or notes into an ICM workspace; audit or restructure a folder | `icm-architect` |
| Run a bundled pipeline (animation, course decks, workspace-builder) | `icm-workspaces` |
| Explore a half-formed idea | `egm-brainstorm` |
| Draft a design doc from a brief | `egm-draft` |
| Review a design doc or plan | `egm-review` (one pass) or `egm-review-loop` (iterate) |
| Apply review findings | `egm-resolve` |
| Document an existing codebase | `egm-bootstrap` |
| Check code still matches its design | `egm-drift-report` |
| Run social media for a business | `social-media-manager` (it orchestrates the nine specialists) |
| Something else / "what can you do?" | List the table above in plain words and ask what they want |

## Step 2: Use a playbook when the goal spans skills

- **New feature, design first:** `egm-brainstorm` -> `egm-draft` -> `egm-review` -> `egm-resolve` -> implement (`karpathy-guidelines`) -> `egm-drift-report`.
- **Structure a messy project:** `icm-architect` (restructure mode) -> `karpathy-guidelines` for any code touched.
- **Brand new social client:** `social-media-manager` handles `brand-onboarding` -> `content-calendar` -> writers -> `publisher`; month end: `social-performance-review`.
- **Document then review a codebase:** `egm-bootstrap` -> `egm-review` on the generated READMEs.

Pause between chain steps so the user can edit the artifact (every skill here writes plain files).

## Rules

- `karpathy-guidelines` is a baseline: apply it whenever code is written or changed, even if not the chosen skill.
- Skills with `disable-model-invocation: true` (all `egm-*`) are refused by the `Skill` tool. Read the target `SKILL.md` under `${CLAUDE_PLUGIN_ROOT}/skills/<name>/` and follow it in this thread. EGM reviews need subagents; see `${CLAUDE_PLUGIN_ROOT}/docs/egm/claude.md`.
- ICM workspaces run from a copy in the user's project, never from the plugin cache.
- Social skills may need optional MCP tools (image generation, scheduling): see `${CLAUDE_PLUGIN_ROOT}/docs/social/SETUP.md`. If a tool is missing, say so and continue without it.
- Before starting, state the choice in one line: which skill(s), and why.
