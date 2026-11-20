# 09c · Create a skill: review-code

Turns `08_code-review.md` into `/review-code`. The name avoids a clash with the built-in `/code-review`.

```text
Create a project skill at .claude/skills/review-code/SKILL.md for the code review step of the CLAUDE.md workflow, so I can run /review-code <feature-folder>.

Base it on the code review prompt I used earlier in this conversation. If you don't have it, ask me to paste it. It must:
- Review the uncommitted diff, plus new files, against the latest plan and plan reviews in the feature folder.
- Check correctness, edge cases, plan conformance (missing and unrequested work), code quality per CLAUDE.md Rules, and whether CLAUDE.md is still accurate.
- Actually run checks: compile, plus a headless AppTest run from a temporary script outside the repo. Never start the server.
- Write the review as a new timestamped file in code_reviews/, with numbered findings (severity, file:line, fix) and a "Checks performed" section.
- Never change code.

Name it review-code so it doesn't clash with the built-in /code-review. Refer to CLAUDE.md instead of copying it. Write a clear description. Show me the result, don't run it.
```
