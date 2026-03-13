# Codex App Explain Skill

Portable layered teaching and re-explanation for `Codex App`.

This repository ships one installable `Codex App` skill for explanation work:
concept teaching, derivation unpacking, slide or PDF passage explanation, and
bounded homework-step explanation.

This public repository now also documents the stable mode split used for these
tasks:

- `short-concept mode` for one concept or one local blocker
- `prerequisite-chain mode` for hidden dependency chains
- `paper-sentence mode` for explicit sentence-by-sentence reading
- `full-layered mode` for full rebuilds and derivations

## What Ships

- installable skill:
  [`codex-app-explain`](./codex-app-explain)
- bundled references for teaching principles, source binding, and route
  adaptation
- a public mode reference for concept, chain, sentence-reading, and layered
  teaching routes
- root-level docs for installation, scope, and privacy boundary

## Install / Use

- `Codex App`: install the skill from this repo path `codex-app-explain`
- GitHub install target:
  - repo: `<owner>/codex-app-explain-skill`
  - path: `codex-app-explain`
- Restart `Codex App` after installation so the new skill is discovered.

## Trigger Examples

- `Explain this definition step by step.`
- `Where does this derivation step come from?`
- `Teach me this equation from basic to rigorous.`

## Non-Trigger Examples

- `Remember my formatting preference.`
- `Find this file for me.`
- `Write the full assignment for me.`

## Privacy Boundary

This public skill keeps the workflow generic and reusable.

- It excludes personal memory files, local profile data, and private companion
  workflows.
- The published source embeds no personal absolute paths.
- It keeps examples generic rather than course-specific or identity-specific.

## Companion Boundary

This repository is the teaching-workflow half of the stack.

- It owns route selection, source binding, prerequisite handling, and stop
  conditions.
- It does not own persistent user memory or user-specific formatting.
- When a host environment provides a separate output-rules skill, that
  companion should own notation and layout while this skill continues to own
  the teaching route.

## Repository Layout

- `codex-app-explain/`: installable `Codex App` skill
- `codex-app-explain/references/`: bundled public teaching references
- `CHANGELOG.md`: release history
- `LICENSE`: `MIT`

Chinese:

- [README.zh-CN.md](./README.zh-CN.md)
