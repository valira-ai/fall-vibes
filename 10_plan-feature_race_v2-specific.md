# 10 · Feature: GDP car race · v2 (specific)

Same feature, with the decisions that came up last time surfaced up front.

```text
Plan a new "GDP race" section for the dashboard, above "GDP over time". This is the planning step of the CLAUDE.md workflow: write the plan to docs/ and don't change any code.

The idea: one lane per selected country, each with a car showing that country's flag. The cars race across the screen, and higher GDP means a faster car.

The plan must address:
- Mechanics: compare at least two options. For example, a timeline race through the selected years (speed = that year's GDP, so cars overtake as economies change) vs constant speed from the end year. Recommend one.
- Scaling: with the USA next to Malta, linear speed means the small car barely moves. Options and a recommendation.
- Missing data: years without GDP, and countries with no data at all.
- How it's built: Streamlit has no animation widget, so explain how the animation is embedded and how data gets from Python to it. No new dependencies.
- Flags: emoji vs images (and whether images need internet or a third-party site). What regions and income groups show instead.
- Look: light and dark theme, lots of countries selected, one country selected, users who prefer reduced motion.
- Security: if country names are inserted into HTML/JS, how they're escaped.
- Code layout: keep streamlit_app.py readable; say what goes in a new module.
- Verification: what can be checked headlessly (AppTest) and what needs a manual browser check.

End with numbered open questions, each with options and your recommendation.
```
