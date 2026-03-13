# Chapter 01: Getting Started with Time Series

An introduction to time series analysis — what time series data is, why it requires specialised
methods, and the foundational Python tools for working with dates and times. We explore real-world
datasets to build intuition for trend, seasonality, and noise before diving into formal methods
in later chapters.

## Notebooks

| # | Notebook | Topics |
|---|----------|--------|
| 1 | `01_what_is_time_series.ipynb` | What is a time series, types of time series data, components (trend, seasonality, cyclicity, noise), predictability factors, qualitative vs quantitative forecasting, the 5-step forecasting workflow, the statistical perspective |
| 2 | `02_python_datetime.ipynb` | Python `datetime` module (`date`, `time`, `datetime`, `timedelta`), formatting with `strftime`/`strptime`, timezone handling with `zoneinfo`, NumPy `datetime64` and `timedelta64`, Pandas `Timestamp` and `DatetimeIndex` |
| 3 | `03_time_series_data.ipynb` | Loading time series from CSV, setting a `DatetimeIndex`, frequency and `pd.infer_freq`, exploring real datasets (airline passengers, CO2, energy production), visual identification of trend, seasonality, and noise |

## Key Concepts

- A **time series** is a sequence of observations recorded at regular time intervals
- Time series analysis requires specialised methods because observations are **not independent** — nearby values are correlated (autocorrelation)
- The three visible components of a time series are **trend** (long-term direction), **seasonality** (regular repeating patterns), and **noise** (random variation)
- **Cyclicity** differs from seasonality: cycles have variable, longer periods not tied to calendar time
- Forecasting accuracy depends on: understanding of contributing factors, data availability, similarity of future to past, and whether forecasts affect outcomes
- The **5-step forecasting workflow**: define the problem, gather information, preliminary analysis (always graph first!), choose and fit models, evaluate
- A forecast is not a single number but a **distribution** — point forecasts should always be accompanied by prediction intervals

## References

- [FPP3 Chapter 1: Getting Started](https://otexts.com/fpp3/intro.html) — Hyndman & Athanasopoulos
- [Portilla TSA Section 00: Intro to Time Series](https://www.udemy.com/user/joseportilla/) — datetime basics and first time series plots
