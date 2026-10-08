# AGENTS.md — layer-openclaw-full

**This repo is retired.** It owns no entities any more: the `openclaw-full`
metalayer and its `/charly-openclaw:openclaw-full` skill were dropped when the
OpenClaw family was consolidated into `opencharly/layer-openclaw`
(opencharly/opencharly#431). The family's gateway image and its layer live there,
and no `-full`, `-desktop` or `-ml` variant returns.

The tool layers this metalayer composed are unaffected — they live in their own
repos and stay available. What was dropped is the pre-packaged composition, and the
owning skill that documented it went with it, so no reader is left holding a
procedure for a layer that no longer exists.

Do not add entities here, and do not compose this repo — it is kept only until the
operator archives it. A change that belongs to the OpenClaw family belongs in
`opencharly/layer-openclaw` instead.

There is no build, validate or test surface left in this repo beyond the org-wide
`charly/pr-validator` check that every repo carries. The authoritative rulebook is
the umbrella `AGENTS.md` in `opencharly/opencharly`.
