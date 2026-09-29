# openclaw-full

The maximal headless OpenClaw deployment as a charly *meta-composition* layer —
the OpenClaw gateway plus every feasible CLI tool and skill, with no system
Chrome/CDP.

The `openclaw-full` candy installs nothing of its own; it composes the OpenClaw
gateway (`pod-openclaw`), the Claude Code CLI, and the tool candies (codex,
gemini, clawhub, mcporter, oracle, xurl, summarize, playwright, blogwatcher,
gifgrep, wacli, goplaces, songsee, sag, camsnap, gogcli, ordercli, himalaya, uv,
nano-pdf, gh, tmux, ffmpeg, ripgrep, sqlite). The observable effect of the
composition is that every composed tool's key artifact lands in **one image**:
the openclaw / mcporter binaries under `~/.npm-global/bin`, the claude binary
under `/usr/local/bin`, uv under `/usr/local/bin`, and `rg` / `sqlite3` / `tmux` /
`ffmpeg` / `gh` under `/usr/bin`.

## What it provides

| Property | Value |
|---|---|
| Layer / candy | `openclaw-full` |
| Type | Meta-composition — installs nothing of its own |
| Composes | `pod-openclaw`, `layer-claude-code`, and ~26 tool candies |
| Gateway port | 18789 (checked by the composed `openclaw` candy) |
| Service / port | none of its own (the gateway service comes from `pod-openclaw`) |

## How to use it

Compose the metalayer in a box's `candy:` list — the `openclaw-full` box does
exactly this:

```yaml
openclaw-full:
  candy:
    base: cachyos
    candy:
      - agent-forwarding
      - '@github.com/opencharly/layer-openclaw-full:v2026.247.0718'
```

Then:

```bash
charly box build openclaw-full
charly config openclaw-full
charly start openclaw-full
```

## Layout

- `charly.yml` — the `openclaw-full:` candy entity (the composed `candy:` list
  and the cross-section `plan:` checks) plus the embedded `skill:` entity (the `openclaw-full-skill:` node).
- `CHANGELOG/` — per-CalVer release history.
- `.github/workflows/tag-on-merge.yml` — CalVer tag + `CHANGELOG/` on merge.
- `README.md` — this user overview.

## Related

- Owning skill: `/charly-openclaw:openclaw-full` — the maximal headless
  composition.
- Gateway: `/charly-openclaw:openclaw`.
- Deployment: `/charly-automation:openclaw-deploy`.
- ML variant: `opencharly/layer-openclaw-full-ml`.
- [`opencharly/opencharly](https://github.com/opencharly/opencharly) — the umbrella.
