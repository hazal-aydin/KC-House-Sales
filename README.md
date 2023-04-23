# King County House Sales

Author: Hazal Aydin

## Overview

The scope of this study is to assist a real estate agency that helps individuals in selling homes. The expected outcome is to guide homeowners on how renovations could potentially enhance the assessed value of their properties and by what degree - by identifing the key property features, such as square footage and number of rooms. The model I prepared is created through 5 iterations. 86.6% of the variations in the sale prices can be explained by the model, but it has its own limitations and could be refined even futher. With this initial study, we identified "square footage of house apart from basement", "the square footage of interior housing living space for the nearest 15 neighbors" and "the square footage of the lot" as the most important features.

### Business Problem

In January 2023, the median listing home price in King County, WA was $800K, trending up 4.2% year-over-year. 

It presents a good business opportunity for the homeowners who wants to sell their homes and maximise their profits from their investments. However, to maximise the profit, they need to commit to renovations.

The question is how much they should spend and which features they should invest in.


### Data

The King County House Sales dataset is used for this study. It comes from 2014-2015 year's sales data and consists of 21 features, including an unique id, and 21,597 entries. With the amount of entries, the modelling process should satisfy the minimum requirements of the tests (i.e. Jarque-Bera) and the outcomes are likely to be accurate.


### Methods

I took an iterative and train-test split approach to the regression model. Used both OLS model from statsmodels and LinearRegression from sklearn.

I used plots to visualise the relationships between the variables and behaviours of the residuals.

To prepare the data for the analysis, I also utilised the following methods:

* I removed columns and rows that were not part of the study ('id','lat','long',  and 'view')
* Either filled the null values or drop the rows that consist of them.
* Transformed some of the features into more insightful ones. For example, the built year is transformed into the age of the house.
* Addressed the multicollinearity of features and removed the highly correlated ones from the dataset.
* Created dummy variables to include the categorical values to the study.

## Conclusions

The model is created through 5 iterations. It explains 86.6% of the variables in the dependent variable (Y = Sale Prices) through independent variables (X = Features / Predictors).

Through iterations, I increased the adjusted R2 value from 78.8% to 86.6% which is a significant 10% increase, resolved the large condition number issue, and recuded the Jarqe-Bera score from 998472 to 3451.401 (-99.65%).

Apart from the locations of the houses, which cannot change through renovations, "square footage of house apart from basement", "the square footage of interior housing living space for the nearest 15 neighbors" and "the square footage of the lot" appeared to be the most important features when it comes to valuing a property.

Having renovations in the past 5 years, good quality finish, having a waterfront view and high number of bathrooms all increase the overall sale price.

### Limitations & Next Steps

Even though I created a good fit model that explains 86.6% of the variables, it is just an initial study to identify the top features - and it comes with its own limitations. The main issue with the study is the variables it uses.
I included most of the variables as is. However, the model showed some interesting outcomes that requires more investigation. Next steps to refine the model should include the following points:

* The square footage of interior housing living space for the nearest 15 neighbors is the second most important feature in the model. By itself, it doesn't give much insight on the renovations. If we transform this data into a categorical variable that states whether a house has a larger living space than its neighbours will be more meaningful.
* The number of floors and the number of bedrooms have negative correlation with house prices. It's an unexpected result from a business perspective. Their relationship with the square footage of living space and the sizes of the rooms and floors could give more actionable insights. It's possible that having larger rooms and floors could be increasing the value of the property more than the number of them.
* Finally, Jarqe-Bera score of the study is still at large and needs addressing. Transforming the features by considering the above points could help - or the model could be more aggressive with removing the outliers.

## For More Information

For More Information
Please review our full analysis in [my Jupyter Notebook] or my presentation.

For any additional questions, please contact Hazal Aydin at h.aydinhazal@gmail.com

Repository Structure
├── README.md                                              <- The top-level README for reviewers of this project
├── student.ipynb                                          <- Narrative documentation of analysis in Jupyter notebook
├── King_County_House_Sales- Jupyter Notebook.pdf          <- PDF version of the jupyter notebook
├── King_County_House_Sales_Presentation.pdf               <- PDF version of project presentation
└── data                                                   <- Sourced externally