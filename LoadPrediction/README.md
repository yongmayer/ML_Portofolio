# Short-term electricity load prediction

## Summary
In the Texas freeze of February 2021, more than 4.5 million homes and businesses (more than 10 million people) were left without power, some for several days. See the [Wiki page](https://en.wikipedia.org/wiki/2021_Texas_power_crisis) for more info. In this work, I try to use history weather and electricity load data to predict future load based on forecasted weather in 8 weather zones in the Electric Reliability Council of Texas (ERCOT). A short-term (7-days) prediction is performed.

## Data
History Data and forecast weather are feteched from this [WiDSTexas2021 repository](https://github.com/WiDSTexas2021/datathon-code/tree/main/data).

Actural load in the prediction window can be found in [ERCOT](http://mis.ercot.com/misapp/GetReports.do?reportTypeId=13101&reportTitle=Actual%20System%20Load%20by%20Weather%20Zone) to validate the result.

For convenience, I also combined the history load and actural load in the prediction window. 
In this work, hisotry data window is 2008-07-01 to 2021-06-19 and the prediction window is 2021-06-20 to 2021-06-26.

## Model and Result
Trained a regression model using XGBoost. Achieved a RSME of 460.8 outof 9283.3 (4.96%).