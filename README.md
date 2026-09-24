# Close Stock Price Volatility Prediction: Samsung Electronics Co., Ltd.

## 1. The Problem
Stock market volatility is a key metric for measuring the risk level of an investment asset; the higher the volatility, the greater the likelihood of extreme price fluctuations. The main challenge in modeling financial data is heteroskedasticity, where the variance of volatility is not constant over time. This project aims to build an accurate investment risk prediction model for Samsung Electronics stock using 23 years of historical data.

## 2. My Approach
To address data non-stationarity and heteroskedasticity effects, I built a time series analysis pipeline with the following steps:

* **Data Preparation & Stationarity:** Utilized the closing price data of Samsung stock from November 2000 to November 2023. Applied differencing and the Augmented Dickey-Fuller (ADF) Test to stationarize the data on its mean.
* **Base Modeling (ARIMA):** Conducted Box-Jenkins identification through ACF and PACF plots, and tested several tentative models. The ARIMA(2,1,1) model was selected as the best base model based on the lowest Akaike Information Criterion (AIC) value of 126860.1.
* **Volatility Modeling (ARCH):** Diagnostic testing (ARCH LM-test) proved the presence of ARCH effects on the base model's residuals. I then evaluated Autoregressive Conditional Heteroscedasticity (ARCH) modeling and selected the ARCH(7) model, which delivered the best performance with the lowest AIC of 14.5516.

## 3. Results & Impact
* The developed ARCH(7) model successfully predicted stock price volatility accurately, with the predicted values proven to fall within the confidence intervals (upper and lower bounds) of the original data.
* Based on forecasting for the next 10 days, the model detected the highest risk spike on the sixth day with a standard deviation reaching 1132.7281, providing a clear quantitative signal regarding the high investment risk during that period.

## Tech Stack
* **Language/Environment:** R (RStudio)
* **Methodologies:** Time Series Analysis (ARIMA, ARCH)
* **Statistical Diagnostic Testing:** Ljung-Box, Jarque Bera, ARCH LM-test