# Chapter 10: Multivariate Models (VAR/VARMA)

When multiple time series are interrelated -- money supply and consumer spending,
or river discharge levels at connected stations -- forecasting them in isolation
ignores useful cross-series information.  **Vector Autoregression (VAR)** and
its extensions model several time series jointly, allowing each variable's
forecast to depend on the history of *all* variables in the system.

This chapter covers VAR, VARMA, and VECM models, along with the diagnostic
tools (Granger causality, impulse response functions) that give these models
their interpretive power.

## Notebooks

| # | Notebook | Topics |
|---|----------|--------|
| 1 | `01_var_models.ipynb` | VAR(p) theory and matrix notation, lag order selection (AIC/BIC), Granger causality, impulse response functions, fitting with `statsmodels.tsa.api.VAR`, inverse-differencing forecasts |
| 2 | `02_varma_and_vecm.ipynb` | VARMA(p,q) via `VARMAX`, identifiability issues, VECM for cointegrated series, Johansen cointegration test, when each model type is appropriate |
| 3 | `03_practical_multivariate_forecasting.ipynb` | End-to-end multivariate forecasting pipeline, comparison with univariate ARIMA, honest assessment of when VAR adds value, practical guidelines |

## Key Concepts

- **VAR(p)** models each variable as a linear function of *p* lags of every variable in the system -- the multivariate generalization of AR(p)
- **Matrix notation**: $\mathbf{y}_t = \mathbf{c} + \mathbf{\Phi}_1 \mathbf{y}_{t-1} + \cdots + \mathbf{\Phi}_p \mathbf{y}_{t-p} + \boldsymbol{\varepsilon}_t$ where each $\mathbf{\Phi}_i$ is a $K \times K$ coefficient matrix
- **Stationarity requirement**: all series entering a VAR must be stationary; difference first if unit roots are present
- **Lag order selection**: fit VAR for $p = 1, 2, \ldots$ and choose the order that minimizes AIC or BIC
- **Granger causality**: variable $x$ Granger-causes $y$ if past values of $x$ help predict $y$ beyond what $y$'s own past provides
- **Impulse response functions (IRFs)**: trace the dynamic effect of a one-unit shock to one variable on all variables over time
- **VARMA(p,q)** adds MA terms to VAR -- more flexible but harder to estimate and identify; pure VAR is more common in practice
- **VECM**: for series that are non-stationary but *cointegrated* (they share a common stochastic trend), VECM models the short-run dynamics while respecting the long-run equilibrium relationship
- **Honest assessment**: VAR does not always outperform univariate models; it adds value primarily when strong cross-series relationships exist

## References

- [FPP3 Chapter 12.3: VAR Models](https://otexts.com/fpp3/VAR.html) -- Hyndman & Athanasopoulos
- [Portilla TSA Sections 06-08/09: VAR Models](https://www.udemy.com/user/joseportilla/) -- VAR with statsmodels
- [statsmodels: VAR](https://www.statsmodels.org/stable/vector_ar.html)
- [statsmodels: VARMAX](https://www.statsmodels.org/stable/generated/statsmodels.tsa.statespace.varmax.VARMAX.html)
- [statsmodels: VECM](https://www.statsmodels.org/stable/generated/statsmodels.tsa.vector_ar.vecm.VECM.html)
- [Lutkepohl, H. (2005). *New Introduction to Multiple Time Series Analysis*](https://link.springer.com/book/10.1007/978-3-540-27752-1) -- the definitive reference
