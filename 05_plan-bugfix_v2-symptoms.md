# 05 · Plan the bug fix · v2 (symptoms)

Describes the bugs the way a user would: what you see, not why it happens. Works in any session.

```text
Plan a fix for these bugs in the dashboard. Follow the workflow in CLAUDE.md: this is the planning step, so write the plan to docs/ and don't change any code.

1. When I clear the country selection, the app should show the "Select at least one country" warning, but it never does.
2. When a country's GDP fell over the selected years, its metric tile still shows a green up arrow.
3. For some countries the tile shows "nanB" or "nanx" instead of a value.
4. The country list mixes real countries with regions and income groups (World, Euro area, High income, ...), and everything is shown as a 3-letter code, so you can't tell what you're picking.

For each bug, give the root cause (file:line), the proposed fix, and how we'll check that it's fixed.
```
