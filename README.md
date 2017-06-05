# Food-amenities-demand-quantity-prediction
A comprehensive approach (Polynomial Ridge Regression, Pipeline) towards predicting the demand of food amenities based on past sales data.

***Business Problem***: To predict the expected order quantity of food amenities based on past data.

**Data Definition (test SKU = Cucumber (Indian))

>Data Variables considered and their Definition
* Input variables
1. AvgSP (Rs./Kg.) - Average selling price of the SKU
2. RetailPrice (Rs./Kg.) - Retail price of the SKU
3. Wholesale (Rs./Kg.) - Wholesale price of the SKU
4. FinalGRN (Rs./Kg.) - Cost price
5. CustomerCount - Total number of customers for the particular SKU
6. TotalGTOrders - Total number of customers across all SKUs

* Required variable
1. ActualDemand - Demand quantity

>Time Period considered
* 17/03/2017 till 18/05/2017

**Data Understanding and Processing

>Outlier detection and removal
* Amount of quantities lying below 5 percentile of the range or above 95 percentile of the range were considered outliers
* The outliers were replaced by the values closest to them in the considered range (5-95)

>Summary Statistics

* Input

![input_variables_sumstat](https://cloud.githubusercontent.com/assets/26039458/26774708/15edf306-49c1-11e7-8566-916ca12415b1.png)

* Output

![output_var_sumstat](https://cloud.githubusercontent.com/assets/26039458/26774720/333901b2-49c1-11e7-8de0-7a9922dfaabe.png)

>Training and Test Datasets
* Training set - 17/03/2017 to 13/05/2017
* Test set - 14/05/2017 to 18/05/2017

>Seasonal effect

Since time series forecasting hasn't been used in this approach, we don't need to worry about seasonality.

>Creating Data Input to model

* Assumption: The various prices of the SKU are known on the particular day or can at least be predicted with a very nice accuracy
* The input variables to be estimated remain #CustomerCount and #TotalGTOrders
* Average selling price of the particular SKU along with the average selling price of onion is used for the prediction of the above input quantities
* A polynomial ridge regression model is employed using a pipeline, with alpha = 18.0 for CustomerCount prediction, = 21.0 for TotalGTOrders prediction.
