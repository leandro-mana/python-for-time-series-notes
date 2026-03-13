# Python for Time Series Notes

![Python](https://img.shields.io/badge/Python-3.12+-blue?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-F37626?logo=jupyter&logoColor=white)
![statsmodels](https://img.shields.io/badge/statsmodels-0.14+-4051B5)
![Notebooks](https://img.shields.io/badge/Notebooks-~50-green)
![Chapters](https://img.shields.io/badge/Chapters-14-orange)
![License](https://img.shields.io/badge/License-MIT-yellow)

Study notes and interactive Jupyter notebooks for Time Series Analysis and Forecasting — from
fundamentals through ARIMA, Exponential Smoothing, Prophet, Deep Learning, and modern forecasting
frameworks. All content is delivered through executable Jupyter notebooks designed for self-paced
learning.

> Part of the **Python Learning Series**:
> [Data Science](https://github.com/leandro-mana/python-for-data-science-notes) ·
> **Time Series** ·
> Deep Learning (planned) ·
> NLP (planned)

## Requirements

- [Python 3.12+](https://www.python.org/downloads/)
- [Poetry](https://python-poetry.org/docs/#installation)

## Quick Start

```bash
# 1. Install dependencies
make install

# 2. Open notebooks for a chapter
make jupyter CH=01
```

## Project Structure

```text
python-for-time-series-notes/
├── src/
│   ├── data/                # Shared datasets (CSV)
│   ├── chapter_01/          # Getting Started with Time Series
│   ├── chapter_02/          # Time Series with Pandas
│   ├── chapter_03/          # Time Series Visualization
│   ├── chapter_04/          # Time Series Decomposition
│   ├── chapter_05/          # Time Series Features & Statistics
│   ├── chapter_06/          # The Forecaster's Toolbox
│   ├── chapter_07/          # Exponential Smoothing
│   ├── chapter_08/          # ARIMA Models
│   ├── chapter_09/          # Dynamic Regression (SARIMAX)
│   ├── chapter_10/          # Multivariate Models (VAR/VARMA)
│   ├── chapter_11/          # Prophet
│   ├── chapter_12/          # Deep Learning for Time Series
│   ├── chapter_13/          # Modern Forecasting Frameworks
│   └── chapter_14/          # Capstone Project
├── tests/                   # Pytest test suite
├── docs/                    # Reference books (gitignored)
├── Makefile                 # Automation commands
└── pyproject.toml           # Poetry configuration
```

## Chapters

### Part I: Time Series Fundamentals

| Chapter | Notebooks | Topics |
| --- | --- | --- |
| **01 - Getting Started** | 3 | What is a time series, types of data, Python datetime, components (trend, seasonality, noise), the forecasting workflow |
| **02 - Time Series with Pandas** | 5 | DatetimeIndex, frequency and periods, resampling, time shifting, rolling and expanding windows, missing data (ffill, bfill, interpolate) |
| **03 - Visualization** | 3 | Time plots, seasonal plots, subseries plots, lag plots, ACF plots, matplotlib date formatting |
| **04 - Decomposition** | 4 | Transformations (Box-Cox, log), moving averages, classical decomposition, STL decomposition, additive vs multiplicative |
| **05 - Features & Statistics** | 4 | Summary statistics, ACF and PACF theory, stationarity (ADF, KPSS tests), differencing, Granger causality, white noise |

### Part II: Statistical Forecasting

| Chapter | Notebooks | Topics |
| --- | --- | --- |
| **06 - The Forecaster's Toolbox** | 4 | Simple methods (naive, drift, mean, seasonal naive), residual diagnostics, prediction intervals, evaluation metrics (MAE, RMSE, MAPE), time series cross-validation |
| **07 - Exponential Smoothing** | 4 | SES, Holt's linear trend, Holt-Winters, ETS state-space taxonomy, damped trends, model selection (AIC/BIC) |
| **08 - ARIMA Models** | 5 | Stationarity and differencing, backshift notation, AR, MA, ARIMA, seasonal ARIMA, auto_arima, ARIMA vs ETS |
| **09 - Dynamic Regression** | 3 | Regression with ARIMA errors, exogenous variables (SARIMAX), harmonic regression, lagged predictors |
| **10 - Multivariate Models** | 3 | VAR, VARMA, Granger causality for variable selection, impulse response functions, cointegration |

### Part III: Modern Forecasting

| Chapter | Notebooks | Topics |
| --- | --- | --- |
| **11 - Prophet** | 3 | Model internals (piecewise trend, Fourier seasonality), changepoints, holidays, cross-validation, evaluation |
| **12 - Deep Learning** | 4 | RNN/LSTM architecture and gates, GRU, sequence-to-sequence, Temporal Fusion Transformer, N-BEATS overview |
| **13 - Modern Frameworks** | 3 | sktime unified API, Nixtla statsforecast/mlforecast, model comparison, forecast combinations |
| **14 - Capstone Project** | 2 | End-to-end forecasting: EDA, decomposition, multiple models, evaluation, model selection |

## Running Notebooks

```bash
# Open a specific chapter in Jupyter Lab
make jupyter CH=08

# List all chapters
make list-chapters

# List notebooks in a chapter
make list-notebooks CH=07
```

## Code Quality

```bash
make lint           # Ruff linter
make format         # Auto-format
make type-check     # mypy
make check          # All checks
```

## Development

See [CONTRIBUTING.md](CONTRIBUTING.md) for workflow, commit conventions, and code style guidelines.

## References

- [Jose Portilla's Python for Time Series Data Analysis](https://www.udemy.com/user/joseportilla/) (Udemy) — practical exercises and datasets
- [Forecasting: Principles and Practice, 3rd Edition](https://otexts.com/fpp3/) — Rob J Hyndman & George Athanasopoulos — theoretical foundation
- [statsmodels Documentation](https://www.statsmodels.org/stable/)
- [sktime Documentation](https://www.sktime.net/en/stable/)
- [Nixtla statsforecast Documentation](https://nixtlaverse.nixtla.io/statsforecast/)
- [Prophet Documentation](https://facebook.github.io/prophet/)
- [pmdarima Documentation](https://alkaline-ml.com/pmdarima/)
- [Keras 3 Documentation](https://keras.io/)

## Author

[Leandro Mana](https://www.linkedin.com/in/leandro-mana/)

## License

MIT
