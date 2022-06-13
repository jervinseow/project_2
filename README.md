<img src="http://imgur.com/1ZcRyrc.png" style="float: left; margin: 20px; height: 55px">

# Project 2 - Ames Housing Data and Kaggle Challenge

## 1. Problem Statement
I am an employee of a real estate agency in Ames, Iowa who has been tasked with doing market research for the company to find out the features of a house that are the strongest predictors of the sale price of the house and the magnitude to which these features affect the sale price of the house. This information can help our company’s agents determine a fair price range for each house and highlight the strongest features of each house they sell in order to maximise selling price for our customers.

### Some points to note:

- Without time/resources/expertise to understand everything about a house, the customer is unable to ascertain his own valuation perfectly.
- Because a customer’s resources are limited, our agents assist the price discovery process such that the customer is able to arrive at a satisfactory valuation.
- If we are able to highlight features that increase the perceived value and “downplay” features that decrease perceived value - then the price discovered by the customer will be higher than if he had total information about the house (which is impossible in reality).
- This means that we are able to extract additional value from the customer by tilting the price discovery process in our favor.

## 2. Executive Summary
The goal of this project is to accurately predict the sale price of a residential property in Ames, Iowa by utilizing linear regression models. The datasets I used (https://www.kaggle.com/c/dsi-us-11-project-2-regression-challenge/data) contain details of over 2,500 residential properties sold in Ames between 2006 and 2010. They also have 81 columns which include 22 nominal, 23 ordinal, 14 discrete, and 20 continuous variables (and 2 additional observation identifiers); 79 of which are the different features of a home. More details of the datasets can be found here: http://jse.amstat.org/v19n3/decock/DataDocumentation.txt

I started by importing and cleaning the datasets, and made sure that data types for each feature were accurate. I then identified and gave appropriate treatment to the null values.

Next, I explored the relationship between the features and sale price by looking for possible trends as well as collinearity. I created histograms and scatter plots for the numerical features and bar charts for the categorical features. Distributions for many numeric features were right skewed and also had a positive relationship with sale price, especially the features related to square footage. I also noticed that several of the categorical features also had a positive relationship with sale price.

I then encoded the nominal variables using one-hot encoding and the ordinal variables using ordinal encoding. Columns of both datasets were mismatched as a result and I made sure to sync them up before moving on to create interacion columns

After scaling the data and fitting it, I began to build several linear regression models, namely Linear, Ridge, LASSO and ElasticNet regression, to predict the sale price of a home. The best model would have the lowest root mean squared error (RSME) and highest R2 score for the training and test data.

I chose the Lasso Regression Model because of it gave the best testing R2 score and RSME. Its training R2 score and RSME was slightly lower but comparable to the other models. It was also the model with the least amount of overfit. You can find the Kaggle scores below:

Private Score (30% of test date): 21370.23
Public score (70% of test date): 24113.54

## 3. Conclusion and Recommendations

1. Features to highlight and downplay
- To highlight: House size, quality of the house and neighbourhood the house is located in 
- To downplay: Age and poor quality of the house  
2. Features to prioritise for refurbishment to maximise sale price
- The materials used to build the house have a stronger effect on Sale Price than the condition of the materials
- With a given budget for refurbishment, it is better to focus on material quality than condition
3. Neighborhoods to prospect for houses to sell 
- Houses are more expensive in certain neighborhoods like Northridge Heights, Stone Brook and Green Hills.
- Agents can focus on these neighborhoods to maximise commission
4. Agents can use this model to predict prices objectively prior to client negotiation  









