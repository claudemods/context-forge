# Context Forge

**One Claude Code plugin, one entry point: `/context-forge:forge`.** Describe what you want; it routes you to the right skill out of 21 skills.

Context Forge merges five open-source agent toolkits so you install once instead of five times.

## What's inside

| Area | What it does | Skills |
|---|---|---|
| **Coding discipline** | Think before coding, keep it simple, make surgical changes, verify against goals | `karpathy-guidelines` |
| **Workspace design (ICM)** | Turn a process, repo or vault into an agent-friendly folder workspace; audit and restructure existing ones | `icm-architect`, `icm-workspaces` (script-to-animation, voice-driven-animation, course-deck-production, workspace-builder) |
| **Design and review (EGM)** | Brainstorm, draft and review designs with fresh-context "goldfish" reviewers; document a codebase; detect design drift | `egm-brainstorm`, `egm-draft`, `egm-review`, `egm-review-loop`, `egm-resolve`, `egm-bootstrap`, `egm-drift-report` + 10 reviewer agents |
| **Social media team** | Brand onboarding, content calendar, captions, LinkedIn/Threads/X posts, creatives, scheduling, monthly review | `social-media-manager` + 9 specialists |
| **Router** | Picks the right capability and chains them | `forge` |

## Install

```sh
claude plugin marketplace add claudemods/context-forge
claude plugin install context-forge@context-forge
```

Start a new session, then type `/context-forge:forge` or call any skill directly, e.g. `/context-forge:egm-brainstorm`.

## Examples

```text
/context-forge:forge I want to design a webhook system and have it reviewed
/context-forge:forge turn this folder of research notes into an ICM workspace
/context-forge:forge set up a month of social content for a bakery
/context-forge:egm-review design_draft.md
```

A typical feature chain: `icm-architect` (optional) -> `egm-brainstorm` -> `egm-draft` -> `egm-review` -> `egm-resolve` -> build under `karpathy-guidelines` -> `egm-drift-report`.

## Layout

```
.claude-plugin/   manifests, EGM agent adapters
skills/           all skills (forge is the router)
agents/           EGM reviewer personas
resources/        EGM document standards
workspaces/       ICM ready-made pipelines
_core/            ICM conventions and templates
docs/             egm/ and social/ guides
licenses/         upstream licenses
```

## Notes

- EGM skills are user-invoked only (`disable-model-invocation: true`); `forge` reads and follows them in-thread. Reviews need a harness that can spawn fresh subagents.
- Run ICM workspaces from a copy in your own project, not inside the plugin cache.
- Social skills refer to each other as `/skill-name`; in the plugin the real name is `/context-forge:skill-name`. Going through `forge` avoids the mismatch.
- The social media skills use optional MCP tools (image generation, Blotato scheduling); see `docs/social/SETUP.md`.

## Credits and licenses

Context Forge bundles work by others, each under its own license: Karpathy skills (MIT), icm-architect and ICM workspaces (MIT), Elephant-Goldfish Model by Google (Apache-2.0, not an officially supported Google product), and social-ai-team (license unconfirmed). See [NOTICE.md](NOTICE.md) and [licenses/](licenses/).
