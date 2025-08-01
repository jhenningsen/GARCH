# GARCH Algorithm Testing

This repository is dedicated to testing and implementing the Generalized Autoregressive Conditional Heteroskedasticity (GARCH) algorithm.

## About the GARCH Algorithm

The **Generalized Autoregressive Conditional Heteroskedasticity (GARCH)** model is a statistical model used to forecast the volatility of financial time series data, such as stock returns. It is particularly useful because it captures two key characteristics of this data:

1.  **Volatility Clustering:** Periods of high volatility tend to be followed by periods of high volatility, and periods of low volatility tend to be followed by periods of low volatility.
2.  **Mean Reversion:** Volatility is not constant and tends to revert to its long-term average over time.

The GARCH model forecasts future volatility as a weighted average of the long-term average volatility, the volatility from the previous period's forecast, and the square of the previous period's return (a proxy for the last shock to the system).

Here is a summary of the performance of the various GARCH models were evaluated:

#### 1. Standard GARCH
* **Description:** The base model that assumes positive and negative shocks have the same effect on future volatility.
* **Performance:** This model was the worst performer in the backtest. Its forecast was less accurate than simply using the average historical volatility, as indicated by a negative R-squared value. This confirmed that a more sophisticated model was needed for this data.

#### 2. EGARCH (Exponential GARCH)
* **Description:** An asymmetric model that captures the "leverage effect," where a negative return has a greater impact on future volatility than a positive return of the same magnitude.
* **Performance:** This model was a significant improvement over the standard GARCH model. It had a lower forecast error and a positive R-squared, showing that it had real predictive power.

#### 3. GJR-GARCH (Glosten-Jagannathan-Runkle GARCH)
* **Description:** An asymmetric model that also captures the leverage effect by adding a specific term for negative shocks. It is often a strong competitor to the EGARCH model.
* **Performance:** This model was the **best performer overall**. It achieved the lowest forecast error (MSE and MAE) and the highest R-squared value, demonstrating superior predictive accuracy compared to all other models tested.

#### 4. APARCH (Asymmetric Power GARCH)
* **Description:** A highly flexible and generalized model that captures both asymmetry and the power of the volatility process.
* **Performance:** Despite its added complexity, the APARCH model was the worst performer in the backtest. This highlights that a more complex model is not always a better forecaster, and sometimes a simpler model like GJR-GARCH finds a more robust fit for out-of-sample data.


## Project Goals

- Implement the GARCH(p, q) model.
- Test the algorithm with the SPY financial datasets.
- Compare the performance various GARCH models.

## GARCH Model Performance Summary
Below is a summary of the results obtained with basic p=1, q=1 parameter values

| Model                                    | MSE        | MAE        | R²          |
| :--------------------------------------- | :--------- | :--------- | :---------- |
| **GJR-GARCH (Normal)**              | **0.900774** | **0.641340** | **0.088907** |
| GJR-GARCH (Student's t-dist)             | 0.916880   | 0.650123   | 0.072617    |
| EGARCH (Normal)                          | 0.929720   | 0.646335   | 0.059629    |
| Standard GARCH                           | 1.008652   | 0.670256   | -0.020206   |
| APARCH                                   | 1.015525   | 0.671701   | -0.027159   |

<br>

<img width="1291" height="677" alt="GJR-Prediction Chart" src="https://github.com/user-attachments/assets/73aca6cb-2c33-4024-a6bc-28b18657d365" />

## Getting Started

Each notebook can be run independently. Google Colab was used for the creation of the notebooks and in the recommended environment for executing them. Each notebook will pull the data from Yahoo Finance a perform the analysis of it respective model.
