# Predicting flight prices
Emily Ubbelohde

## Abstract
The goal of this project was to define and tune a regression model to predict the price of future flights. I scraped data from Kayak using selenium, after cleaning and feature engineering I was able to visualize my regression models using Scikit-learn. 


## Design
This project was inspired by my passion for travel, and the knowledge that so many people right now are planning their next get away. I originally was hoping this model could be used to predict when you should purchase flight tickets, but due to the lack of linearity of this problem that was not possible. However the code written could be used to scrape future prices between anyones desired trip origin and destination, and build a model that would give them an idea of what they can expect to spend on those tickets for the current point in time. 

## Data
The dataset I gathered contains 1,037 data points with 19 features, after removing duplicates I was left with 738 data points. Most of the features were categorical, or unusable in their scraped form. The categorical values gave little to no improvement in the prediction of the model. All data points were gathered from LNK to ZRH to ensure that origin and destination did not affect the models.

## Algorithms

Feature Engineering 
 Converting times to integers in order to represent them in linear regression
 Computing a ‘Days to Trip’ column that found the difference of the date today and the departure date for the trip
Dropping large outliers for flight prices, there were 14 values over $2,000 which made modeling difficult as the mean and mode of those values were $738 and $578 respectively. 
Modeling features in both heat maps and pair plots to determine which features had the biggest relationship with the target.  

*Models*
  
Linear regression, polynomial regression, ridge regression, and lasso regression were used before settling on polynomial regression as the model with the best performance across train, validate and test sets. 

*Model Evaluation and Selection*


  
The entire training dataset into 90/10 train vs. holdout, and all scores reported below were calculated with 5-fold cross validation on the training portion only. Predictions on the 25% holdout were limited to the very end, so this split was only used and scores seen just once.


**Best Model**
   - The best model ended up being a third degree polynomial that combined the outgoing flight from the origin, the negative decay of the return duration and the number of days until the trip
   - Training Score with Cross Validation: .216
   - Validation Score with Cross Validation: .208
   - Standard Deviation 0.0814
   - Variance 0.0062

**Test Data** 
   - Score: 0.18  

## Tools
- Numpy and Pandas for data manipulation
- Scikit-learn for modeling
- Matplotlib and Seaborn for plotting

## Summary
- This question cannot be answered by a linear model, this is the best model we could get using traditional regression, using time series would be my next steps. If scraping data hadn't taken so long I like to think I would have gotten there. I would also apply the best model I got for this data set to a data set for a different destination to see how my results vary. 

## Communication
Slides and visuals presented 
