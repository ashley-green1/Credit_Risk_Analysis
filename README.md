# Credit Risk Analysis

## Overview

Here we have been tasked with applying machine learning to predict credit card risk.  Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, we test various algorithms for accuracy to determine which bests predicts low and high risk loan applications. 

The dataset consists of approximately 85 features (aka variables) for each loan.  Some examples are Principal & Interest Received to Date, Most Recent Payment Amount, Interest Rate, Debt-to-Income ration, Months Since Recent Credit Inquiry and Home Ownership. 

The problem inherent with this dataset is a severe imbalance in favor of good loans.  Naturally, most loans never face default, resulting in 99.9% of the database being low-risk loans.  That is extremely skewed data. 

To overcome the skewness of the data, we use sklearn to split the data into training and testing sets.  We then use the testing data to train various models and make predictions.  Lets now go over the results. 


## Results


