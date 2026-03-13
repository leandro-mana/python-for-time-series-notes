# Chapter 03: Time Series Visualization

Specialised visualisation techniques that reveal the structure of time series data. These go
beyond basic line plots to expose seasonal patterns, autocorrelation, and relationships between
lagged observations — the essential "preliminary analysis" step before any modelling.

## Notebooks

| # | Notebook | Topics |
|---|----------|--------|
| 1 | `01_time_and_seasonal_plots.ipynb` | Time plots, seasonal plots (data overlaid by season), seasonal subseries plots, matplotlib date formatting (locators, formatters), multiple seasonal periods |
| 2 | `02_lag_and_autocorrelation_plots.ipynb` | Lag plots (scatterplots of $y_t$ vs $y_{t-k}$), autocorrelation function (ACF), interpreting ACF for trend and seasonality, white noise, significance bounds |
| 3 | `03_advanced_visualisation.ipynb` | Scatterplots between time series, pairwise relationships, heatmaps of seasonal patterns, custom matplotlib styling for publication-quality time series figures |

## Key Concepts

- **"Always start by graphing the data"** — the first and most important step in any forecasting task (FPP3)
- **Seasonal plots** overlay data by season (e.g., each year as a separate line by month) to make seasonal patterns and year-to-year changes visible
- **Seasonal subseries plots** show the values for each season as a separate mini time series, with horizontal lines marking means
- **Lag plots** are scatterplots of $y_t$ vs $y_{t-k}$ — strong linear relationships at lag $k$ indicate autocorrelation at that lag
- The **autocorrelation function (ACF)** measures the linear relationship between $y_t$ and $y_{t-k}$ for each lag $k$ — it is the single most important diagnostic plot in time series analysis
- **White noise** has an ACF where all autocorrelations fall within the significance bounds $\pm 1.96 / \sqrt{T}$

## References

- [FPP3 Chapter 2: Time Series Graphics](https://otexts.com/fpp3/graphics.html) — Hyndman & Athanasopoulos
- [Portilla TSA Section 04: Visualizing Time Series Data](https://www.udemy.com/user/joseportilla/) — matplotlib date formatting
