# AGENTS.md — layer-openclaw-full

Standalone candy repo for the `openclaw-full` meta-composition layer — the
OpenClaw gateway plus every feasible headless CLI tool, no system Chrome/CDP. The
candy lives in `charly.yml` at the repo root: the composed `candy:` list, the
cross-section `plan:` `check:` assertions, and the embedded `skill:` entity
projected into the marketplace corpus as `/charly-openclaw:openclaw-full`.

Canonical files:

- `charly.yml` — the `openclaw-full:` candy entity and the
  `openclaw-full-skill:` skill entity.
- `CHANGELOG/` — per-CalVer release history.
- `.github/workflows/tag-on-merge.yml` — CalVer tag + `CHANGELOG/` on merge.
- `README.md` — user overview only; never agent guidance.

## Load these skills first (R0)

- `/charly-openclaw:openclaw-full` — the owning skill. The maximal headless
  composition and its tool stack. Load before editing or troubleshooting.
- `/charly-image:layer` — the candy authoring reference (`charly.yml` schema,
  `plan:` step verbs incl. `check:`, the `candy:` composition list, and service
  declarations). Load before editing any entity field or plan step.
- `/charly-automation:openclaw-deploy` — gateway/skill configuration when the
  change touches how tools are exposed.

## Build / validate / test

- The merge gate is the **org-wide** `charly/pr-validator` (required check
  `validate / validate`, defined in `opencharly/.github`); this repo has **no
  per-repo candy gate** and ships only `.github/workflows/tag-on-merge.yml`.
- The candy's `plan:` `check:` steps assert the **cross-section** of composed
  tool artifacts (claude, mcporter, rg, sqlite3, tmux, ffmpeg, gh, uv) — they
  FAIL if any composed candy is dropped from the metalayer.

## Modify this repo

- Edit the `openclaw-full:` candy entity AND the `openclaw-full-skill:` skill
  entity in `charly.yml` together. The skill is the projected usage source.
- Keep the composed `candy:` list and the cross-section checks in step: adding or
  dropping a composed candy means updating both, or the checks stop proving the
  composition.
- Pin composed candies at merged tags only.
- New behaviour claims belong in the `plan:` as an observable `check:` step, and
  in the skill body.

## Landing

- The authoritative rulebook is the umbrella `AGENTS.md` in
  `opencharly/opencharly` and `charly/AGENTS.md` in the charly repo — read it
  before landing.
- Release history lives in `CHANGELOG/`.
