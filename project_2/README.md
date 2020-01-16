# Problem Statement:
How can home owners increase the sale prices of their homes?

# Data Dictionary (Final Features):
|Feature|Type|Description|
|---|---|---|---|
|BsmtFin SF 1|float|(Continuous): Type 1 finished square feet|
|Bsmt Exposure|int|(Ordinal): Refers to walkout or garden level walls|
|Fireplaces|int|(Discrete): Number of fireplaces|
|TotRms AbvGrd|int|(Discrete): Total rooms above grade (does not include bathrooms)|
|Mas Vnr Area|float|(Continuous): Masonry veneer area in square feet| 
|Full Bath|int|(Discrete): Full bathrooms above grade| 
|Year Remod/Add|int|(Discrete): Remodel date| 
|Bsmt Qual|int|(Ordinal): Evaluates the height of the basement| 
|Total Bsmt SF|float|(Continuous): Total square feet of basement area| 
|Garage Cars|float|(Discrete): Size of garage in car capacity| 
|Garage Area|float|(Continuous): Size of garage in square feet| 
|Kitchen Qual|int|(Ordinal): Kitchen quality| 
|Exter Qual|int|(Ordinal): Evaluates the quality of the material on the exterior| 
|Overall Qual|int|(Ordinal): Rates the overall material and finish of the house|  
|Land Contour_HLS|int|(Nominal): Flatness of the property - Hillside|
|Neighborhood_Crawfor|int|(Nominal): Physical locations within Ames city limits - Crawford| 
|Neighborhood_GrnHill|int|(Nominal): Physical locations within Ames city limits - Green Hills| 
|Neighborhood_NoRidge|int|(Nominal): Physical locations within Ames city limits - Northridge|
|Neighborhood_NridgHt|int|(Nominal): Physical locations within Ames city limits - Northridge Heights| 
|Neighborhood_Somerst|int|A(Nominal): Physical locations within Ames city limits - Somerset| 
|Neighborhood_StoneBr|int|(Nominal): Physical locations within Ames city limits - Stone Brook|
|Bldg Type_Duplex|int|(Nominal): Type of dwelling - Duplex|
|Bldg Type_Twnhs|int|(Nominal): Type of dwelling - Townhouse Inside Unit|
|Bldg Type_TwnhsE|int|(Nominal): Type of dwelling - Townhouse End Unit|
|Foundation_Slab|int|(Nominal): Type of foundation - Slab|

# Conclusions and Recommendations:
The feature which influences prices most is dependant on whether the house is located in the Neighborhood of Green Hills while the feature which hurts house prices most is if the house is if the house is a Townhouse end unit.

Some features home owners should look at to improve their house prices are the number of full bathrooms above grade, Kitchen quality, Exterior quality, Overall quality, having Hill side land contour and having slab foundation.

Neighborhoods which may be considered good investments are (in order) Green Hills, Stone Brook, Northridge, Northridge Heights, Crawford and Somerset.

The stronger features in this model are largely dependent on the neighborhood the houses are in. We can look that factors which make those neighborhoods more desirable compared to the others. For exmaple, we can look at the crime rates in the neighborhood or distance away from the central business district or the quality of air in the neighborhood.