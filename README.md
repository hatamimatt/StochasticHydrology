# Streamflow Fourier

A time series analysis project that downloads and analyzes USGS streamflow data using ARIMA (AutoRegressive Integrated Moving Average) modeling to forecast river discharge patterns.

## Overview

This project demonstrates time series analysis techniques applied to hydrological data from the US Geological Survey (USGS). It downloads daily streamflow data for the Congaree River at Columbia, SC, processes it into monthly averages, and applies ARIMA modeling to forecast future discharge patterns.

## Features

- **Data Download**: Automated download of USGS streamflow data via their REST API
- **Data Processing**: Conversion from daily to monthly time series with proper handling of missing values
- **Time Series Analysis**: 
  - Stationarity testing through differencing
  - ACF (Autocorrelation Function) and PACF (Partial Autocorrelation Function) analysis
  - ARIMA model fitting and diagnostics
- **Forecasting**: 12-month ahead forecasts with confidence intervals
- **Visualization**: Comprehensive plotting of raw data, differenced series, residuals, and forecasts

## Data Source

- **Station**: Congaree River at Columbia, SC (USGS Station ID: 02169500)
- **Parameter**: Daily discharge (parameter code: 00060)
- **Time Period**: January 2004 to July 2025
- **Data Source**: USGS National Water Information System (NWIS)

## Requirements

```bash
pip install pandas numpy matplotlib statsmodels urllib3
```

## Usage

1. **Open the Jupyter notebook**:
   ```bash
   jupyter notebook arima.ipynb
   ```

2. **Run all cells** to execute the complete analysis pipeline:
   - Data download and preprocessing
   - Time series visualization
   - ARIMA model fitting
   - Forecast generation

## Analysis Pipeline

### 1. Data Acquisition
- Downloads daily discharge data from USGS NWIS API
- Filters and cleans the raw data
- Converts to pandas DataFrame with proper datetime indexing

### 2. Data Preprocessing
- Resamples daily data to monthly averages
- Handles missing values and data quality issues
- Creates differenced series for stationarity

### 3. Model Development
- Fits ARIMA(1,1,1) model to the monthly discharge series
- Performs diagnostic tests on residuals
- Validates model assumptions

### 4. Forecasting
- Generates 12-month ahead forecasts
- Provides confidence intervals for predictions
- Visualizes historical data with forecast overlay

## Model Results

The ARIMA(1,1,1) model shows:
- **AR(1) coefficient**: 0.6783 (significant autoregressive component)
- **MA(1) coefficient**: -1.0000 (strong moving average component)
- **Model fit**: Good with AIC of 3749.819
- **Residual diagnostics**: Generally well-behaved with some non-normality

## Key Findings

1. **Seasonality**: The Congaree River shows clear seasonal patterns in discharge
2. **Trend**: The differenced series appears stationary, suitable for ARIMA modeling
3. **Forecast Accuracy**: The model captures the general trend and seasonal patterns
4. **Uncertainty**: Confidence intervals widen over time, reflecting increasing forecast uncertainty

## Files

- `arima.ipynb`: Main Jupyter notebook containing the complete analysis
- `README.md`: This documentation file

## Dependencies

- **pandas**: Data manipulation and time series operations
- **numpy**: Numerical computations
- **matplotlib**: Plotting and visualization
- **statsmodels**: Time series analysis and ARIMA modeling
- **urllib**: HTTP requests for data download

## Future Enhancements

- Add multiple station analysis
- Implement seasonal ARIMA (SARIMA) models
- Include additional hydrological variables (temperature, precipitation)
- Create interactive dashboards
- Add model comparison and selection criteria

## License

This project is open source and available under the MIT License.

## Contributing

Contributions are welcome! Please feel free to submit issues, feature requests, or pull requests.

## Acknowledgments

- US Geological Survey for providing the streamflow data
- The statsmodels community for the excellent time series analysis tools
- The scientific Python ecosystem for the robust data analysis capabilities 