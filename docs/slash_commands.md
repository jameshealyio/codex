# Slash commands

For an overview of Codex CLI slash commands, see [this documentation](https://developers.openai.com/codex/cli/slash-commands).

## Fork-specific: `/ralph`

This fork adds a custom slash command:

- `/ralph`
  - Shows a quick guide in the transcript for using Ralph mode.
- `/ralph <goal>`
  - Sends a structured prompt that asks Codex to:
    - run iterative loops until the goal is complete,
    - compact context around 60% usage,
    - emit short progress checkpoints each loop.

Example:

```text
/ralph ship the failing test fix and update docs
```
