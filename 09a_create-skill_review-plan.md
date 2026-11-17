# 09a · Create a skill: review-plan

Turns the long prompt from step 06 into `/review-plan`. A skill is a markdown file with instructions the agent loads only when it's needed, either because you call it by name or because its description matches the task.

If you're in a new session, paste the prompt from `06_review-plan_long.md` where it says so. (The agent can't read it itself, because the prompts live in a separate repo.)

```text
I've been using a long plan review prompt, and we'll review more plans today. Turn it into a project skill so I can just run /review-plan.

- Create it at .claude/skills/review-plan/SKILL.md.
- Base it on the plan review prompt I used earlier in this conversation. If you don't have it, ask me to paste it.
- Argument: the feature folder, e.g. docs/2026-10-21-1005_fix-dashboard-bugs. If none is given, use the most recent feature folder under docs/ and say which one you picked.
- Don't copy things that already live in CLAUDE.md (the workflow, folder layout, commands). Refer to CLAUDE.md instead, so there's one source of truth.
- Write the description so it's clear when this skill should be used. That's what decides whether the agent picks it up on its own.
- Keep it short. Cut instructions a capable reviewer would follow anyway, and keep the ones that change the result.

Show me the skill when you're done. Don't run it yet.
```

What to point out: the skill's `description` is the only part the agent always sees; the body is loaded on demand. That's why skills don't bloat the context the way a huge CLAUDE.md does.
