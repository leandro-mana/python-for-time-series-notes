# Chapter 05: Time Series Features and Statistics

Statistical tools for characterising, testing, and summarising time series.  This chapter
bridges descriptive analysis (Chapters 01-04) and model building (Chapters 06+): the
diagnostics introduced here — ACF, PACF, stationarity tests, and white-noise checks — are
the primary tools used to select and validate forecasting models.

## Notebooks

| # | Notebook | Topics |
|---|----------|--------|
| 1 | `01_acf_and_pacf.ipynb` | ACF formula, manual computation, PACF and partial correlation, Yule-Walker equations, `plot_acf()` and `plot_pacf()`, ACF/PACF signature table for AR/MA/ARMA identification |
| 2 | `02_stationarity.ipynb` | Strict vs weak stationarity, visual rolling-statistics test, ADF test, KPSS test, first and seasonal differencing, over-differencing warning |
| 3 | `03_statistical_tests.ipynb` | Ljung-Box test for white noise, Granger causality test, cointegration test, interpreting p-values and null hypotheses |
| 4 | `04_time_series_features.ipynb` | Summary statistics for time series, trend and seasonal strength from STL, spectral entropy, feature extraction across multiple series |

## Key Concepts

- **Autocorrelation (ACF)** measures the linear association between $y_t$ and $y_{t-k}$ — it captures both direct and indirect dependence through intermediate lags
- **Partial autocorrelation (PACF)** isolates the direct association between $y_t$ and $y_{t-k}$ after removing the linear effect of the intervening lags $y_{t-1}, \ldots, y_{t-k+1}$
- **Stationarity** (constant mean, constant variance, autocovariance depending only on lag) is a prerequisite for most classical forecasting models — non-stationary series must be differenced first
- The **ADF test** has H0: unit root (non-stationary); the **KPSS test** has H0: stationary — using both together gives a more reliable verdict
- **Differencing** removes trend (first difference) or seasonality (seasonal difference) and is the standard way to make a series stationary
- The **Ljung-Box test** checks whether residual autocorrelations are collectively zero — a key model-adequacy diagnostic
- **Granger causality** tests whether past values of one series improve predictions of another — predictive usefulness, not true causation
- **Trend and seasonal strength** ($F_T$, $F_S$) quantify how much of the variation is attributable to each component, useful for comparing and clustering series

## References

- [FPP3 Chapter 4: Time Series Features](https://otexts.com/fpp3/features.html) — Hyndman & Athanasopoulos
- [Portilla TSA Section 06-01: ACF and PACF](https://www.udemy.com/user/joseportilla/) — Autocorrelation theory and plots
- [Portilla TSA Section 06-03: Stationarity and Differencing](https://www.udemy.com/user/joseportilla/) — ADF, KPSS, differencing
- [statsmodels: acf / pacf](https://www.statsmodels.org/stable/generated/statsmodels.tsa.stattools.acf.html)
- [statsmodels: adfuller](https://www.statsmodels.org/stable/generated/statsmodels.tsa.stattools.adfuller.html)
- [statsmodels: kpss](https://www.statsmodels.org/stable/generated/statsmodels.tsa.stattools.kpss.html)
- [statsmodels: acorr_ljungbox](https://www.statsmodels.org/stable/generated/statsmodels.stats.diagnostic.acorr_ljungbox.html)
- [statsmodels: grangercausalitytests](https://www.statsmodels.org/stable/generated/statsmodels.tsa.stattools.grangercausalitytests.html)
