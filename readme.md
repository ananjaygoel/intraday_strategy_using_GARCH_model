# GARCH Model Intraday Trading Strategy

This repository contains the code and data for an intraday trading strategy based on a GARCH model. The strategy uses daily predictions and variance from a GARCH model to generate a daily signal, which is then combined with intraday indicators (RSI and Bollinger Bands) to create an intraday trading signal.

## Repository Contents

- `GARCH_Intraday_Strategy.ipynb`: This Jupyter notebook contains the Python code for implementing the trading strategy, from data loading and preprocessing to signal generation and backtesting.
- `daily_data.csv`: This file contains the daily data used for the GARCH model and daily signal generation.
- `intraday_data.csv`: This file contains the intraday data used for generating intraday indicators and the intraday signal.

## Strategy Overview

The strategy follows these steps:

1. **Data Loading**: Loads daily and intraday price data.
2. **GARCH Model and Daily Signal**:
    - Calculates the prediction premium from the GARCH model's predictions and variance.
    - Computes the 6-month rolling standard deviation of the prediction premium.
    - Generates a daily signal based on whether the prediction premium is above or below its rolling standard deviation.
    - The daily signal is then shifted to avoid look-ahead bias.
3. **Intraday Indicators and Signal**:
    - Merges the daily signal with intraday data.
    - Calculates intraday indicators, specifically RSI and Bollinger Bands.
    - Generates an intraday signal based on the RSI and Bollinger Band values relative to the closing price.
4. **Position Entry and Hold**:
    - Determines the position entry based on a combination of the daily and intraday signals.
    - Holds the position until the end of the day.
5. **Strategy Returns**:
    - Calculates the returns for each intraday period based on the position.
    - Aggregates intraday returns to get daily returns.
    - Computes the cumulative returns of the strategy.

## Requirements

To run the notebook and reproduce the results, you will need the following libraries:

- pandas
- numpy
- matplotlib
- pandas_ta

You can install these libraries using pip:
