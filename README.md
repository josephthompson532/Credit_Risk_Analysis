# Credit_Risk_Analysis


## Purpose
The purpose of this analysis was to experiment with creating a machine learning model that would most accurately predict credit risk. 

## Overview
Several methods were tried. Firstly I employed several different over and undersampling techniques using a Logistic Regression to see if they would make a substantial difference. The techinques included random over sampling and SMOTE for oversampling high risk credit cases and then Cluster Centroid for undersampling. I also used a combination of both with SMOTEENN.

After this I used a Balanced Random Forest Classifier and an AdaBoost algorithm to model the algorithm.

## Results
### Logistic Regression with Random Over Sampling
balanced accuracy score: .659
precision: .01
recall: .65

### Logistic Regression with SMOTE
balanced accuracy score: .643
precision: .01
recall: .60

### Logistic Regression with Cluster Centroid
balanced accuracy score: .611
precision:.01
recall:.66

### Logistic Regression with SMOTEENN
balanced accuracy score: .652
precision: .01
recall: .64

### Balanced Random Forest Classifier
balanced accuracy score: .681
precision: .05
recall: .41

### AdaBoost
balanced accuracy score: .883
precision:.05
recall:.86

## Summary
When predicting credit risk, it is more import to maximize recall than precision. This is because even if the model does misclassify fraud in some cases, I should be able to sort out at relatively low cost whether each case is really fraud. However, it is imperative that we catch EVERY instance of fraud that we can, because the cost of missing a case of fraud is high. 

Out of all of the results the AdaBoost performed the best across all three metrics, particularly recall. However, This model is not ready for deployment because its precision is so absurdly low that it doesn't really help us meaningfully narrow down possible cases of fraud. Despite catching 86% of the cases of fraud, there is still a pool of 7690 cases of positives when I include the false positives due to the .05 precision rate. This is an enduring issue throughout all of the models. The precision is too low and it muddles the results that we do catch.

Unfortunately, none of these models would be ready for deployment. I need to find a way to get precision up, while not sacrificing recall.