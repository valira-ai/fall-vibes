# 04 · Put our workflow into CLAUDE.md

CLAUDE.md can also tell the agent how you want to work. From here on, every change goes plan → plan review → implementation → code review, and each step leaves a file in `docs/`.

~~~text
Add a "Workflow (always follow)" section to CLAUDE.md that describes how we'll work from now on. Keep it short and precise.

Every feature or bug fix goes through four steps, and each step leaves a markdown file under docs/:

1. Planning: plan the change together with me. Create a feature folder docs/YYYY-MM-DD-HHMM_<kebab-case-slug>/ (timestamp = when work started) with three subfolders: plans/, plan_reviews/, code_reviews/. Write the plan to plans/. No code changes in this step.
2. Plan review: review the plan and write the review as a new file in plan_reviews/. If the plan is revised afterwards, write a new timestamped plan file instead of overwriting the old one.
3. Implementation: implement the change following the latest plan and all of its reviews.
4. Code review: review the diff and write the review as a new file in code_reviews/.

Every file is prefixed with a timestamp YYYY-MM-DD-HHMM_ so files sort chronologically. Get it from `date +%Y-%m-%d-%H%M`, don't make it up. Only move to the next step when I agree.

Include a small example of the folder layout. Also add a "Rules" section with one rule: don't write comments that restate what the code does; only comment where the code isn't self-explanatory.
~~~
