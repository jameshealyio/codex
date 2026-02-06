# Slash commands

For an overview of Codex CLI slash commands, see [this documentation](https://developers.openai.com/codex/cli/slash-commands).

## Fork-specific: `/ralph`

This fork adds a custom slash command:

- `/ralph`
  - Shows an in-app guide and starts an interactive step-by-step setup flow
    (goal -> loops -> compaction threshold -> optional instructions file).
- `/ralph [options] <goal>`
  - Sends a structured prompt that asks Codex to:
    - run iterative loops until the goal is complete,
    - compact context at a configurable threshold (default 60%),
    - emit short progress checkpoints each loop.

Supported options:

- `--loops, -l <n>`
  - Loop budget (default `6`, range `1..50`).
- `--compact-at <percent>`
  - Context compaction threshold (default `60`, range `20..90`).
- `--instructions, -i <path>`
  - Load external guidance from a file such as `INSTRUCTIONS.md`.

Example:

```text
/ralph --loops 8 --instructions INSTRUCTIONS.md ship the failing test fix and update docs
```
