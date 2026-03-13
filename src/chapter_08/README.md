# Chapter 08: ARIMA Models

Autoregressive Integrated Moving Average (ARIMA) models are the other major family of
time series forecasting methods alongside exponential smoothing.  This chapter builds up
from the simplest AR and MA components through non-seasonal ARIMA to full seasonal ARIMA,
and concludes with a head-to-head comparison against ETS.

## Notebooks

| # | Notebook | Topics |
|---|----------|--------|
| 1 | `01_ar_models.ipynb` | AR(p) models, backshift notation, PACF for order selection, `AutoReg` API, simulating AR processes |
| 2 | `02_ma_models.ipynb` | MA(q) models, distinction from moving average smoothing, ACF for order selection, invertibility, simulation |
| 3 | `03_arima.ipynb` | ARIMA(p,d,q) — combining AR, differencing, and MA; the full modelling workflow; `ARIMA` API; `pmdarima.auto_arima`; residual diagnostics |
| 4 | `04_seasonal_arima.ipynb` | SARIMA(p,d,q)(P,D,Q)m — seasonal orders, seasonal differencing, `SARIMAX` API, complete airline passengers walkthrough |
| 5 | `05_arima_vs_ets.ipynb` | When to use ARIMA vs ETS, head-to-head comparison on multiple datasets, AIC / RMSE / MAPE, practical guidance |

## Key Concepts

- **AR(p)** models express the current value as a linear combination of its own past values plus noise — the PACF cuts off after lag p
- **MA(q)** models express the current value as a linear combination of past forecast errors — the ACF cuts off after lag q (MA is NOT moving average smoothing)
- **ARIMA(p,d,q)** adds differencing to make a non-stationary series stationary before applying ARMA — d is the number of differences required
- **Backshift notation** $B y_t = y_{t-1}$ provides a compact algebraic representation of AR, MA, and differencing operations
- **Seasonal ARIMA** adds seasonal AR, differencing, and MA terms at the seasonal lag m, written SARIMA(p,d,q)(P,D,Q)m
- **Automatic order selection** via `pmdarima.auto_arima` searches over (p,d,q) using AIC/BIC, analogous to `ets()` automatic selection
- The **ARIMA modelling workflow**: plot, test stationarity, difference, examine ACF/PACF, fit, check residuals, forecast
- ARIMA and ETS are complementary — neither dominates; in practice, try both and pick the model with better out-of-sample accuracy

## References

- [FPP3 Chapter 9: ARIMA Models](https://otexts.com/fpp3/arima.html) — Hyndman & Athanasopoulos
- [Portilla TSA Section 06: ARIMA](https://www.udemy.com/user/joseportilla/) — AR, MA, ARIMA, SARIMA with statsmodels
- [statsmodels: AutoReg](https://www.statsmodels.org/stable/generated/statsmodels.tsa.ar_model.AutoReg.html)
- [statsmodels: ARIMA (new API)](https://www.statsmodels.org/stable/generated/statsmodels.tsa.arima.model.ARIMA.html)
- [statsmodels: SARIMAX](https://www.statsmodels.org/stable/generated/statsmodels.tsa.statespace.sarimax.SARIMAX.html)
- [pmdarima: auto_arima](https://alkaline-ml.com/pmdarima/modules/generated/pmdarima.arima.auto_arima.html)
