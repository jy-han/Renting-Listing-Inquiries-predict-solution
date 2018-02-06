# Renting-Listing-Inquiries Prediction
Data: Two Sigma Connect: Rental Listing Inquiries(2017 kaggle competetion) 
Task: predict how popular an apartment rental listing is based on the listing content like text description, photos, number of bedrooms, price, etc. 
The target variable : interest_level. 
Solution: Logistic regression with L1 regularization. 

The solution works as:
1. Read & Discovery data
 - Data size: 49352(train), 74659(test)
 - It has 15 features, with no null value
2. Feature Engineering
 - encode interest level with number
 - for price, bathrooms and bedrooms features, do some numerical calculating
 - create date: encode date to integer
 - remove building_id
 - latitude & longtitude: clustering
 - display_address is a high-cardinality category, use MeanEncoder method
 - street address: remove, contains same information with display_address
 - photos: remove fisrt (photos per house considered a useful feature later)
3. Train the model
 - default Logistic Regression: 0.93(logloss)
 - cross validation with regularization L1 and L2: result show L1 has better score with parameter 0.1
 - tuning parameter: result indicate 0.1 is best
4. Decide model and predict
 
 
