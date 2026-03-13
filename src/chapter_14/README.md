# Chapter 14: Capstone Project

This chapter brings together every technique from the course in a single
end-to-end forecasting project.  We work with the **Alcohol Sales** dataset
(`Alcohol_Sales.csv`), which exhibits trend, strong seasonality, and changing
variance -- a realistic mix of challenges.

The project follows the five-step forecasting workflow introduced in
Chapter 01:

1. **Define the problem** -- forecast the next 24 months of U.S. alcohol sales
2. **Explore the data** -- time plots, seasonal plots, decomposition,
   stationarity tests
3. **Fit candidate models** -- benchmarks, statistical models, Prophet
4. **Evaluate and compare** -- same train/test split, same metrics, cross-validation
5. **Produce the final forecast** -- retrain on all data, generate prediction
   intervals, communicate results

## Notebooks

| # | Notebook | Topics |
|---|----------|--------|
| 1 | `01_capstone_eda.ipynb` | Problem definition, data loading, summary statistics, time/seasonal/subseries/lag plots, classical and STL decomposition, ADF and KPSS stationarity tests, differencing, ACF/PACF, train/test split |
| 2 | `02_capstone_modelling.ipynb` | Benchmark models (Naive, Seasonal Naive, Drift), ETS, ARIMA, SARIMA, Holt-Winters, Prophet, model comparison table, forecast combination, final forecast with prediction intervals, conclusions |

## Key Concepts

- **Structured workflow**: a repeatable process prevents ad-hoc analysis and
  ensures nothing is overlooked
- **Honest evaluation**: all models evaluated on the same held-out test set
  with the same metrics (MAE, RMSE, MAPE)
- **Forecast combination**: averaging the top models often outperforms any
  single model
- **Prediction intervals**: communicating uncertainty is as important as the
  point forecast
- **Lessons learned**: reflecting on what worked, what did not, and why

## References

- [FPP3: The Forecaster's Toolbox](https://otexts.com/fpp3/) -- Hyndman & Athanasopoulos
- All previous chapters of this course
