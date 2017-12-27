
## Predict Annual Returns

**Feature Selection and Engineering**

The important part of the problem was to consider it as a time series and also use only relevant features so as to reduce the noise and reveal the signal more accurately.<br />
So most of the work is done on selecting the key features and which extract time series features.<br />
• Office_id<br />
• pf_category<br />
• Country code<br />
• Bought and Sold : All converted into Dollars<br />
• Euribor_rate<br />
• Libor_Rate : Missing values filled with median<br />
• Type<br />
• Start,Create,End : Months,Days,Ordinal Dates,Weekdays,Years from the
dates as the returns followed a trend.<br />
• Duration: Duration in days between Create and End Dates.<br />

**Modeling** <br />
Different models have been tried but the Gradient boosting model gave the best results.<br />
A native xgboost has been tuned as the final model.
