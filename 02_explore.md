# 02 · Explore the repo

Understand before you change. The numbered bug list from this step is what `05_plan-bugfix_v1-vague.md` refers to, so run 05 v1 in the same session.

The environment doesn't exist yet (step 03), so the agent may not be able to run pandas. That's fine: it should say which claims it couldn't verify.

```text
I'm new to this repo. Explore it and explain it to me. Don't change any files.

1. What the app does from a user's point of view, and how to run it.
2. How the data flows: where it's loaded, how it's transformed, and what drives each part of the UI. Reference code as file:line.
3. The data in data/gdp_data.csv: rows, columns, year range, what's missing, anything surprising.
4. Bugs and suspicious behavior: anything that's wrong or breaks for some input. For each one, give it a number and tell me what the user sees, how to reproduce it, and where it comes from in the code. Check your claims against the actual data if you can run code. If you can't, say which claims are unverified.
5. Separately, a short list of improvements that aren't bugs.

Be concise. Number the bugs so I can refer to them later.
```

Last time the agent found 4 bugs: the empty-selection warning never shows, falling GDP gets a green arrow, `nanB`/`nanx` for missing data, and regions mixed in with countries shown as bare codes. It also flagged unreadable chart axes (`1,960`, raw dollars). If a participant's agent misses some of them, that's a discussion point, not a failure.
