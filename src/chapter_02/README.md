# Chapter 02: Time Series with Pandas

The essential pandas operations for working with time series data. This chapter covers the
day-to-day tools you'll use throughout the rest of the course — from DatetimeIndex manipulation
and resampling to rolling statistics and handling missing values in temporal contexts.

## Notebooks

| # | Notebook | Topics |
|---|----------|--------|
| 1 | `01_datetime_index.ipynb` | DatetimeIndex deep dive, frequency setting (`asfreq`), slicing by date, `PeriodIndex` vs `DatetimeIndex`, multi-column datetime parsing |
| 2 | `02_resampling.ipynb` | Downsampling and upsampling with `resample()`, modern offset aliases (`'ME'`, `'QE'`, `'YE'`), OHLC resampling, custom aggregations, `asfreq()` vs `resample()` |
| 3 | `03_shifting_and_lagging.ipynb` | `shift()` for lag features, `diff()` for differencing, `pct_change()` for returns, why these operations are fundamental to time series modelling |
| 4 | `04_rolling_and_expanding.ipynb` | Rolling windows (`rolling()`), expanding windows (`expanding()`), simple moving average (SMA), rolling standard deviation, time-based windows, custom rolling functions, Bollinger Bands example |
| 5 | `05_missing_data.ipynb` | Forward fill (`ffill`), backward fill (`bfill`), interpolation (`linear`, `time`, `spline`), detecting and visualising missing data patterns, strategies for different missing data scenarios |

## Key Concepts

- **DatetimeIndex** is the backbone of pandas time series — it enables date-based slicing, resampling, and frequency-aware operations
- **Resampling** changes the frequency of your data: downsampling (monthly → yearly) requires aggregation, upsampling (monthly → daily) requires filling
- **Shifting** creates lagged versions of a series — essential for computing returns, differences, and building features for forecasting models
- **Rolling windows** compute statistics over a sliding window of fixed size — the simple moving average (SMA) is the most common, but rolling std, correlation, and custom functions are equally important
- **Missing data** in time series should almost never be dropped (it breaks the temporal structure) — instead use forward fill, backward fill, or interpolation depending on the context

## References

- [FPP3 Chapter 2.1: tsibble objects](https://otexts.com/fpp3/tsibbles.html) — Hyndman & Athanasopoulos
- [Portilla TSA Section 04: Time Series with Pandas](https://www.udemy.com/user/joseportilla/) — datetime index, resampling, shifting, rolling, exercises
- [Pandas Time Series Documentation](https://pandas.pydata.org/docs/user_guide/timeseries.html)
