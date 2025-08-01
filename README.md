# GARCH Algorithm Testing

This repository is dedicated to testing and implementing the Generalized Autoregressive Conditional Heteroskedasticity (GARCH) algorithm.

## About the GARCH Algorithm

The GARCH model is a statistical model used in econometrics and financial analysis to model and forecast volatility in financial time series.

## Project Goals

- Implement the GARCH(p, q) model.
- Test the algorithm with various financial datasets.
- Compare the performance of the GARCH model with other volatility models.

### GARCH Model Performance Summary
Below is a summary of the results obtained with basic p=1, q=1 parameter values

| Model                                    | MSE        | MAE        | R²          |
| :--------------------------------------- | :--------- | :--------- | :---------- |
| **GJR-GARCH (Normal)**              | **0.900774** | **0.641340** | **0.088907** |
| GJR-GARCH (Student's t-dist)             | 0.916880   | 0.650123   | 0.072617    |
| EGARCH (Normal)                          | 0.929720   | 0.646335   | 0.059629    |
| Standard GARCH                           | 1.008652   | 0.670256   | -0.020206   |
| APARCH                                   | 1.015525   | 0.671701   | -0.027159   |

## Getting Started

Each notebook can be run independently. Each notebook will pull the data from Yahoo Finance a perform the analysis of it respective model.
