# Linear Analysis of House Prices

Authors:
Alec Mills
Ashli Dougherty
Matt Rubic

## Project Overview

For this project, we used multiple linear regression modeling to analyze house sales in a King County from 2014-2015.

### Business Problem

Based on the King County Housing Authority data from 2014-2015, we seek to explain to a large realty group (e.g. Berkshire Hathaway) which variables influence the sale price of the most expensive houses on the market (top 15%, or houses over \\ $800k).

### The Data

This project uses the King County House Sales dataset, which can be found in  `kc_house_data.csv` in the data folder in the project's GitHub repository. The description of the column names can be found in `column_names.md` in the same folder.

### Methods

We cleaned data to remove all null values and convert categorical data into numeric data that could be interpretted by a linear regression model. We used correlation between our target variable (price), and all other variables to identify the most highly correlated variable (sqft_living), and made a baseline linear regression model of our target variable from that variable. We iterated upon that model, to include as much information as we could to explain price, while also trying to reduce the effect of collinearity.

### Results

Our model was able to explain 54% (r-squared of .540) of the variation in sale price of houses that sold for over \\ $800,000. The two variables that explained the greatest amount of variation in sale price were sqft_living and grade of a house. Based on the coefficents produced by our model, each square foot of a house increased the sale price by \\ $275.98, and each increase in building grade above the minimum obtainable grade for a house increased the sale price by about \\ $4454. 

The model that we used to explain the variance in sale price of high-value houses performed better with the data of all houses sold in King County for 2014-2015, where it was able to explain 69.2% (r-squared of .692) of the variance in sale price of a house. We found that much of the variation in sale price that our model did not account for could be explained by the location of a house. Though latitude and longitude are continuous values and were included in our model, their relationships with price are non-linear. We found through graphical and statistical analysis that specifc locations yielded generally higher sale prices, and transcended what was otherwise a strong relationship between sqft_living and price of a house.

![alt text](https://github.com/mattrubic/dsc-phase-2-project-v2-3/blob/main/images/p2_1.png?raw=true)
![alt text](https://github.com/mattrubic/dsc-phase-2-project-v2-3/blob/main/images/p2_2.png?raw=true)
![alt text](https://github.com/mattrubic/dsc-phase-2-project-v2-3/blob/main/images/p2_3.png?raw=true)
![alt text](https://github.com/mattrubic/dsc-phase-2-project-v2-3/blob/main/images/p2_4.png?raw=true)
![alt text](https://github.com/mattrubic/dsc-phase-2-project-v2-3/blob/main/images/p2_5.png?raw=true)
![alt text](https://github.com/mattrubic/dsc-phase-2-project-v2-3/blob/main/images/p2_6.png?raw=true)
![alt text](https://github.com/mattrubic/dsc-phase-2-project-v2-3/blob/main/images/p2_7.png?raw=true)
![alt text](https://github.com/mattrubic/dsc-phase-2-project-v2-3/blob/main/images/Untitled.png?raw=true)



### Conclusions

Based on our analysis, we would explain that the greatest factors for predicting which houses will sell for the greatest amounts (among high-value houses) are square footage of the house, building grade of the house, and the location of the house. We identified some premium locations that contribute to greater sale prices, such as houses in the Seattle city limits, houses that are near water, and some specific neighborhoods. We also concluded that in general, factors like the year a house was built, its condition above average, and its number of bedrooms are not predictive of its sale price (among high value houses). We suspect these factors are not predictive because houses in this subset are of a higher minimum condition than all houses sold, and that location plays a grater role in the value of a house than these specific features. A limitation of our analysis is that a linear regression will not identify factors that may explain much of the data, but in a non-linear way (such as the relationship between latitude, longitude, and price). A next step would be to use a non-linear regression (such as a Random Forest regression) to identify relationships within the data that exist, but are not linear.