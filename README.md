# Predicting Flight Prices
This project was my attempt at predicting flight prices using a linear regression model. 


## Data 

All data for this project was scraped from Kayak using selenium. The dataset I gathered contained 1,037 flights each with a total of 19 featueres. After cleaning and removing duplicates the dataset had a total of 738 flights. All data points were gathered from LNK to ZRH to ensure that origin and destination did not affect the models.

## Algorithms

*Feature Engineering* 
  - Converting times to integers in order to represent them in linear regression
  - Computing a ‘Days to Trip’ column that found the difference of the date today and the departure date for the trip
  - Dropping large outliers for flight prices. 14 values for price over $2,000 which were ultimately dropped as the mean and mode of those values were $738 and $578 respectively. 
  - Modeling features in both heat maps and pair plots to determine which features had the biggest relationship with the target.  

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
   
## Summary
- This question cannot be answered by a linear model, this is the best model we could get using traditional regression, using time series would be my next steps.
