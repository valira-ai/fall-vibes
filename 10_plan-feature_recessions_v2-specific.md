# 10 · Feature: recession detection · v2 (specific)

An EDA and domain-knowledge task with no new dependencies. Numbers to check the result against are in the README.

```text
Plan a feature that detects and highlights big GDP drops. This is the planning step of the CLAUDE.md workflow: write the plan to docs/ and don't change any code.

What I want:
- A year-over-year change series per country. Years where GDP fell by more than a threshold (slider, default 5 %) are marked on the "GDP over time" chart, with the change in the tooltip.
- A table of the largest drops for the selected countries and years: country, year, change in %, and how many years it took to get back to the previous peak (or "not yet").

The plan must address:
- Units: the data is GDP in current US$. A drop can be a real contraction, a currency devaluation, or both. Before planning, look at a few big drops in the data and think about which kind they are. Then propose how to deal with it, for example: wording ("drop in US$ GDP" rather than "recession"), or adding World Bank constant-price GDP (NY.GDP.MKTP.KD) as a second dataset. Compare the options and recommend one.
- Missing data: a gap between two years is not a drop. How are gaps handled in the year-over-year change and in the recovery count?
- Aggregates: should World and regions get markers too?
- Chart: the chart is a plain st.line_chart today, which can't show markers. Say what replaces it. Altair and Vega-Lite already come with Streamlit, so this needs no new dependency.
- Verification: list a few well-known cases (e.g. 2009, 2020, and some big currency crises) with the values you expect from this data, computed by actually running code, plus headless AppTest checks. Don't start the server.

End with numbered open questions, each with options and your recommendation.
```
