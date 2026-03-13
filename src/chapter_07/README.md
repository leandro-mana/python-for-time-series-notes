# Chapter 07: Exponential Smoothing

The exponential smoothing family is the workhorse of time series forecasting.  Starting
from Simple Exponential Smoothing (a weighted average that gives more weight to recent
observations), the chapter builds through Holt's linear trend method and Holt-Winters
seasonal method, culminating in the full ETS (Error, Trend, Seasonal) state-space
framework that encompasses all 15 usable exponential smoothing variants.

## Notebooks

| # | Notebook | Topics |
|---|----------|--------|
| 1 | `01_simple_exponential_smoothing.ipynb` | SES weighted-average form, component form (level equation), flat forecast function, alpha parameter interpretation, optimization via SSE, statsmodels `SimpleExpSmoothing`, comparison to naive/mean benchmarks |
| 2 | `02_holts_method.ipynb` | Holt's linear trend method, two-parameter (alpha, beta*) component form, damped trend (Gardner & McKenzie 1985, phi parameter), statsmodels `Holt`, linear vs damped trend comparison |
| 3 | `03_holt_winters.ipynb` | Triple exponential smoothing, additive vs multiplicative seasonality, three-parameter (alpha, beta*, gamma) component form, damped variants, statsmodels `ExponentialSmoothing`, prediction intervals |
| 4 | `04_ets_framework.ipynb` | ETS = Error, Trend, Seasonal state-space formulation, full taxonomy (15 usable models), additive vs multiplicative errors, model selection via AIC/BIC, statsmodels `ETSModel`, automatic model selection |

## Key Concepts

- **Exponential smoothing** produces forecasts as weighted averages of past observations, with exponentially decaying weights — recent data matters more than distant data
- The **smoothing parameter alpha** controls how quickly the method adapts: alpha near 0 means slow learning (long memory), alpha near 1 means fast learning (short memory)
- **Simple Exponential Smoothing** (SES) is suitable for data with no trend and no seasonality — it produces flat forecasts equal to the last estimated level
- **Holt's method** extends SES by adding a trend component with its own smoothing parameter beta* — it produces linear (sloped) forecasts
- The **damped trend** modification (phi parameter) causes the trend to flatten over time, preventing the unrealistic indefinite extrapolation of linear trends — empirically, damped trends often outperform linear trends
- **Holt-Winters** adds a seasonal component with smoothing parameter gamma, available in additive (constant seasonal amplitude) and multiplicative (proportional seasonal amplitude) forms
- The **ETS framework** adds an error term (additive or multiplicative) to create a full state-space model: E={A,M} x T={N,A,Ad} x S={N,A,M} = 18 combinations, of which 15 are numerically stable
- **Model selection** within ETS uses information criteria (AIC, AICc, BIC) — the model with the lowest AIC is preferred as it balances fit and parsimony
- All implementations use `initialization_method='estimated'` (statsmodels 0.14+), which estimates initial states via maximum likelihood rather than using ad-hoc heuristics

## References

- [FPP3 Chapter 8: Exponential Smoothing](https://otexts.com/fpp3/expsmooth.html) — Hyndman & Athanasopoulos
- [Portilla TSA Section 05: Exponential Smoothing](https://www.udemy.com/user/joseportilla/) — Practical implementation with statsmodels
- [statsmodels: Exponential Smoothing](https://www.statsmodels.org/stable/tsa.html#exponential-smoothing) — SimpleExpSmoothing, Holt, ExponentialSmoothing, ETSModel
- [Gardner, E.S. (1985). Exponential smoothing: The state of the art](https://doi.org/10.1016/0169-2070(85)90012-5) — Foundational review
- [Hyndman, R.J., et al. (2002). A state space framework for automatic forecasting](https://doi.org/10.1016/S0169-2070(01)00110-8) — The ETS framework
- [Hyndman, R.J., et al. (2008). Forecasting with Exponential Smoothing: The State Space Approach](https://doi.org/10.1007/978-3-540-71918-2) — Comprehensive treatment
