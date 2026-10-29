# role-software-engineer-lead

**Version:** 0.1.0 · `rasa.module.role.software-engineer-lead` · public

The **Software Engineer Lead** role (`software-engineer-lead`) as a RasaOS role module. The ask is software: a feature, a fix, an audit of code, infrastructure or a decision about them; the operator's own standards apply

| File | What it is |
|---|---|
| `role.json` | The role's fields (id, name, summary, version, consumers, knowledge, takes, kinds, grants, crew). galt publishes them to `/tenant_config/roles/software-engineer-lead`. |
| `prompt.md` | The role's prompt, from RasaOS/module-crew `content/crew/leads/software-engineer.md` at `f6fea0d`. |
| `.claude-plugin/plugin.json` | The plugin manifest, which makes the repo loadable into a session with `--plugin-dir`. |
| `rasa.json` | The Element manifest: `kind: module`, with the role's id and version under `rasa`. |
| `bin/check-role` | The release gate. |

Role version **1**, from RasaOS/module-crew `content/crew/leads/software-engineer.md` at `f6fea0d`.

**Crew.** A crew **lead** (galt card `software-engineer`). `role.json` `crew` holds that tier's card fields; galt reads them when a crew hires or runs this role. The prompt's `{cli}`, `{crew}` are filled by galt in a crew; outside a crew they stay as written.

## Loading it

- **As an agent's brain:** `galt agent new <name> --brain RasaOS/role-software-engineer-lead@v0.1.0`. galt reads `role.json` and `prompt.md`. There is no role assignment this way, so no grants.
- **In a crew:** a crew hires it by its card name `software-engineer` once galt reads crew roles from the role list (tenant ADR 2026-10-28-one-role-list); until then galt runs its in-code copy.
- **Public:** any computer can fetch it. No vault token is needed.

## Changing the role

This repo is the role's source. Change it through a PR on this repo (vsi-tenant's `/role` skill does it): bump `role.json` `version` and the Element version together. Until galt reads crew roles from here, galt's in-code copy must get the same change.
