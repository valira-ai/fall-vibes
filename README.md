# Workshop prompts

Prompts for the AI-assisted engineering workshop, in the order we run them. Each file has a short note for the facilitator, then the prompt in a code block to copy.

These prompts live in their own repo, separate from the dashboard, so the agents participants run on the dashboard can't read them in advance. Participants copy each prompt from here into their agent. They should not copy this folder into the dashboard repo.

Using Codex or another tool instead of Claude Code: wherever a prompt says `CLAUDE.md`, use `AGENTS.md`. The skill paths in step 09 (`.claude/skills/`) are for Claude Code; in another tool, ask the agent where it keeps project skills.

Files with `v1`, `v2`, `v3` are alternative versions of the same step, from vague (vibe coding) to explicit (engineering). Let participants pick one, or have half the room run `v1` and the other half `v3` and compare the results.

## Order

| # | File | Session | What it shows |
|---|------|---------|---------------|
| 01 | `01_init.md` | new | `/init`, then trimming the generated CLAUDE.md |
| 02 | `02_explore.md` | same | Understanding a codebase before touching it |
| 03 | `03_environment.md` | same | Letting the agent set up and verify the env |
| 04 | `04_claude-md-workflow.md` | same | Encoding *your* process in CLAUDE.md |
| 05 | `05_plan-bugfix_v1-vague.md` / `v2-symptoms` / `v3-engineered` | same as 02 for v1, any for v2/v3 | Plan before code; how much the prompt matters |
| 06 | `06_review-plan_long.md` | **new** (ideally a different model/tool) | A thorough review prompt... that you'd hate to type 3 times |
| 07 | `07_implement_v1-vague.md` / `v2-specific` / `v3-incremental` | back to the planning session, or new | Implementing against a reviewed plan |
| 08 | `08_code-review.md` | **new** (ideally a different model/tool) | Independent review of the diff |
| 09 | `09a_create-skill_review-plan.md`, `09b_…implement`, `09c_…review-code` | any | Turning repeated prompts into skills |
| 10 | `10_plan-feature_*` | new | Feature planning, pick **one** feature |
| 11 | `11_review-plan_skill.md` | new | Same review as 06, now one line |
| 12 | `12_implement_skill.md` | planning session | Same for implementation |
| 13 | `13_code-review_skill.md` | new | Same for code review |

Steps 11–13 are the payoff of 09: put the length of `06_review-plan_long.md` next to `11_review-plan_skill.md`.

## Starting state of the repo

Participants start from a fresh clone of the original template:

```bash
git clone https://github.com/streamlit/gdp-dashboard-template.git
```

That means no `CLAUDE.md`, no `docs/`, no `race.py`, and no `.claude/skills/`. All of those are outputs of the workshop. If they were already there, they'd spoil `/init` and exploration.

The feature prompts in step 10 assume the dashboard after the bug fix only: the chart is still a plain `st.line_chart`, and there's no race.

## Feature options for step 10

All plan files are written as the planning step of the CLAUDE.md workflow. The `v1` versions deliberately don't say "plan", to show whether CLAUDE.md alone makes the agent plan first.

| Feature | Files | Flavor | New deps / data | Why it's good for teaching |
|---|---|---|---|---|
| GDP car race | `10_plan-feature_race_*` | fun, frontend | none | Visual, everyone gets it, last workshop's crowd favorite |
| Forecast + backtest | `10_plan-feature_forecast_*` | modelling | maybe `statsmodels` | Leakage, naive baselines, shocks (2009/2020); the agent will happily ship a forecast that doesn't beat "last value" unless the plan forces a baseline |
| GDP per capita | `10_plan-feature_per-capita_*` | data engineering | population CSV from the World Bank | Getting a second dataset, joins, key mismatches, aggregates, reproducible downloads |
| Recession / drop detection | `10_plan-feature_recessions_*` | EDA, domain sense | none (optional: constant-price GDP) | The data is in *current US$*: big "recessions" are often currency crashes. Good test of whether the plan review catches it |

**Facts for checking the recession feature** (computed from `data/gdp_data.csv`, year-over-year change in current US$): USA 2009 −2.0 %, USA 2020 −1.5 %, World 2009 −5.2 %, World 2020 −2.9 %, Argentina 2002 −64 %, Russia 2015 −34 %, Korea 1998 −33 %, Mexico 1995 −31 %. Russia's *real* GDP fell only about 2 % in 2015, so that −34 % is almost entirely the ruble.

**Data quality facts:** 266 rows (217 economies + 49 aggregates); only 116 rows have values for every year 1960–2022; 3,558 missing cells.

**Per-capita prep:** download the population data before the workshop in case the Wi-Fi is bad. The indicator is `SP.POP.TOTL` (World Bank). The raw World Bank CSV has 4 preamble lines and a trailing empty column, unlike `data/gdp_data.csv`, which is a good thing for the agent to notice by itself.

More ideas, not prepared as prompts:
- **Data quality panel**: a missing-data heatmap (country × year), coverage %, and a "only countries with full data" filter. The easiest one, a good fallback.
- **Cluster growth trajectories**: k-means on log-GDP curves indexed to a base year (`scikit-learn`). Forces decisions about imputation and scaling that the agent shouldn't make alone.
- **Share of world GDP**: a stacked area of each country's share of `WLD`. Includes the check whether the countries actually add up to `WLD`. They don't quite: the countries sum to 98.6 % of `WLD` in 1990, 99.3 % in 2010, and 98.8 % in 2022, because countries with missing values are left out of the sum. The plan should notice the gap and explain it.
- **Indexed growth view**: a toggle to show GDP indexed to 100 at the start year, plus a log scale and CAGR in the tiles. Small, no deps, very "data".

## Where to run reviews

Run reviews (06, 08, 11, 13) in a **fresh session**, so the reviewer doesn't share the author's assumptions. Even better, use a different model or tool (last time: Claude Code for planning and implementing, Codex for reviews).
