# Notice

Context Forge bundles unmodified-in-substance copies of these projects, with paths and command prefixes adjusted:

- andrej-karpathy-skills by forrestchang (MIT)
- icm-architect by Jake Van Clief (MIT) - licenses/LICENSE-icm-architect-MIT
- Interpretable-Context-Methodology workspaces by Model Workspace Protocol Contributors (MIT) - licenses/LICENSE-icm-workspaces
- elephant-goldfish-model by Google LLC (Apache-2.0) - licenses/LICENSE-egm-APACHE-2.0. Changed: plugin name/prefix (`egm:` -> `context-forge:`), docs moved to `docs/egm/`, Codex-only `openai.yaml` files removed. Not an officially supported Google product.

The Karpathy skills upstream ships no LICENSE file in the copy provided; its plugin manifest declares MIT.

- social-ai-team (10 social media skills + setup docs), copied from `social-ai-team-main`. The copy had no LICENSE file and no stated author, so its license terms are unconfirmed. Its `install.sh` / `install.bat` were not included (the plugin install replaces them). Inside the plugin its skills are invoked as `/context-forge:<skill>`; text inside those skills that says `/skill-name` or "~/.claude/skills" refers to the standalone install.
