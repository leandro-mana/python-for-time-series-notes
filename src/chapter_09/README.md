# Chapter 09: Dynamic Regression (SARIMAX)

Standard regression assumes independent errors, but time series residuals are
almost always autocorrelated.  **Dynamic regression** solves this by modelling
the errors with an ARIMA process while keeping external predictors in the mean
equation.  In statsmodels this is the SARIMAX class -- the "X" stands for
eXogenous variables.

This chapter covers the theory from FPP3 Chapter 10 and the practical
holiday-effects example from Portilla Section 06-07.

## Notebooks

| # | Notebook | Topics |
|---|----------|--------|
| 1 | `01_regression_with_arima_errors.ipynb` | Why regression errors are autocorrelated, regression with ARIMA errors, the SARIMAX API, simple macro-economic example |
| 2 | `02_sarimax_exogenous_variables.ipynb` | Restaurant visitors + holiday effects, SARIMA vs SARIMAX comparison, feature engineering for exogenous variables, practical guidelines |
| 3 | `03_dynamic_harmonic_regression.ipynb` | Fourier terms for complex seasonality, choosing K, handling long seasonal periods, SARIMAX with Fourier features |

## Key Concepts

- **Regression with ARIMA errors** models the target as a linear function of predictors plus an error term that follows an ARIMA process: $y_t = \beta_0 + \beta_1 x_{1,t} + \cdots + \beta_k x_{k,t} + \eta_t$ where $\eta_t \sim \text{ARIMA}(p,d,q)$
- The **"X" in SARIMAX** adds exogenous regressors to a SARIMA model -- you must supply exog values for both fitting and forecasting
- **Exogenous variables must be known** for the entire forecast horizon (e.g., holidays, calendar effects, Fourier terms) -- you cannot use lagged values of the target as exogenous
- **Holiday / event dummies** are the most common exogenous variables and can substantially improve forecasts for series affected by holidays
- **Fourier terms** ($\sin$ and $\cos$ pairs) provide a flexible way to model complex or long-period seasonality as exogenous regressors
- The number of Fourier pairs **K** controls smoothness: K=1 gives a simple sine wave, K=m/2 reproduces any seasonal pattern exactly
- Dynamic harmonic regression is especially useful when the seasonal period is too long for seasonal ARIMA (e.g., daily data with m=365)

## References

- [FPP3 Chapter 10: Dynamic Regression Models](https://otexts.com/fpp3/dynamic.html) -- Hyndman & Athanasopoulos
- [Portilla TSA Section 06-07: SARIMAX](https://www.udemy.com/user/joseportilla/) -- SARIMAX with holiday exogenous variables
- [statsmodels: SARIMAX](https://www.statsmodels.org/stable/generated/statsmodels.tsa.statespace.sarimax.SARIMAX.html)
- [Wikipedia: Fourier Series](https://en.wikipedia.org/wiki/Fourier_series)
