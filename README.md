# Context Forge

Four agent tools merged into one Claude Code plugin with one entry point: `/context-forge:forge`.

| Source | What it adds here | Skills |
|---|---|---|
| [andrej-karpathy-skills](https://github.com/forrestchang/andrej-karpathy-skills) | Think before coding, simplicity first, surgical changes, goal-driven execution | `karpathy-guidelines` |
| icm-architect (Jake Van Clief) | Designs or restructures any process/folder/repo into an ICM workspace; link, index, viz and quote-check scripts | `icm-architect` |
| [Interpretable-Context-Methodology](https://arxiv.org/abs/2603.16021) | Ready-made pipelines: script-to-animation, voice-driven-animation, course-deck-production, workspace-builder | `icm-workspaces` |
| [elephant-goldfish-model](https://github.com/google/elephant-goldfish-model) (Google) | Brainstorm, draft and review designs with fresh-context "goldfish" reviewers; bootstrap docs; drift reports | `egm-brainstorm`, `egm-draft`, `egm-review`, `egm-review-loop`, `egm-resolve`, `egm-bootstrap`, `egm-drift-report` + 10 reviewer agents |

`forge` is the router: describe what you want and it picks the capability (see [skills/forge/SKILL.md](skills/forge/SKILL.md)).

## Install

```sh
claude plugin marketplace add claudemods/context-forge
claude plugin install context-forge@context-forge
```

Then start a new session and try `/context-forge:forge`, or call any skill directly, e.g. `/context-forge:egm-brainstorm`.

## Layout

```
.claude-plugin/   plugin + marketplace manifests, EGM agent adapters
skills/           forge, karpathy-guidelines, icm-architect, icm-workspaces, egm-*
agents/           EGM reviewer personas (read by the adapters)
resources/        EGM document standards
workspaces/       ICM ready-made pipelines
_core/            ICM conventions and templates (shared by workspaces)
docs/egm/         EGM harness docs
licenses/         upstream licenses
```

## Notes

- EGM skills keep `disable-model-invocation: true`; `forge` reads and follows them in-thread. Reviews need a harness that can spawn fresh subagents.
- Run ICM workspaces from a copy in your own project, not inside the plugin cache.
- The `/context-forge:` prefix replaces the original `/egm:` prefix in all EGM docs and skills.

## Licensing

Mixed, per upstream: EGM is Apache-2.0, icm-architect and the ICM workspaces are MIT, Karpathy skills are MIT. See [NOTICE.md](NOTICE.md) and [licenses/](licenses/). Check each upstream's license before redistributing.
