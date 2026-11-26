# 01 · Initialise the repo

`/init` explores the repo and writes `CLAUDE.md` (Codex: `AGENTS.md`).

```text
/init
```

The generated file is usually too long, and the agent reads all of it on every request. Trim it:

```text
Review the CLAUDE.md you just wrote. Keep only what an experienced engineer new to this repo couldn't quickly figure out from the code: commands, non-obvious architecture, gotchas, conventions. Remove anything generic, anything that just restates the README, and file listings. Show me what you removed and why.
```

Then read it yourself and fix anything that's wrong.
