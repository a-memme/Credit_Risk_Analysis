# Credit_Risk_Analysis
## Purpose 
Comparing different sampling techniques as well as machine learning models to determine which combinations predict credit risk best. As credit risk is an inherenly unbalanced classification problem (i.e good loans drastically outweigh bad ones) more intricate sampling techniques are needed in order to get at reliable results from the ML models. 

## Results 
The first four models used logistic regression with a number of different sampling techniques. The models and their respective statistics are as follows (classification report images can be referenced below each model):

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
