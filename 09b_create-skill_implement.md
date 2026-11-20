# 09b · Create a skill: implement

Turns `07_implement_v2-specific.md`, plus whatever you had to correct during implementation, into `/implement`.

```text
Create a project skill at .claude/skills/implement/SKILL.md for the implementation step of the CLAUDE.md workflow, so next time I can run /implement <feature-folder>.

It should cover:
- Which documents to read: the latest plan, every plan review, and my answers in the conversation. What wins when they conflict, judged by timestamps.
- Checking the plan's claims about the current code before relying on them.
- When to ask me and when to take the safe default.
- Verification: whatever CLAUDE.md lists under Commands, and at least py_compile plus a headless AppTest run from a temporary script outside the repo. Never start the server. Report honestly what was run.
- Commenting rules, strictly: the default is no comment. No comments that narrate the change or restate the code.
- The hand-off: what was done, which review findings were addressed, what was deferred, the check results, and a reminder that the code review comes next.

Also include anything you noticed during the implementation we just did that I had to correct, or that should be done differently next time.

Refer to CLAUDE.md for the workflow and commands instead of copying them. Write a description that makes clear when to use the skill. Show me the result, don't run it.
```
