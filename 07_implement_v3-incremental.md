# 07 · Implement · v3 (incremental)

Like v2, but one bug at a time. You check each fix in the browser before the agent moves on.

First start the app in a separate terminal: `.venv/bin/streamlit run streamlit_app.py` (Windows: `.venv\Scripts\streamlit run streamlit_app.py`). It reloads when files change.

```text
Implement the plan in <feature-folder>, one bug at a time, in the plan's order. Read the latest plan and all plan reviews first. Where a review corrects the plan, the review wins.

For each bug:
1. Make the change for that bug only.
2. Run `python -m py_compile` with the .venv Python on the files you touched.
3. Stop and tell me in 2–3 lines what you changed and exactly what to click in the running app to see that it's fixed.

Wait for my "ok" before the next bug. If I report a problem, fix it before moving on. Don't start the app server; it's already running.
```
