| Ocotber
# 5 th
, 2019 |
| --- |

|
## Executive Summary
 |
| --- |

### Problem

What are the most important factors in selecting a housing and price and how will that be modeled effectively in a linear regression.

## Target Audience

Relator and Sales associates will use this information to determine how to price a house effectively in the market given the current housing and neighborhood information.

## Data and process

The data contained the housing sales of the Ames Iowa city sales for the year of 2014. While there were missing values, these were interepreted as zeros to ensure that it could be accounted for as non present data. Considering some of these values were missing because there was no data for this information, recording it as a zero allowed there to be groups that could easily be evaluated bother categorically and numerically. When looking at outliers, there was no reason to delete these. This is due to there being supporting evidence for the sale and no mistaken info to be taken into account.

When creating new columns, three cateogires must be done, this was to create a numeric ratings system, appropraite dummy variables and correct interaction variable. The quality and condition information was infered to have a zero to five rating with zero being not present and five being excellent. Using a corelation matriz this allowed use to infer that the quality was a key decision making component in any sale. When looking into dummy variables, the sale and house type showed the most correlation and impact on sale price. While neighborhood did have some powerful information, there was not enough of a sample size to infer more information due to most of the sales concentrated in three neighborhoods. When looking at house and sale type, larger more spread homes that were new builds had the biggest impact. Finally with interaction variables, this was done to combine variables such as sqft, build quality and number of rooms into a single variable. This changed the behavior of the variable as well as lead use to have more inference power. All of these were combined to make a single model.

When evaluated the model, I used a combination of r2 scoring and regularization. When looking at the model I noticed that it was having greater difficulty predicted higher prices and was bowing out. When looking at a residuals plot, there was also a lack of homostocasitcy. to correct for this I decided to use the natural log of the sale prices and then evaluate based on that information. When looking at this info incomparison to the model, I showed a truely linear and corrected distribution. After checking the final lasso, I showed that I was using appropraite variables and was not overfit.

## Findings

1. When selling a home, the number of rooms, overall quality of features and sales type were the most important factors. Looking at these individually the larger and more maintained homes would have more of higher price because these homes are larger and more well maintained.

2. When looking at the pricing of homes by neighborhood, most of the sales are concentrated in a select few neighborhood. While this is vital, there was more information held in the type of home and how recent the build. There is a higher demand for larger newer homes in Ames. 

3. When looking at certain features, there pressence was not as important as the quality that was present. With regards to kitchens, the number of kitchens did not have as large of an impact as the quality of the kitchen present. A fully upgraded kitchen could cause a 20% correlation with the sales price.

4. While this method is great at predicting lower to mid-high priced homes, the luxury homes held more information and were harder to normalize against. This is due to additional factors not being present in the data set, such as historical information and neighborhood information (outside of the name).

5.Overall, house prices seem to have a more logistic behavior that linear one. When evaluating housing prices, looking at the log will allow for the data to be seen more linearly and have a more homoscedastic shape to it. This shows a even distribution of noise and errors.


## Recommendations

For further investigation, I would like to look at more neighborhood data as well as transactional data. If a house has not sold for a long time and with a low previous sale price, it could show appreciation within the neighborhood and home itself in comparision to the previous market value. Also if this is a house that has sat on the market it could indicate a lower sale price versus one that moved more quickly. With regards to neighborhood information, I would like to see how homes would sell based on neighboorhod demographics. Younger people tend to buy smaller homes in hipper neighborhoods, while families will consider other factors such as school ratings and larger lot sizes. These house may have the same sale price, but would sell for completely different reasons.

## Data 

Ames Housing Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|Index|int|all|This is the row ID for the data set.| 
|pid|integer|all|transaction Id for house.|
|ms_subclass|int|all|Building Class.|
|ms_zoning|object|all|Zoning Code for data|
|lot_frontage|float|all|area on lot without home|
|lot_area|int|all|lot size|
|street|object|all|designdation of driveway type|
|alley|object|all|designdation of alley type|
|lot_shape|object|all|shape of property|
|land_contour |object|all|flatness of property|
|utilities|object|all|type of utlities|
|lot_config|object|all|style of lot|
|land_slope|object|all|slope of property|
|neighborhood|object|all|neighborhood name|
|condition_1|object|all|proxmity to road|
|condition_2|object|all|proxmity to road|
|bldg_type|object|all|type of dwelling|
|house_style|object|all|house style|
|overall_qual|object|all|quality of build|
|overall_cond |object|all|quality of maintence of home|
|year_built|int|all|year house was built|
|year_remod/add|int|all|year house was remodled|
|roof_style|object|all|type of roof|
|roof_matl|object|all|roof material|
|exterior_1st|object|all|exterior finish on house|
|exterior_2nd|object|all|exterior finish on house|
|mas_vnr_type|object|all|masonery vaneer type|
|mas_vnr_area |object|all|masonery vaneer in sqft|
|exter_qual|object|all|quality of exterior|
|exter_cond|object|all|quality of maintence of exterior|
|foundation|object|all|type of foundation|
|bsmt_qual|object|all|quality of basement|
|bsmt_cond|object|all|quality of maintence of basement|
|bsmt_exposure|object|all|exposure of basement walls if present|
|bsmtfin_type_1 |object|all|finish status of basement|
|bsmtfin_sf_1 |float|all|Sqft in basement|
|bsmtfin_type_2|object|all|finish status of basement|
|bsmtfin_sf_2 |float|all|Sqft in basement|
|bsmt_unf_sf  |float|all|Sqft in basement in unfinished area|
|total_bsmt_sf |float|all|Sqft in basement total area|
|heating  |object|all|type of heating present|
|heating_qc |object|all|quality of heating available|
|central_air|object|all|central air present (y/n)|
|electrical|object|all|type of electrical present|
|1st_flr_sf|int|all|Sqft on first floor|
|2nd_flr_sf|int|all|Sqft on second floor|
|low_qual_fin_sf|int|all|Sqft that is low quality on all floors|
|gr_liv_area|int|all|Sqft that is high quality on all floors|
|bsmt_full_bath|float|all|number of full bathrooms in the basement|
|bsmt_half_bath |float|all|number of half bathrooms in the basement|
|full_bath|int|all|number of full bathrooms|
|half_bath|int|all|number of half bathrooms|
|bedroom_abvgr|int|all|number of bedrooms|
|kitchen_abvgr|int|all|number of kitchens|
|kitchen_qual|object|all|quality of kitchen|
|totrms_abvgrd|int|all|total numbers of rooms not in basement|
|functional|object|all|functional rating of home|
|fireplaces|int|all|number of fireplaces|
|fireplace_qu|object|all|quality of fireplace|
|garage_type|object|all|type of garage present if applicable|
|garage_yr_blt |float|all|year garage was built|
|garage_finish|object|all|type of finish on garage|
|garage_cars|float|all|numbers of cars that can fit in garage|
|garage_area|float|all|garage Sqft|
|garage_qual|object|all|quality of garage|
|garage_cond|object|all|quality of garage maintence|
|paved_drive|object|all|pressence of a paved driveway|
|wood_deck_sf|int|all|wood deck area sqft|
|open_porch_sf |int|all|open porch area sqft|
|enclosed_porch |int|all|enclosed porch area sqft|
|3ssn_porch |int|all|three sided porch area sqft|
|screen_porch|int|all|screened in porch area sqft|
|pool_area|int|all|pool area sqft|
|pool_qc|object|all|quality of pool|
|fence |object|all|presence of fence (y/n)|
|misc_feature|object|all|misc item in house|
|misc_val|int|all|value of misc item|
|mo_sold|int|all|month house was sold|
|yr_sold|int|all|year house was sold|
|sale_type |object|all|type of sale|
|saleprice|float|all|sale price of house in dollars|
|exter_qual_numeric|float|all|numeric converion of quality of build (0-5)|
|exter_cond_numeric|float|all|numeric converion of quality of maintence (0-5)|
|bsmt_qual_numeric|float|all|numeric converion of quality of basement build (0-5)|
|bsmt_cond_numeric|float|all|numeric converion of quality of basement build maintence (0-5)|
|heating_qc_numeric|float|all|numeric converion of quality of heating (0-5)|
|kitchen_qual_numeric|float|all|numeric converion of quality of kitchen (0-5)|
|fireplace_qu_numeric|float|all|numeric converion of quality of fireplace (0-5)|
|garage_qual_numeric|float|all|numeric converion of quality of garage build (0-5)|
|garage_cond_numeric|float|all|numeric converion of quality of garage build maintence (0-5)|
|pool_qc_numeric|float|all|numeric converion of quality of pool (0-5)|
|sale_type_CWD|int|all|sale type for CWD (0-1)|
|sale_type_Con|int|all|sale type for Con (0-1)|
|sale_type_ConLD|int|all|sale type for ConLD (0-1)|
|sale_type_ConLI|int|all|sale type for ConLI (0-1)|
|sale_type_ConLw|int|all|sale type for ConLw (0-1)|
|sale_type_New |int|all|sale type for New (0-1)|
|sale_type_Oth|int|all|sale type for Other (0-1)|
|sale_type_WD|int|all|sale type for WD (0-1)|
|house_style_1.5Fin|int|all|home type for 1 and 1/2 story finished (0-1)|
|house_style_1.5Unfint|all|home type for 1 and 1/2 story unfinished (0-1)|
|house_style_1Storyint|all|home type for 1 story finished (0-1)|
|house_style_2.5Unfint|all|home type for 2 and 1/2 story unfinished (0-1)|
|house_style_2Storyint|all|home type for 2 story finished (0-1)|
|house_style_SFoyerint|all|home type for split foyer finished (0-1)|
|house_style_SLvl|all|home type for split level finished (0-1)|
|sale_type_VWD|int|all|sale type for VWD (0-1)|