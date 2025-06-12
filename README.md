# Predicting property sale prices in Ames using linea regression
Linear Regression in Action
Capstone Project

 ## Objective

 The goal of this task is to analyse the relationship between these variables and build a multiple linear regression model to predict the sales prices based on the `Gr_Liv_Area` and `Garage_Area` variables.

 ## Dataset Attributes

 The dataset contains information about houses in Ames, Iowa. The data was collected by the Ames City Assessor’s Office describing 2930 property sales which occurred in Ames, Iowa between 2006 and 2010. The dataset, containing 81 variables, was compiled and published by De Cock in 2011.

 Some of the variables contained in the original dataset have been removed from the the dataset provided to you.
 The dataset provided to you contains the following variables:
* **Year_Built:** year that the house was originally constructed
* **Year_Remod_Add:** year that the house was last remodelled
* **Total_Bsmt_SF:** total size of basement area in square feet
* **First_Flr_SF:** size of the first floor in square feet
* **Second_Flr_SF:** size of the second floor in square feet
* **Gr_Liv_Area:** size of above grade, ground living area in square feet
* **Full_Bath:** number of full above grade bathrooms in the house
* **Half_Bath:** number of half above grade bathrooms in the house
* **Bedroom_AbvGr:** number of above grade bedrooms (does not include basement bedrooms)
* **Kitchen_AbvGr:** number of above grade kitchens
* **TotRms_AbvGrd:** total number of above grade rooms (does not include bathrooms)
* **Fireplaces:** number of fireplaces in the house
* **Garage_Area:** size of garage in square feet
* **Sale_Price:** sale price of the house in dollars


*De Cock, D. (2011). "Ames, Iowa: Alternative to the Boston Housing Data as an End of Semester
Regression Project," Journal of Statistics Education, Volume 19, Number 3.*

- https://ww2.amstat.org/publications/jse/v19n3/decock/DataDocumentation.txt
- http://ww2.amstat.org/publications/jse/v19n3/decock.pdf

## Summary of findings

The objective of this task was to analyse the relationship between the variables and build a multiple linear regression model to predict the sales prices based on the `Gr_Liv_Area` and `Garage_Area` variables.

First, we analysed the data to see if it needed cleaning. We found the data to be clean and ready to use. 

Next, we checked the distribution of the data for each of the 13 variables by plotting a series of hisyograms. This showed that some variables, including `Gr_Liv_Area` and `Garage_Area` followed a normal distribution, while others did not.

We then created a correlation heat map to show the strength of correlation between the variables, and specifically the strength of their correlation with the sale price. While many of the variables showed a strong correlation with the sale price, we limited our investiagtion to the two variables with the strongest correlation. These were `Gr_Liv_Area` and `Garage_Area` with correlations of 0.71 and 0.64 respectively. 

Following this, we explored the relatonships between the variables using `pairplot` and found that the data was best modelled uing a normal distribution. Based on this we decided to standardised the data once it had been split into training and test sets in a 75:25 ratio. The training data was then used to generate a linear regression model and this was then used to a root mean square error on the test data values. The root mean square error was approximatley $47k, which was 26% of the mean sale price, showing a significant error but one that is still acceptable for regression analysis. 

Finally we plotted the training data, test data and error bars on scatter plots and evaluated the intercept and coefficents, compared to the median Sale price. The intercept was found to be similar to the median sale price, as expected, and the coefficents were found to represent 22% and 17% of the median sale price for `Gr_Liv_Area` and `Garage_Area` respectively. Since the vast majority of data points (95%) in a normal distribution lie within 2 standard deviations of the mean, we can see from these percentages that the sale price will change by 44% and 32% for ground floor living area and garage area respectively within this range.