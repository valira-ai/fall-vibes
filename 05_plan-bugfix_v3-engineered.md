# 05 · Plan the bug fix · v3 (engineered)

Same bugs as v2, plus the constraints you'd give a new colleague: check facts by running code, no new dependencies, and leave product decisions to you.

```text
Plan a fix for these bugs in the dashboard. Follow the workflow in CLAUDE.md: this is the planning step, so write the plan to docs/ and don't change any code.

1. When I clear the country selection, the app should show the "Select at least one country" warning, but it never does.
2. When a country's GDP fell over the selected years, its metric tile still shows a green up arrow.
3. For some countries the tile shows "nanB" or "nanx" instead of a value.
4. The country list mixes real countries with regions and income groups (World, Euro area, High income, ...), and everything is shown as a 3-letter code, so you can't tell what you're picking.

For each bug, give the root cause (file:line), the proposed fix, and how we'll check that it's fixed.

Constraints:
- Keep the changes small and local. Don't restructure the app.
- No new dependencies. If a fix only works with a newer version of an existing dependency, say so and offer an alternative that doesn't need it.
- Check facts about the data by running code, not by guessing. For example: how many rows are regions or aggregates rather than countries, and which countries are missing a value for 2022.
- Verification: propose how to check each fix. Headless checks with streamlit.testing.v1.AppTest are fine. Don't start the app server.
- Say explicitly what's out of scope.

End the plan with numbered open questions. For each one, give the options and your recommendation. Don't make product decisions for me, such as how growth should be displayed or whether regions should be hidden or removed.
```
