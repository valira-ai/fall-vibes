# Workshop prompts

The prompts we use in the workshop, in order. Copy each one from its code block into your agent.

Keep this folder separate from the dashboard repo. Otherwise the agent can read the prompts ahead of time.

Using Codex or another tool? Wherever a prompt says `CLAUDE.md`, use `AGENTS.md`. The skill paths in step 09 (`.claude/skills/`) are for Claude Code. In another tool, ask the agent where it keeps project skills.

Files marked `v1`, `v2`, `v3` are versions of the same step, from vague (vibe coding) to explicit (engineering). Try more than one and compare.

## Setup

```bash
git clone https://github.com/streamlit/gdp-dashboard-template.git
```

## Order

| # | File | Session |
|---|------|---------|
| 01 | `01_init.md` | new |
| 02 | `02_explore.md` | same |
| 03 | `03_environment.md` | same |
| 04 | `04_claude-md-workflow.md` | same |
| 05 | `05_plan-bugfix_*` | v1: same as 02, v2/v3: any |
| 06 | `06_review-plan_long.md` | new |
| 07 | `07_implement_*` | planning session, or new |
| 08 | `08_code-review.md` | new |
| 09 | `09a`, `09b`, `09c` | any |
| 10 | `10_plan-feature_*` (pick one feature) | new |
| 11 | `11_review-plan_skill.md` | new |
| 12 | `12_implement_skill.md` | planning session |
| 13 | `13_code-review_skill.md` | new |

Run reviews (06, 08, 11, 13) in a new session, so the reviewer doesn't share the author's assumptions. A different model or tool is even better.

## Features for step 10

| Feature | Files | About |
|---|---|---|
| GDP car race | `10_plan-feature_race_*` | Fun, frontend, no new dependencies |
| Forecast | `10_plan-feature_forecast_*` | Modelling, backtests, baselines |
| GDP per capita | `10_plan-feature_per-capita_*` | Adding a second dataset and joining it |
| Recession detection | `10_plan-feature_recessions_*` | Data exploration and domain sense |
