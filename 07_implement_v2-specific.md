# 07 · Implement · v2 (specific)

Says which documents count, what wins when they conflict, and what "done" means. Works in the planning session or a fresh one. Replace `<feature-folder>`.

```text
Implement the change planned in <feature-folder>. This is the implementation step of the CLAUDE.md workflow.

- Read the latest plan in plans/ and every review in plan_reviews/. Where a review corrects the plan, the review wins, unless the plan or my answers in this conversation came later. My answers to the open questions count as part of the plan.
- Before relying on the plan's description of the current code, check that it's still accurate.
- If an open question blocks you and hasn't been answered, ask me. Otherwise take the safe option and tell me which one you took.
- Follow the plan's file list and approach. Match the style of the surrounding code and follow the Rules in CLAUDE.md.
- Verify as you go: at least `python -m py_compile` with the .venv Python on every file you touch, plus a headless run of the app with streamlit.testing.v1.AppTest that exercises each fix. Run those checks from a temporary script outside the repo. Don't start the app server; I'll check in the browser myself.
- If the change makes CLAUDE.md out of date, update it.

When done, tell me: what you implemented, which review findings you addressed, anything you deferred, and exactly which checks you ran with their results.
```
