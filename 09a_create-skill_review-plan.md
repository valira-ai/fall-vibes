# 09a · Create a skill: review-plan

Turns the review prompt from 06 into `/review-plan`. A skill is a markdown file with instructions. The agent always sees its description and loads the rest only when needed.

In a new session, the agent will ask you to paste the prompt from `06_review-plan_long.md`.

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
