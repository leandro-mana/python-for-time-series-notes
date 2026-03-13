# Chapter 13: Modern Forecasting Frameworks

Every forecasting library has its own API -- statsmodels, Prophet, sklearn,
pmdarima -- making it tedious to compare models fairly.  **Modern forecasting
frameworks** solve this by providing a unified interface that wraps many
backends behind a consistent fit/predict workflow.

This chapter covers two leading frameworks:

- **sktime** -- a scikit-learn-compatible toolkit for time series that unifies
  forecasting, classification, and annotation under one API
- **Nixtla's statsforecast** -- blazing-fast implementations of classical
  statistical models designed to fit hundreds of series in seconds

We also develop a **systematic model comparison workflow** and explore
**forecast combinations**, where averaging multiple models often outperforms
any single model.

## Notebooks

| # | Notebook | Topics |
|---|----------|--------|
| 1 | `01_sktime.ipynb` | Unified forecasting with sktime: ForecastingHorizon, temporal train/test split, AutoARIMA / ETS / Naive via a common API, pipelines with TransformedTargetForecaster, ensembling |
| 2 | `02_statsforecast.ipynb` | Nixtla's statsforecast: AutoARIMA, AutoETS, AutoTheta, SeasonalNaive at scale; required data format (unique_id, ds, y); cross-validation; forecast combinations |
| 3 | `03_model_comparison_workflow.ipynb` | End-to-end comparison of Naive, Seasonal Naive, ETS, ARIMA, SARIMA, Holt-Winters, and Prophet; cross-validated evaluation; forecast combination; decision framework for choosing a method |

## Key Concepts

- **Unified API**: sktime wraps heterogeneous forecasting libraries behind a
  single `fit` / `predict` / `update` interface, making fair model comparison
  straightforward
- **ForecastingHorizon**: sktime's object for specifying relative or absolute
  forecast horizons, supporting both in-sample and out-of-sample prediction
- **Pipelines**: `TransformedTargetForecaster` chains preprocessing steps
  (detrending, deseasonalizing, Box-Cox) with a forecaster in a single object
- **statsforecast speed**: Nixtla's C-optimized implementations can fit
  AutoARIMA on hundreds of series in seconds -- orders of magnitude faster
  than statsmodels
- **Data format**: statsforecast requires a DataFrame with columns `unique_id`,
  `ds` (timestamp), and `y` (target value)
- **Forecast combinations**: averaging forecasts from multiple models often
  produces lower error than any individual model -- simple average, weighted
  average, and median are common strategies
- **Decision framework**: a practical flowchart for selecting forecasting
  methods based on data characteristics (length, trend, seasonality, complexity)

## References

- [sktime documentation](https://www.sktime.net/en/stable/)
- [Nixtla statsforecast](https://nixtlaverse.nixtla.io/statsforecast/index.html)
- [FPP3 Chapter 13: Forecasting Combinations](https://otexts.com/fpp3/) -- Hyndman & Athanasopoulos
- [Portilla TSA Sections 09-10: Facebook Prophet and Forecasting at Scale](https://www.udemy.com/user/joseportilla/)
- Bates, J.M. & Granger, C.W.J. (1969). *The Combination of Forecasts*. Operational Research Quarterly
