# layer-openclaw-full — RETIRED

This repo is retired. Its entities were the `openclaw-full` metalayer — the
OpenClaw gateway plus every feasible headless CLI tool — and the
`/charly-openclaw:openclaw-full` skill that documented it. That variant was
**dropped**, not moved, when the OpenClaw family was consolidated into
[`opencharly/openclaw`](https://github.com/opencharly/openclaw): the family ships
the gateway image and its layer, and no `-full`, `-desktop` or `-ml` successor
returns.

**The tool layers are not retired.** codex, gemini, ripgrep, ffmpeg, gh, uv, tmux,
sqlite and the rest belong to their own repos and remain available. What is gone is
the pre-packaged "gateway plus everything" composition; a consumer that wants a
tool now composes it beside the gateway image directly.

Nothing should compose this repo. It is kept only until the operator archives it.
