# 08 · Code review

Run it in a new session, ideally with a different model or tool than the one that wrote the code.

The built-in `/code-review` (Claude Code) and `/review` (Codex) find bugs in a diff, but they don't know our plan. This prompt checks the code against the plan and saves the review in the feature folder.

```text
Review the uncommitted changes in this repo (git diff, plus any new untracked files) as the code review step of the CLAUDE.md workflow. Don't change any code.

The change was planned in <feature-folder>. Read the latest plan and all plan reviews first, so you know what was supposed to be built and which decisions were made.

Check:
1. Correctness: does the code do what the plan says, for every item in it? Look for bugs in edge cases: missing data, empty selections, a single country, first and last year, aggregates.
2. Plan conformance: anything the plan asked for that's missing, and anything implemented that the plan didn't ask for.
3. Run it: compile the touched files, and run the app headlessly with streamlit.testing.v1.AppTest using the project's .venv. Exercise the scenarios from the plan's verification section and check for exceptions. Run these from a temporary script outside the repo. Don't start the server.
4. Code quality: follows the Rules in CLAUDE.md, matches the existing style, no dead code, no comments that narrate the change, no unnecessary complexity.
5. Docs: is CLAUDE.md still accurate after this change?

Write the review to <feature-folder>/code_reviews/ as a new file named with a timestamp from `date +%Y-%m-%d-%H%M`, e.g. 2026-10-21-1021_code-review.md. Include:
- Findings: numbered, most severe first, each with severity, file:line, what's wrong, and a suggested fix. Only include findings you can back with evidence.
- Checks performed: exactly what you ran and the results, and what you didn't check (e.g. browser-only visuals).

If you find nothing wrong, say so plainly rather than inventing minor issues.
```
