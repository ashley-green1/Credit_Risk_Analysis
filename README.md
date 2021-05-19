# Credit Risk Analysis

## Overview

Here we have been tasked with applying machine learning to predict credit card risk.  Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, we test various algorithms for accuracy to determine which bests predicts low and high risk loan applications. 

The dataset consists of approximately 85 features (aka variables) for each loan.  Some examples are Principal & Interest Received to Date, Most Recent Payment Amount, Interest Rate, Debt-to-Income ration, Months Since Recent Credit Inquiry and Home Ownership. 

The problem inherent with this dataset is a severe imbalance in favor of good loans.  Naturally, most loans never face default, resulting in 99.9% of the database being low-risk loans.  That is extremely skewed data. 

To overcome the skewness of the data, we use sklearn to split the data into training and testing sets.  We then use the testing data to train various models and make predictions.  

We evaluate the model's performance by the following:
- Accuracy Score -  this is simply the rate of predictions that are correct, with 1 being 100% accurate and 0 being 0% accurate.
- Precision Score -  a measure of how reliable a positive classification is, with 1 being 100% reliable and 0 being 0% reliable.  For example, "I know that the test for high risk came back positive.  How likely is it that the loan is high risk?"
- Recall Score -  a measure of how many actual positives were identified correctly, with 1 being 100% correct and 0 being 0% correct. "I know that my loan is high risk. How likely is it that the test will predict it?"

 

## Results

Lets go over 6 different machine learning model predictions of a high risk loan application.


### Random Oversampling

- In random oversampling, instances of the minority class are randomly selected and added to the training set until the majority and minority classes are balanced. 
- Accuracy: 0.67 of high risk applications were predicted and actually correct.<br/>
![](https://github.com/ashley-green1/Credit_Risk_Analysis/blob/main/Resources/Random_OverSamp_bal_acc_score.png)

- Precision: 0.01 of high risk applications were predicted and actually correct.<br/>
Recall: 0.70 of actual high risk applications identified correctly.<br/>
![](https://github.com/ashley-green1/Credit_Risk_Analysis/blob/main/Resources/Random_OverSamp_imb_class_report.png)


### SMOTE Oversampling

- In synthetic minority oversampling technique (SMOTE), the size of the minority is increased by new instances being interpolated.  That is, for an instance from the minority class, a number of its closest neighbors is chosen. 
- Accuracy: 0.66 of high risk applications were predicted and actually correct.<br/>
![](https://github.com/ashley-green1/Credit_Risk_Analysis/blob/main/Resources/SMOTE_bal_acc_score.png)

- Precision: 0.01 of high risk applications were predicted and actually correct.<br/>
Recall: 0.63 of actual high risk applications identified correctly.<br/>
![](https://github.com/ashley-green1/Credit_Risk_Analysis/blob/main/Resources/SMOTE_imb_class_report.png)


### Cluster Centroids Undersampling

- Cluster Centroilds identifies clusters of the majority class, then generates synthetic data points, called centroids, that are representative of the clusters.  The majority class is then undersampled down to the size of the minority class.
- Accuracy: 0.545 of high risk applications were predicted and actually correct.<br/>
![](https://github.com/ashley-green1/Credit_Risk_Analysis/blob/main/Resources/Cluster_Centroids_UnderSamp_bal_acc_score.png)

- Precision: 0.01 of high risk applications were predicted and actually correct.<br/>
Recall: 0.69 of actual high risk applications identified correctly.<br/>
![](https://github.com/ashley-green1/Credit_Risk_Analysis/blob/main/Resources/Cluster_Centroids_UnderSamp_imb_class_report.png)


### SMOTEENN Combination Sampling
- SMOTEENN combines the SMOTE and Edited Nearest Neighbors (ENN) algorithms. <br/>
SMOTEENN is a two-step process: <br/>
1.	Oversample the minority class with SMOTE.<br/>
2.	Clean the resulting data with an undersampling strategy. If the two nearest neighbors of a data point belong to two different classes, that data point is dropped<br/>
- Accuracy: 0.545 of high risk applications were predicted and actually correct.<br/>
![](https://github.com/ashley-green1/Credit_Risk_Analysis/blob/main/Resources/SMOTEENN_bal_acc_score.png)

- Precision: 0.01 of high risk applications were predicted and actually correct.<br/>
Recall: 0.72 of actual high risk applications identified correctly.<br/>
![](https://github.com/ashley-green1/Credit_Risk_Analysis/blob/main/Resources/SMOTEENN_imb_class_report.png)


### Random Forest Classifier
- The random forest algorithm will sample the data and build several smaller, simpler decision trees. Each tree is simpler because it is built from a random subset of features.
- Accuracy: 0.87 of high risk applications were predicted and actually correct.<br/>
![](https://github.com/ashley-green1/Credit_Risk_Analysis/blob/main/Resources/rf_acc_score.png)

- Precision: 0.03 of high risk applications were predicted and actually correct.<br/>
Recall: 0.70 of actual high risk applications identified correctly.<br/>
![](https://github.com/ashley-green1/Credit_Risk_Analysis/blob/main/Resources/rf_imb_class_report.png)


### Easy Ensemble Classifier
- The Easy Ensemble involves creating balanced samples of the training dataset by selecting all examples from the minority class and a subset from the majority class. Rather than using pruned decision trees, boosted decision trees are used on each subset, specifically the AdaBoost algorithm.
- Accuracy: 0.94 of high risk applications were predicted and actually correct.<br/>
![](https://github.com/ashley-green1/Credit_Risk_Analysis/blob/main/Resources/eec_acc_score.png)

- Precision: 0.09 of high risk applications were predicted and actually correct.<br/>
Recall: 0.92 of actual high risk applications identified correctly.<br/>
![](https://github.com/ashley-green1/Credit_Risk_Analysis/blob/main/Resources/eec_imb_class_report.png)


## Summary

While some of the above machine learning models outperform others, I recommend more research be done to identify machine learning models that yield better prediction success.

However, in a scenario where limited to the options above, I'd recommend the Easy Ensemble model.  Each of its scores reveal it most likely to accurately identify and predict high risk loan applications.  

It is important to note that its F1 score of 0.16 is significantly higher than the other models as highlighted in the Classification Reports. 
F1 score is a weighted average of the true positive rate (recall) and precision, where the best score is 1.0 and the worst is 0.0. 

There's usually a trade-off between sensitivity and precision and a balance must be struck between the two. A useful way to think about the F1 score is that a pronounced imbalance between sensitivity and precision will yield a low F1 score.  While 0.16 is low, it is up to 8 times higher than the other models in this case.  Hence, of the options above, most favored to predict high risk loan applications.

 
