# 10 · Feature: GDP per capita · v2 (specific)

Needs a second dataset. The prompt says where to get it, how to store it, and how to check the join.

```text
Plan adding GDP per capita to the dashboard. This is the planning step of the CLAUDE.md workflow: write the plan to docs/ and don't change any code.

Data:
- Population comes from the World Bank indicator SP.POP.TOTL (total population), the same source as data/gdp_data.csv.
- The app must not hit the network at runtime. Plan a small script that downloads the data once and saves it into data/, committed together with the script, so the download is reproducible. Check the raw file format before assuming it matches gdp_data.csv.
- Validate the join and report the numbers in the plan: country codes present in one file but not the other, years where GDP exists but population doesn't (and the reverse), and how aggregates (World, regions, income groups) behave.

UI:
- A toggle between "Total GDP" and "GDP per capita" that switches the line chart and the metric tiles.
- Per capita values are in dollars, not billions. The metric tiles show billions today. Say how the tiles, chart axis, and tooltips change, and keep the formatting rules in one place.

The plan must also cover:
- Missing population data: what the user sees.
- A sanity check: per capita values for a few well-known countries, compared against the World Bank's own GDP per capita indicator (NY.GDP.PCAP.CD) for a couple of years.
- Out of scope: PPP and inflation adjustment. Mention them, don't plan them.
- Verification with headless AppTest checks. Don't start the server.

End with numbered open questions, each with options and your recommendation.
```
