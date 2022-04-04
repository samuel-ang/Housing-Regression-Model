## Project 2 - Ames Housing Data and Kaggle Challenge

### Introduction & Problem Statement

For many people, a home represents a sizable portion of their assets and net worth. Moving houses can also be a lengthy and expensive process. It is for this reason that we founded RENO-BOT, the leading AI Renovation Advisor start-up, and it is our mission to help homeowners maximize the value of their houses in the event they wish to move. 

As Co-Founder and Chief Data Scientist, it is my pleasure to walk you through our proprietary housing price regression model that is the backbone of RENO-BOT.

In housing price regression model, we seek to **predict house sales prices with linear regression models**, to answer the question, **which factors influence house sales prices the most?**

Through the linear regression model, we can quantify the impact that key factors have on house prices. Some factors cannot be changed like location, but others could be. This would be informative to house owners who are interested in making improvements to their home, as reference point to evaluate cost benefit of potential improvements. 

Our data is based on the housing dataset from Ames, Iowa, and contains over 80 features.

### Methodology

We will conduct feature selection with the priciple of reducing multicollinearity between features. Numerical features and Categorical features will be assessed seperately, while sharing similar high level methodology, with differences in the type of statistic used for each type. 

This is done to preserve the structure of categorical features as the aim of this study seeks to provide homeowners with guidance in upgrading their home, so as to see the relative impact to price of each individual category in the regression model.

High Level Methodology:
- Remove features with strong multicollinearity based on a correlation heatmap
- Followed by reducing pairwise correlation, keeping the feature that has higher correlation with `SalePrice` of the pair. 

Numerical Features: we would use the Pearson standard correlation coefficient.

Categorical Features: we would use Cramér's V to assess the category to category association between categorical features, and then calculate the One-way ANOVA statistic to assess how siginificant the impact the category sub-group has on `SalePrice`.

Its a common saying that location is most important in buying a house. So we would group selected features to run the regression model, first area as baseline, then area plus location features, then area plus house features, then lastly all features together.

---

### Datasets

#### Provided Data

Data files from [DSI-US-11 Regression Challenge](https://www.kaggle.com/c/dsi-us-11-project-2-regression-challenge)
[Data description](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt).


### Conclusions and Recommendations

We have found that based on this dataset, house features impact housing price more than location features, and lasso regression model performed the best.

Coefficients of the regression can be used to inform home owner's renovation plans as to whether they have the potential to be cost-effective. In our model we have the data for estimated improvement to home values should home owners want to upgrade their porch, exterior coverings, masonry veneer and roof.

This would be useful datapoints in our AI renovation adviser to suggest possible improvements. For example, the largest increase we found is a $4,600 increase if masonry veneer is upgraded from Cinder Block to Brick Face. However whether this is a cost-effective improvement would depend on the cost to improve the feature.

Not all categorical features were included, several reasons include because the impact of these features were less significant compared to those selected. Further studies could collect a larger sample size with more balanced sample across categories, and employ principle component analysis to isolate the impact of those variables.

Further studies:

While one conclusion is that house features impact housing price more than location features, it could be that our location features are not refined enough to give significant results. We could investigate how location affects price by measuring distance from key amenities/city center to get a better picture of how location affects price.