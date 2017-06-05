# Food-amenities-demand-quantity-prediction
A comprehensive approach (Polynomial Ridge Regression, Pipeline) towards predicting the demand of food amenities based on past sales data.

***Business Problem***: To predict the expected order quantity of food amenities based on past data.

Data Definition (test SKU = Cucumber (Indian))
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

Data Understanding and Processing
>Outlier detection and removal
* Amount of quantities lying below 5 percentile of the range or above 95 percentile of the range were considered outliers
* The outliers were replaced by the values closest to them in the considered range (5-95)

>Summary Statistics
* Input
