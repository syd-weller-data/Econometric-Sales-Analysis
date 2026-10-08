# Econometric-Sales-Analysis
Analysis and forecasting of synthetic sales data using time series econometrics and Stata

Tools: Stata

##Overview 

Based on synthetically created data in Excel, I was tasked with creating a five-page report detailing the performance of sales from a fake company 'Weller Industries', as well as forecasting sales performance numbers for an addition quarter and year. 

##Data
The raw data was created in Excel but translated into a .dta file for use in Stata. The original dataset contained the date, CPI, interest rates, production rates, and recorded sales, with 500 observations of monthly data between 1968 and 2010. Based on my analysis of the data below, I chose to only use the date and recorded sales based on potential multicollinearity and economic intuition. I used CPI to transform the sales data from nominal to real. 

##Analysis
I destringed and cleaned the data by transforming the labelling so the date matched the frequency and months were properly labelled. I then ran analysis in the following order:
- I plotted the raw data and found a strong exponential trend, so I logged and differenced the data so it would appear stationary as well as pass the checks for valid statistical stationarity.
- I set aside the last 100 observations to use as a test set for estimating a proper model. 
- Once the data appeared stationary, I checked its stationarity by running an Augmented Dickey Fuller test with 12 lags.
- I ran a Phillips-Perron test which checks for a similar pattern as the ADF for an additional layer of robustness.
- I ran a KPSS test which found the potential for non-stationarity, however I ruled this out due to the results of the ADF and Phillips-Perron test, as well as the fact that the data appeared highly auto-correlative which may have impacted the results of the KPSS.
- I plotted and analyzed the auto-correlation and partial auto-correlation functions for the transformed data.
- I tested the AIC and BIC of the data and chose two potential ARMA models to use based on the results.
- I tested the residuals of both models to ensure 'white noise'.
- Using RMSE out-of-sample results, I compared the performance of the two models to determine which one estimated the data better; I ultimately determined the ARMA(3,3) model to provide the most accurate estimation results.
- Using the selected model, I predicted 100 data points and compared them to the actual 100 data points I had removed earlier.

##Addition discussion
Following my forecast comparison to the real sales figures, I discussed the potential relevance of the Lucas Critique and why I did not believe it applied to the synthetic Weller Industries data. I then summarized my findings and reaffirmed my choice of an ARMA(3,3) model for the provided synthetic data. 

##Figures
Raw Data before transformation using CPI:
<img width="524" height="400" alt="Screenshot 2026-10-08 at 16 50 25" src="https://github.com/user-attachments/assets/81ad2d4d-8e62-4770-8bca-72d2407a1301" />

Transformed, visually stationary data:
<img width="524" height="346" alt="Screenshot 2026-10-08 at 16 51 17" src="https://github.com/user-attachments/assets/2b838b72-9a72-49e0-870e-bc9245001daa" />

ACF and PACF plots of transformed data:
<img width="961" height="346" alt="Screenshot 2026-10-08 at 16 51 41" src="https://github.com/user-attachments/assets/b962da0a-4aa0-497a-8cbb-a3e349649dc7" />

Forecasted Sales Growth compared to actual data:
<img width="982" height="371" alt="Screenshot 2026-10-08 at 16 52 08" src="https://github.com/user-attachments/assets/89a35bdc-5ac0-4143-ae3e-9baa51f46dd7" />


##Skills Demonstrated
- Stata efficiency
- Econometric and Sales Data Analysis
- Data Format Transformation
- Data Cleaning
- Data Visualization



