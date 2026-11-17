# 07 · Implement · v3 (incremental, human in the loop)

The same as v2, but one bug at a time, with you checking each step in the browser. Slower, but you see every change and can steer early. Good for showing that you choose how much autonomy to give, and that it can differ per task.

Start the app yourself first, in a separate terminal: `.venv/bin/streamlit run streamlit_app.py` (on Windows: `.venv\Scripts\streamlit run streamlit_app.py`). It hot-reloads on save.

```text
Implement the plan in <feature-folder>, one bug at a time, in the plan's order. Read the latest plan and all plan reviews first. Where a review corrects the plan, the review wins.

For each bug:
1. Make the change for that bug only.
2. Run `python -m py_compile` with the .venv Python on the files you touched.
3. Stop and tell me in 2–3 lines what you changed and exactly what to click in the running app to see that it's fixed.

Wait for my "ok" before the next bug. If I report a problem, fix it before moving on. Don't start the app server; it's already running.
```
