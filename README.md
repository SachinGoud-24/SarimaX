# SarimaX
In a retail environment, multiple items undergo price changes constantly. To maintain margin and push sales, we ought to track the performance of the 
item after price change, in metrics like sales/units/margin etc. And if there's red signal in those metrics, roll back the price change.
And for this, we need a baseline to show us how the numbers would look like in the absence of the price change. Once this is available, we can compare the
actual sales/units/margin against this baseline. 

How can we obtain this baseline? Based on the past performance of the item!
There are multiple other approaches and statistical methods. But in this project, I am choosing SARIMAX model. 
This model uses the available past information of the item and tries to estimate/forecast out-of sample values. ( Predict values for the future timeline).

SARIMAX:
S = seasonal
AR = Autoregressive
I = Integration
MA = Moving Average. 
X = exogenous variables

Refer this for a detailed explaination on Sarimax model.
https://www.youtube.com/watch?v=WjeGUs6mzXg

Refer this for documentation on statsmodels SARIMAX python library:
https://www.statsmodels.org/stable/generated/statsmodels.tsa.statespace.sarimax.SARIMAX.html

pdq, PDQ, S (seasonal) values used:
p = [0, 1, 2]
d = [0, 1]
q = [0, 1, 2, 3]
P = [0, 1]
D = [0]
Q = [0, 1]
S = 52 ;     since the data used has a weekly data points with annual seasonality (52 weeks in a year).

Exogenous (X) variables used:
To forecast sales of an item: Item Price
To forecast units of an item: Item Price
To forecast margin of an item: Item Price, Item cost.



