# 10 · Feature: GDP forecast · v2 (specific)

Evaluation first, chart second: a backtest, naive baselines to beat, and no leakage from future data.

```text
Plan a new "GDP forecast" section for the dashboard. This is the planning step of the CLAUDE.md workflow: write the plan to docs/ and don't change any code.

What I want:
- For each selected country, a forecast of GDP for the next N years after the last year of data (N from a slider, 1–10, default 5), with an uncertainty band, drawn as a continuation of the historical line.
- A backtest that tells us whether the forecast is any good: fit on data up to a cutoff year, forecast the years after it, and compare with what actually happened. Show the error per country (e.g. MAPE) next to two naive baselines: last value carried forward, and constant average growth (drift). If the model doesn't beat the baselines for a country, the UI should say so.

The plan must address:
- Model: compare 2–3 options, e.g. log-linear trend, drift on log GDP, and exponential smoothing or ARIMA from statsmodels. Compare them on accuracy, dependencies, and how they handle short or gappy series. Recommend one. statsmodels would be a new dependency: say whether it's worth it.
- Leakage: nothing after the cutoff may influence the backtest, including scaling and parameter selection.
- Missing data: gaps in a series, series that end before 2022, and series with fewer than about 15 points.
- Shocks: 2009 and 2020 are in the data. How do they affect the fit and the uncertainty band?
- Units: the data is GDP in current US$, so it mixes real growth, inflation, and exchange-rate moves. Say what the forecast actually means, and how the UI communicates that.
- Performance: Streamlit reruns the whole script on every interaction. Say what gets cached and how.
- Verification: a worked example for one country that I can check by hand, plus headless AppTest checks. Don't start the server.

End with numbered open questions, each with options and your recommendation.
```
