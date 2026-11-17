# 06 · Review the plan (the long prompt)

Run it in a **fresh session**, ideally with a different model or tool (last time: Codex). The reviewer should not share the planner's context or assumptions.

This prompt is deliberately long and thorough: it's what a good review actually needs. Point that out, then ask: *"We'll review two more plans today. Do you want to paste this three times?"* That's the setup for skills in step 09, where it becomes `/review-plan`.

Replace `<feature-folder>` with the folder from step 05, e.g. `docs/2026-10-21-1005_fix-dashboard-bugs`.

```text
You're reviewing an implementation plan before any code is written. Your job is to find what's wrong or missing, not to praise it. Don't change any code or the plan itself.

Plan: the latest file in <feature-folder>/plans/. If there are older plans or earlier reviews in that folder, read them for context. Also read CLAUDE.md and follow its workflow.

Check the plan against the actual code and data, not just for internal consistency:

1. Current state: are the plan's claims about the existing code true? Open the files and check every file:line reference and every "X happens because Y". Run code to check claims about the data (row counts, missing values, which codes exist), using the project's .venv.
2. Root causes: does each fix address the actual cause, or just the symptom? Would the bug come back in a slightly different situation (another country, another year range, an empty selection, missing data at either end)?
3. Edge cases: missing values, empty inputs, a single item, zero or negative numbers, the first and last year, aggregates vs countries. Name the ones the plan doesn't handle.
4. Side effects: what else does the change touch? Other UI parts that use the same data, widget state that might reset, cached functions, behavior that users rely on today.
5. Dependencies and environment: does the plan add a dependency, raise a minimum version, or rely on an API that only exists in newer versions? Check against what's installed in .venv and what requirements.txt allows. Flag every such change, even small ones.
6. Simplicity: is there a simpler fix that's just as correct? Is anything in the plan unnecessary for the stated goal (scope creep)?
7. Verification: will the proposed checks actually catch a regression? Are they runnable as described? Is there an important behavior with no check at all? Prefer checks that run headlessly (streamlit.testing.v1.AppTest) over "look at it in the browser".
8. Consistency with the repo: does the plan follow the conventions in CLAUDE.md (workflow, rules, code style)? Will CLAUDE.md need updating after this change?
9. Open questions: are the plan's open questions real decisions for the user, with options and a recommendation? Did the plan quietly make a decision that should have been a question?

Write the review to <feature-folder>/plan_reviews/ as a new file named with a timestamp from `date +%Y-%m-%d-%H%M`, e.g. 2026-10-21-1013_plan-review.md. Structure:

- Findings: numbered, most important first. For each one, give the severity (high / medium / low), what's wrong, the evidence (file:line, command output, or doc link), and a concrete fix to the plan.
- Accepted parts: a short list of what's fine as is, so it's clear what was checked.
- Recommended plan revision: a few sentences summarizing what should change.

Be specific and concise. Don't include findings you couldn't back with evidence. If you're unsure about something, say so and say what would settle it. When done, give me a 3-line summary in the chat.
```
