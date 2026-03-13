# Chapter 06: The Forecaster's Toolbox

The essential toolkit every forecaster needs before building sophisticated models.  This
chapter covers simple benchmark methods that every model must beat, residual diagnostics
to verify that a model has extracted all available signal, accuracy metrics to quantify
forecast quality, and time series cross-validation to estimate out-of-sample performance
honestly.

## Notebooks

| # | Notebook | Topics |
|---|----------|--------|
| 1 | `01_simple_forecasting_methods.ipynb` | Mean method, naive method, seasonal naive, drift method — benchmark forecasts that every model must outperform |
| 2 | `02_residual_diagnostics.ipynb` | Fitted values, residuals, diagnostic plots (time plot, ACF, histogram, Q-Q), Ljung-Box test, reusable `check_residuals()` function |
| 3 | `03_evaluation_metrics.ipynb` | MAE, MSE, RMSE, MAPE, MASE — scale-dependent, percentage, and scaled error metrics; train/test splitting for time series |
| 4 | `04_cross_validation.ipynb` | Why k-fold fails for time series, expanding window (walk-forward) validation, sliding window validation, comparing strategies |

## Key Concepts

- **Benchmark methods** (mean, naive, seasonal naive, drift) are the simplest possible forecasts — if a complex model cannot beat these, it is not worth using
- **Residual diagnostics** check whether a model has captured all the signal in the data: good residuals are uncorrelated, zero-mean, constant-variance, and (ideally) normally distributed
- The **Ljung-Box test** formally tests whether residual autocorrelations are collectively zero — significant results indicate unexploited information
- **Scale-dependent metrics** (MAE, RMSE) are useful for comparing methods on the same series; **percentage metrics** (MAPE) allow comparison across different scales but fail when $y_t = 0$
- **MASE** (Mean Absolute Scaled Error) uses the naive forecast as a denominator — values below 1 mean the model outperforms the naive benchmark
- **Time series train/test splits** must respect temporal order — random splitting destroys the autocorrelation structure and produces overly optimistic results
- **Expanding window** cross-validation grows the training set at each fold, while **sliding window** keeps a fixed-size training set — the choice depends on whether all history or only recent history is relevant

## References

- [FPP3 Chapter 5: The Forecaster's Toolbox](https://otexts.com/fpp3/toolbox.html) — Hyndman & Athanasopoulos
- [Portilla TSA Section 07: Forecasting](https://www.udemy.com/user/joseportilla/) — Simple forecasting methods and evaluation
- [statsmodels: Naive and Seasonal Naive](https://www.statsmodels.org/stable/generated/statsmodels.tsa.holtwinters.ExponentialSmoothing.html)
- [sklearn.metrics: Mean Absolute Error, MSE](https://scikit-learn.org/stable/modules/model_evaluation.html#regression-metrics)
- [statsmodels: acorr_ljungbox](https://www.statsmodels.org/stable/generated/statsmodels.stats.diagnostic.acorr_ljungbox.html)
- [Hyndman & Athanasopoulos — Evaluating forecast accuracy](https://otexts.com/fpp3/accuracy.html)
- [Hyndman & Athanasopoulos — Time series cross-validation](https://otexts.com/fpp3/tscv.html)
