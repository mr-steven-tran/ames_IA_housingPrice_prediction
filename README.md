# Examining Home Configurations and Their Effect on Sale Prices
### by Steven Tran



## The nation faces a severe housing shortage, and homebuilders are struggling to keep pace with demand

As of summer 2021, construction of new homes slowed due to labor shortages and higher materials prices. See the following:
* https://www.marketplace.org/2021/07/20/labor-shortage-and-building-material-costs-still-hammering-the-new-home-market/
* https://www.bankrate.com/real-estate/construction-building-trades-labor-shortage/

As homebuilders focus their resources on the construction of new homes and consider what kinds of homes they want to include in their product portfolios, I wondered whether certain types of **home configurations** had any meaningful effect on the home's sale price.

And so the question I'll try to answer in this project is **does a home's configuration, defined as the number of stories and count of bedrooms and bathrooms, meaningfully affect the sale price for a home?** 

While the project was a wonderful introduction to a kaleidoscope of data science concepts for me, I am hoping that the results may be at least a little illuminating for home builders or anyone generally interested in determinants of home prices.


## About the data

The data I'll be using to train regression models comes from the Ames, IA Housing Dataset, [a popular kaggle dataset](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/overview/description) often used by data science students and instructors.

A dictionary describing all the fields within the dataset can be found [here](), published by the dataset's author.



## Summary of Exploratory Data Analysis
For EDA, I reviewed cases of missing data, used K-Nearest Neighbors imputation to fill in some missing continuous data, and reviewed outliers in continouous variables.


## Summary of Preprocessing, Feature Engineering, and Model Evaluation
In preprocessing, I set up interaction terms between dummified variables for bedrooms, bathrooms, and home style.

I then deployed those dummified data into four models:
* Standard Multiple Linear Regression
* Standard Multiple Linear Regression (with PolyNomialFeatures)
* Ridge-regularized Linear Regression 
* Lasso-regularized Linear Regression

Of these four modeling scenarios, the Ridge-regularized Linear Regression resulted in the lowest root mean squared error in predicting home sale price, and had an R-squared predictive power of only about 37%.

Note that if my goal was to build a model that could very accurately predict sale price, I would have certainly focused on continued feature engineering, but in order to limit scope-creep, I restrained myself to discovering the relative effect on saleprice each home configuration had.

## Discussion of Findings & Recommendations
The production model estimated that compared to a 1-story 3-bedroom, 2-bathroom home configuration a 2-story 4-bedroom, 3-bathroom's sale price was greater by only \$1,983, and this was configuration with the strongest magnitude of effect on price compared to the baseline.

The findings of my analysis proved less compelling than I thought they might when I set out to do this project. I found that generally, if a homebuilder is having trouble deciding what kinds of home configurations to include in their product portfolios, they would probably not get much value from focusing on only how many stories and how many bedrooms and bathrooms are in each home configuration.

So with that, I recommend any homebuilder perplexed by the question not to lose any sleep over which home configurations to include in their portfolios
