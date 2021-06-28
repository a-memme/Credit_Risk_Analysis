# Credit_Risk_Analysis
## Purpose 
Comparing different sampling techniques as well as machine learning models to determine which combinations predict credit risk best. As credit risk is an inherenly unbalanced classification problem (i.e good loans drastically outweigh bad ones) more intricate sampling techniques are needed in order to get at reliable results from the ML models. 

## Results 
The first four models used logistic regression with a number of different sampling techniques. The models and their respective statistics are as follows (classification report images can be referenced below each model - derived from credit_risk_resampling.ipynb and credit_risk_ensemble.ipynb respectively):

### Random Oversampling
- accuracy: 0.64
- high risk precision: 0.01
- high risk recall: 0.66

<img width="877" alt="random_stats" src="https://user-images.githubusercontent.com/79600550/123694577-7f89e600-d827-11eb-8676-8380f031cb7a.png">

### SMOTE Oversampling 
- accuracy: 0.65
- high risk precision: 0.01
- high risk recall: 0.61

<img width="854" alt="smote_stats" src="https://user-images.githubusercontent.com/79600550/123694653-97fa0080-d827-11eb-95c1-e93210266f54.png">

### Cluster Centroids Undersampling 
- accuracy: 0.54
- high risk precision: 0.01
- high risk recall: 0.69

<img width="846" alt="cluster_stats" src="https://user-images.githubusercontent.com/79600550/123694757-b6f89280-d827-11eb-9407-5d79223fc754.png">

### SMOTEEN Over and Under Sampling
- accuracy: 0.64
- high risk precision: 0.01
- high risk recall: 0.71

<img width="836" alt="smoteen_stats" src="https://user-images.githubusercontent.com/79600550/123694823-ced01680-d827-11eb-8c0c-da944ff69fb1.png">

The final two instances are two different types of machine learning models, that are both used to help reduce bias and possibility of overfitting data: 

### Balanced Random Forest Classifier 
- accuracy: 0.79
- high risk precision: 0.03
- high risk recall: 0.70

<img width="807" alt="balanced_forest_stats" src="https://user-images.githubusercontent.com/79600550/123694920-eeffd580-d827-11eb-89f3-195b23fb817a.png">

### Easy Ensemble AdaBoost Classifier 
- accuracy: 0.93
- high risk precision: 0.09
- high risk recall: 0.92

<img width="824" alt="easy_ensemble_stats" src="https://user-images.githubusercontent.com/79600550/123695009-09d24a00-d828-11eb-9e4d-51768efa3d2d.png">

## Summary
 The first four models focused on different sampling techniques with use of logistic regression to help account for the inherent class inbalances in credit risk categorizing, while the final two used two different types of models to help account for biases. Oversampling techniques help scale the under-represented class when training the data, while undersampling techniques use the opposite approach by reducing the scale of the over-represented class. 

Given the above statistics, the value of most importance in this circumstance is the recall/sensitivity score. Although precision and accuracy are also of importance, their values are not necessarily indicative of the model's reliability in judging all high risk circumstances. To elaborate, a high precision score means that the model is right most of the time. However, given that credit risk is inherently imbalanced - i.e that there are way more low risk circumstances than high - this could simply mean that the model detects each low risk instance correctly, but never detects a high risk one. In addition, simply looking for a good high-risk precision score indicates reliability in the instances that are considered high-risk, but doesn't account for false-negatives (i.e detecting low risk instances when they really are high). 

Thus, sensitivity is the best metric when dealing with credit risk - the aim is to find a model that can predict all/almost all of high-risk circumstances, even if there is a high false-positive rate. Given the above stats, the Easy Ensemble AdaBoost Classifier yields the highest recall rate at 0.92 - meaning that 92% of high risk cases were actually categorized as high risk. Although the precision score for high risk is quite low (0.09), this simply means that there is a large rate of false positives (i.e that many circumstances were labelled high risk when they were actually low). This may not be the most ideal circumstance, however, the ramifications of a false high-risk categorization are much less detrimental to a peer-to-peer lending services company than a false low-risk categorization. Furthermore, even with an objectively low precision score, the Easy Ensemble model still scored highest in all categories in comparison to all other models.


