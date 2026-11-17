# 01 · Initialise the repo

Built-in command in both Claude Code and Codex. It explores the repo and writes `CLAUDE.md` (Claude Code) or `AGENTS.md` (Codex).

```text
/init
```

The generated file usually says too much: it restates the README, lists every file, and gives generic advice ("write clean code"). Every line in it is read on every request, so trim it. Follow up with:

```text
Review the CLAUDE.md you just wrote. Keep only what an experienced engineer new to this repo couldn't quickly figure out from the code: commands, non-obvious architecture, gotchas, conventions. Remove anything generic, anything that just restates the README, and file listings. Show me what you removed and why.
```

What to point out: open `CLAUDE.md` and read it together. Is anything wrong? (Agents sometimes state guesses as facts.) Fix it by hand. It's your file, not the agent's.
