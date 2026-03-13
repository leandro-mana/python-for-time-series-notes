# Chapter 11: Prophet

Meta's **Prophet** library takes a fundamentally different approach to time
series forecasting.  Instead of the Box-Jenkins methodology (identify orders,
difference, fit ARIMA), Prophet decomposes a time series into interpretable
components -- trend, seasonality, and holidays -- and fits each one with
flexible, well-understood building blocks: piecewise linear or logistic
growth for the trend, Fourier series for seasonality, and indicator variables
for holiday effects.

The result is a forecasting system that produces good forecasts out of the
box for the kind of time series most businesses encounter: daily or weekly
data with multiple seasonal patterns, holiday effects, and occasional trend
changes.

## Notebooks

| # | Notebook | Topics |
|---|----------|--------|
| 1 | `01_prophet_fundamentals.ipynb` | The decomposable model $y(t) = g(t) + s(t) + h(t) + \varepsilon_t$, piecewise linear trend, Fourier seasonality, data format requirements, basic fitting workflow, component plots, airline passengers and alcohol sales examples |
| 2 | `02_prophet_tuning.ipynb` | Changepoint detection and tuning (`changepoint_prior_scale`, `n_changepoints`, `changepoint_range`), additive vs multiplicative seasonality, custom seasonality, holiday effects and country holidays, logistic growth with cap/floor |
| 3 | `03_prophet_evaluation.ipynb` | Built-in cross-validation (`cross_validation`, `performance_metrics`), diagnostic metrics (MAE, RMSE, MAPE, coverage), cross-validation metric plots, Prophet vs SARIMA head-to-head comparison, when to use Prophet vs classical methods, limitations |

## Key Concepts

- **Decomposable model**: $y(t) = g(t) + s(t) + h(t) + \varepsilon_t$ where each component is modeled separately and combined additively (or multiplicatively for seasonality)
- **Piecewise linear trend**: the growth rate $k$ can change at automatically detected *changepoints*; the `changepoint_prior_scale` parameter controls how flexible the trend is
- **Logistic growth**: for series with a natural saturation point (market size, resource capacity), Prophet can fit a logistic growth curve with user-specified cap and floor
- **Fourier seasonality**: periodic patterns are modeled as a truncated Fourier series $s(t) = \sum_{n=1}^{N}(a_n \cos \frac{2\pi nt}{P} + b_n \sin \frac{2\pi nt}{P})$, where $P$ is the period and $N$ controls smoothness
- **Holiday effects**: user-specified events that create predictable disruptions, with configurable windows before and after each holiday
- **Cross-validation**: Prophet provides `cross_validation()` for time-series-aware backtesting with configurable initial training period, step size, and forecast horizon
- **Data format**: Prophet requires a DataFrame with columns `ds` (datestamp) and `y` (value) -- no other format is accepted

## References

- [FPP3 Chapter 12.2: Prophet](https://otexts.com/fpp3/prophet.html) -- Hyndman & Athanasopoulos
- [Portilla TSA Section 08: Prophet](https://www.udemy.com/user/joseportilla/) -- Prophet with fbprophet (now `prophet`)
- [Prophet Documentation](https://facebook.github.io/prophet/) -- official docs
- [Taylor & Letham (2018). *Forecasting at Scale*](https://peerj.com/preprints/3190/) -- the original Prophet paper
- [Prophet GitHub Repository](https://github.com/facebook/prophet)
