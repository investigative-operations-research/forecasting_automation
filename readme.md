
* Easy to see model historical performance in a single number calculated as (prediction/actual) as a percentage which could be monthly or yearly for a quick intuitive sense. Eg. if the actual value was 100, but the model predicted 96.8 - then [1 - (96.8/100)] x 100 = -3.2% as performance metric as per above example.
* The chart showing actuals vs predictions was a simple visual way of showing how well a model captured patterns like trend and seasonality compared to actual data.
* Basic stats like time series stationarity were included in the high-level summary as a reference that users could see at a glance if they wanted it and understood it, but without being intrusive or overbearing for non-technical users when they wanted an intuitive understanding of a forecast in a spreadsheet when considering using or ignoring it in daily work.
* Full stats and time series decomposition was of course made available for those seeking such detail - mostly other data scientists for model refinements.

 
# Summary

 

The task was a portfolio of international roaming destinations for retail mobile customers that was being forecast with a combination of gut feeling and at best 60-90 day moving averages in the existing in-house demand planning software.

 

Executive management called me in to lead the data science team and turn around a forecasting project that had stalled after 18 months of research.

 

There were many consumers for these forecasts with different requirements, time frames, granularity and technical skill:

 

* Executive Leadership [1 year] Cost savings for the mobiles business under threat from global competitors and disruptive technologies like eSIM.
* Contracting Team [1 year] Seeking an edge on yearly capacity purchasing as over buying meant sunk costs, but over-use meant higher penalty rates for overages.
* Accounting [18 month in monthly increments] Wanted to understand cashflows and projections monthly, quarterly and yearly.
* Products [18 month in monthly increments] Seeking to understand market trends and consumer behaviour on product design and pricing decisions.
* Fraud Investigations [2 months] Wanted to identify trends and feature engineering to close the exploitation windows of network abusers and anti-money laundering.

 
# Project Background

 

QUALITATIVE: Before 2022, forecasts were a best guess approach based on a combination of experience and gut feeling of subject matter experts that lacked technical rigor with zero forecasts within spec.

 

QUANTITATIVE: Between 2022 to 2023 the forecasting work was given to a team of data scientists who emphasised pure machine learning over domain knowledge - but made no improvement over the purely qualitative approach previously with the best results only +/-20%.

 

QUAL-QUANT: By combining qualitative and quantitative approaches, my first successul forecast within +/-5% arrived within 2 weeks and kept creeping up over the coming months while allowing for further feedback and refinement from stakeholders for incremental improvement.

 

By taking an iterative approach to model testing - from univariate models like auto-regression or SARIMA to multivariate models or others like deep neural nets as needed - we could save further time and compute over time with each new forecast by also testing if the timeseries variance and trends were similar to the previous forecast to skip re-training otherwise to train a new model.

 

I built a test harness in python usng a functional approach to keep the logic modular and transparent - as well as allow for ease of adding in new models over time incrementally without needing to refactor existing codebases as outlined in the below BPMN-style process chart of how the algorithm worked in practice.

 

 

 

 
# Model testing and walk-forward results

 

Trust in the model performance was important for stakeholders to consider using the forecast in their daily work, for some non-technical stakeholders they prefered visual depictions of model performance such as the below example (using dummy data for commercial in confidence data not able to be publicly released) which shows what a within-sample forecast looked like when a model was tested against historical data.

 

This was in addition to statistical figures such as stationarity and RSME for more technical audiences.

 

This also meant we did not have to "wait and see" how models might perform as we could x-ray 5 years or more of historical data.

 

 
# The result

 

I was able to go from zero forecasts within spec to having 17% of international roaming destinations forecast within +/-5% according to backtesting over the last 12 months which accounted for just over 80% of the total network usage globally.
