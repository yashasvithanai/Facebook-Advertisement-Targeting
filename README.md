# Facebook Advertisement Targeting
### Cross-class collaboration project, Causal Analytics and Analytics Design & Application

The data provided contains results from a large-scale field experiment of advertisements for various clothing brands on Facebook platform. The business goal is to evaluate which attributes constitute successful advertisements. 

Additionally, we were required to investigate the E-Commerce Category and determine if the younger target audience interacts with the advertisement. Another field experiment was also conducted, and we were required to compare the results to provide our final recommendations.

## Data Dictionary
-  _date_ to the week the advertising campaign was run
-  _adType_ refers to whether the advertisement appeared in a link or a photo post 
-  _category_ refers to the type of retailer referenced in the advertisement 
-  _placement_ represents whether the ad appeared on the desktop or mobile client 
-  _keyword_ is a categorical variable that represents which store the purchase was made at 
-  _body_ represents the actual text of the ad 
-  _ageMean_ represents the average age of the targeted consumers 
-  _clickPerDollar_ represents the number of clicks the ad achieved for each dollar spent 

## Analytics Concepts and Skills
-	To understand the effect of different attributes on the advertisement’s success, we create multiple regression models utilizing categorical and interaction variables and interpret the main effects and interactions effects. 
-	We further use the model to make recommendations for given business scenario.

## Analysis

1.	**Regression Model with Categorical Variables to understand effect of attributes**

`facebookDataReg <- lm(clickPerDollar~factor(adType)+factor(category)+factor(placement)+ factor(keywords)+factor(body)+ageMean, facebookData)`

### Insights
-	Cosmetics is the most successful retailer category 
-	Photo post adType is expected to generate 7.4 more clicks per dollar compared to Link post
-	Mobile placement is expected to generate 33.65 more clicks per dollar compared to desktop

2.	**Regression Model recording Interaction Effect between the Average Age of Targeted Consumers and Retailer Category**

`InteractionRegression <- lm(clickPerDollar~factor(adType) + factor(category) + factor(placement) + factor(keywords) + factor(body) + ageMean + factor(category)*ageMean, facebookData)`


### Insights
-	94.8% of the Successful Advertisements in E-Commerce Category had an older targeted audience while the younger age groups did not interact with the advertisement.
-	In the second Ad Experiment, we find that 89.6% of the successful E-Commerce advertisements had a younger target audience.
-	We also found that majority of the successful E-Commerce advertisements were a Photo post Ad Type and a Mobile Placement.

## Recommendations
-	A Photo post Ad Type increases the probability of advertisement’s success than Link post with an expected lift by 7.4 clicks per dollar.
-	A Mobile placement increases the probability of advertisement’s success than that of Desktop with an expected lift by 33.65 clicks per dollar.
-	For the E-Commerce category, the advertisement in the first Experiment should be used to target older audience while the advertisement in the second experiment should be used to target younger audience. 


