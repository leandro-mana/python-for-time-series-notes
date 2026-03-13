# Chapter 04: Time Series Decomposition

Breaking a time series into its constituent components — trend-cycle, seasonal, and remainder.
Decomposition reveals the underlying structure of data, informs model selection, and can improve
forecast accuracy when combined with separate component forecasting.

## Notebooks

| # | Notebook | Topics |
|---|----------|--------|
| 1 | `01_transformations.ipynb` | Calendar, population, and inflation adjustments, mathematical transformations (log, power), Box-Cox transformation and lambda selection, variance stabilisation |
| 2 | `02_moving_averages.ipynb` | Simple moving averages, weighted moving averages, the $2 \times m$ moving average for even-order seasonality, moving averages as trend estimators |
| 3 | `03_classical_decomposition.ipynb` | Additive decomposition ($y_t = T_t + S_t + R_t$), multiplicative decomposition ($y_t = T_t \times S_t \times R_t$), step-by-step algorithm, `seasonal_decompose()` in statsmodels, limitations |
| 4 | `04_stl_decomposition.ipynb` | STL (Seasonal and Trend decomposition using LOESS), advantages over classical, controlling seasonal and trend smoothness, robust decomposition for outliers, `STL` in statsmodels |

## Key Concepts

- **Additive decomposition** assumes components add: $y_t = T_t + S_t + R_t$ — appropriate when seasonal variation is roughly constant
- **Multiplicative decomposition** assumes components multiply: $y_t = T_t \times S_t \times R_t$ — appropriate when seasonal variation grows with the level
- A **log transform** converts multiplicative to additive: $\log(y_t) = \log(T_t) + \log(S_t) + \log(R_t)$
- The **Box-Cox transformation** is a family of power transforms parameterised by $\lambda$ that stabilises variance
- **Classical decomposition** uses moving averages to estimate the trend, then averages detrended values for the seasonal component — simple but limited (fixed seasonality, not robust to outliers, missing edge values)
- **STL decomposition** uses LOESS (locally estimated scatterplot smoothing) — it allows the seasonal component to change over time, is robust to outliers, and handles any type of seasonality
- Decomposition is not just descriptive — it can be used for **forecasting** by forecasting each component separately and recombining

## References

- [FPP3 Chapter 3: Time Series Decomposition](https://otexts.com/fpp3/decomposition.html) — Hyndman & Athanasopoulos
- [Portilla TSA Section 05: Time Series Analysis with Statsmodels](https://www.udemy.com/user/joseportilla/) — ETS decomposition
- [statsmodels: seasonal_decompose](https://www.statsmodels.org/stable/generated/statsmodels.tsa.seasonal.seasonal_decompose.html)
- [statsmodels: STL](https://www.statsmodels.org/stable/generated/statsmodels.tsa.seasonal.STL.html)
