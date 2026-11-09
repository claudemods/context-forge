# Notice

Context Forge bundles unmodified-in-substance copies of these projects, with paths and command prefixes adjusted:

- andrej-karpathy-skills by forrestchang (MIT)
- icm-architect by Jake Van Clief (MIT) - licenses/LICENSE-icm-architect-MIT
- Interpretable-Context-Methodology workspaces by Model Workspace Protocol Contributors (MIT) - licenses/LICENSE-icm-workspaces
- elephant-goldfish-model by Google LLC (Apache-2.0) - licenses/LICENSE-egm-APACHE-2.0. Changed: plugin name/prefix (`egm:` -> `context-forge:`), docs moved to `docs/egm/`, Codex-only `openai.yaml` files removed. Not an officially supported Google product.

The Karpathy skills upstream ships no LICENSE file in the copy provided; its plugin manifest declares MIT.

- social-ai-team (10 social media skills + setup docs), copied from `social-ai-team-main`. The copy carried no LICENSE file; the repository owner states it is open source. Its `install.sh` / `install.bat` were not included. Skill references were changed from `/skill` and `~/.claude/skills` to `/context-forge:skill` and `${CLAUDE_PLUGIN_ROOT}`.
