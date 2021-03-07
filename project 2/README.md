# **Project 2 - Ames Housing Price Prediction Challenge**

## **Problem Statement**

With house prices in Ames, Iowa <a href='https://datausa.io/profile/geo/ames-ia/#housing'>trending 7-9% upwards year-over-year</a>, there is a huge opportunity for both homeowners and investors participate in the booming real estate market.

By thoroughly examining the Ames Housing Dataset to identify key housing features, including the exterior facade, housing characteristics as well as the surroundings of the houses, we determine which have of these the greatest impact on sale prices. We seek to develop a and iteratively refine a regression model that will accurately predict future housing prices and will share our business insights with future investors and homeowners to help them secure the best deals.


## **Executive Summary**


This project explores the <a href='https://www.kaggle.com/c/dsi-us-6-project-2-regression-challenge/overview'>Ames Housing Dataset challenge launched on Kaggle</a> with the purpose of constructing a powerful regression model to accurately predict housing prices in the future.

The data set contained information about 79 features for over 2000 homes sold in Ames, Iowa over the 2006-2010 period. Through a combination of extensive data cleaning and exploratory data analysis, we identified and interpeted missing values, before making use of heatmaps, histograms, scatter plots, bar plots and boxplots to obtain a complete statistical picture of the training data set. From this, we were able to identify several important features which had strong correlations to the sale price.

To further fine-tune the data, feature engineering was also performed as there were many overlapping and correlated features which provided similar information to one another, and thus they were either re-factored or removed to prevent multicollinearity from affecting our prediction models. Some features were configured to be more interpretable and one-hot encoding was performed on categorical data to be compatible for our machine learning models.

The given training set was partitioned into a smaller training set and a validation set to allow for model assessment before performance evaluation on the test set. 3 regression models were selected for this purpose - the linear, ridge and lasso regression models. These models were assessed based on the root-mean-squared error estimates using a 10-fold cross validation method. The ridge regression model marginally overperformed the linear and lasso regression models, with a root-mean-squared-error of 27972.

The top features predicting sale prices were: combined house quality, combined area and the neighborhood of Stonebrook. Features expected to be among influencers were the house age and the years since the house was remodelled / added on to. However, we noted that perhaps the overall quality of the house was a bigger factor than the age of the house.

We do recommend homeowners and investors pay close attention to the above features, as well as having awareness of external economic conditions, such as the 2007-2008 housing market crash. Those were extenuating circumstances that caused a capitulation in housing prices over the period when the data was collected. Thus it is equally important to be wary of external economic conditions and recessions which are massive influence in housing prices.


## **Data Dictionary**


The data dictionary for the Ames housing data can be found on Kaggle <a href='https://www.kaggle.com/c/dsi-us-6-project-2-regression-challenge/data'>here</a>.


## **Conclusions and Recommendations**


Through extensive cleaning, exploratory data analysis, preprocessing and running various models on the training set, we were able to build a model to help current and future homeowners, as well as investors with their decisions in the Ames, Iowa housing market.

We used the ridge regression model, as it had the best performance on the training data set with an RMSE of 27972, a 63.6% improvement over the baseline RMSE. The best predictors of sale price are:
- Combined house quality: A score comprising the overall quality, external quality, kitchen quality and basement quality. We do expect this as future home buyers would be influenced by the current quality / condition of the house in its current state, and that alone would have a major psychological impact on home valuations.


- Combined area: The sum of the above ground living area, total basement area and garage area. These contribute to the total built up area of the house and allows the current homeowner to demand a higher sale price.


- Neighborhood (Stonebrook): Upon further research, <a href='https://www.stonebrooke.org/'>Stonebrook</a> is home to a strong residential community with multiple amenities including a swimming pool and a clubhouse. It also has one of the best locations in Ames with its close proximity to the North Grand shopping mall and Iowa State University, which is the <a href='https://www.flickr.com/photos/fourstarcashiernathan/sets/72157624665613300/page3/?view=lg'>largest university</a> in Iowa. Given its prime location, it's no wonder that homes in this neighborhood have a significant impact on the house sale price.

Some surprising features which were not included in the top 3 are the house age and the years since the house was remodelled / added on to. It was expected that these had a major influence on the sale price, but it is also worth noting that it may not just be the age of the house that matters, but the overall quality of the house.

With these top features identified, our recommendation to future homeowners and investors is to pay close attention to the combined quality and built up area of the house, as well as the neighborhood where the home is located in. We also do note the extenuating circumstances of the housing market during the 2006 - 2010 years where the US housing market bubble popped, causing a capitulation in housing prices. Thus it is equally important to be wary of external economic conditions and recessions which are a massive factor in housing prices.

#### **Interpretations & Reflections on Kaggle Results**

The root mean squared error for the Kaggle test submission was approximately $47000.

Despite a low RMSE score on the training sets, the ridge regression model did not have an equally strong performance on the Kaggle test set. This was likely due to the regression model being fitted with only 36 features. In addition, there was much deviation from actual sale prices above \\$300,000, which could mean that this model is more suited towards predicing sale prices below \\$300,000.

On hindsight, this is likely an indication that too few features were included in the model, as a result of over-zealous feature removal during the EDA and feature engineering processes. Removed features which were deemed similar to the features kept, such as MS Zoning or external housing materials, could have allowed the model to perform better on the test set. As such, greater care should be taken in future projects to prevent underfitting of the model, which could result in better predictions
