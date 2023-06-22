# Machine-Learning-project

This pdf explains what I analyse and result of the project.  

[Project README.pdf](https://github.com/Kumoichi/Machine-Learning-project/files/10494901/Project.README.pdf)



Rice Type Classification Dataset
This repository contains a dataset for classifying rice into two types: Jasmine and Gonen. The dataset consists of 18,185 instances and 12 features. The features include numeric values such as area, major axis length, minor axis length, eccentricity, convex area, equivalent diameter, extent, perimeter, roundness, and aspect ratio. The dataset is provided in CSV format and has a size of 910 KB.

Dataset Details
Number of instances: 18,185
Number of features: 12
Features:
id: Unique identifier for each instance
Area: Area of the rice sample
MajorAxisLength: Length of the major axis of the rice sample
MinorAxisLength: Length of the minor axis of the rice sample
Eccentricity: Eccentricity of the rice sample
ConvexArea: Convex area of the rice sample
EquivDiameter: Equivalent diameter of the rice sample
Extent: Extent of the rice sample
Perimeter: Perimeter of the rice sample
Roundness: Roundness of the rice sample
AspectRation: Aspect ratio of the rice sample
Why Use this Dataset for a Machine Learning Project?
This dataset is well-suited for a machine learning project for several reasons:

Sufficient Data: The dataset contains a large number of instances (18,185), which provides enough data for analysis. Having an adequate amount of data improves the accuracy of machine learning models.

Numeric Features: All the features in the dataset are numeric values, making it suitable for regression analysis. The use of numeric features allows for clear identification of feature correlations.

No Missing Values: The dataset is complete and does not contain any missing values. This aspect contributes to accurate analysis, as missing values can introduce biases or affect the quality of results.

Dataset Links
Rice Type Classification Dataset
Project Link on Google Colab
Data Analysis
The following analyses have been performed on the dataset:

Regression
Finding correlation between ConvexArea and MajorAxisLength (row 5, column 2) using a heatmap.
Finding correlation between ConvexArea and other features: Area, MajorAxisLength, EquivDiameter, Extent, Roundness, and AspectRation.
Classification
Comparing all features for classification.
Specifically comparing Extent and Eccentricity for classification purposes.
Experimental Methods
Hypothesis
For regression analysis, it is hypothesized that RandomForestRegressor will yield the best results, followed by simple LinearRegression and PCA. This hypothesis is based on the assumption that RandomForestRegressor generally provides better scores. LinearRegression with PCA may reduce the dimension but could result in a lower score.

For classification, it is hypothesized that KNN and Logistic Regression will produce similar results, but cross-validation may lead to lower accuracy due to the avoidance of overfitting. The goal is to create a model that can predict future values accurately.

Regression Methods Used
Simple LinearRegression
PCA
RandomForestRegressor
DecisionTree
Regulation (using Lasso)
Classification Methods Used
KNN
Logistic Regression
SVM
Cross-validation
PCA
Decision Tree
Results & Analysis
Regression Results
Correlation between ConvexArea and MajorAxisLength: Moderate correlation with a score of 0.3616 using simple LinearRegression.
Correlation between ConvexArea and multiple features (Area, MajorAxisLength, EquivDiameter, Extent, Roundness, and AspectRation): High correlation with a score of 0.9865 using simple LinearRegression.
Comparing simple LinearRegression and RandomForestRegressor:

X = MajorAxisLength, Y = ConvexArea
Simple LinearRegression score: 0.3616
RandomForestRegressor score: 0.0729
RandomForestRegressor performs worse due to having only one feature (X). It usually returns better results when multiple features are present.
Comparing simple LinearRegression, PCA, and RandomForestRegressor:

X = Area, MajorAxisLength, EquivDiameter, Extent, Roundness, AspectRation; Y = ConvexArea
Simple LinearRegression score: 0.9865
PCA score: 0.9849
RandomForestRegressor score: 0.99754
The hypothesis is confirmed, as RandomForestRegressor achieves the best result, followed by simple LinearRegression and PCA. RandomForestRegressor's random feature selection contributes to higher accuracy.
Decision Tree
Decision tree with 4 levels of depth:
Top
Left
Right
The least number of samples (35) is observed when the value is 9028.343.
The greatest number of samples (1868) is observed when the value is 6305.36.
The decision tree produces only 16 unique values.
Regulation
Lasso regulation is used.
Score: 0.9871, indicating that it is not the best score.
Regulation is employed to prevent overfitting. Although it may yield worse results, it is considered a better model as it can predict future values more accurately.
Classification Results
X = Extent, Eccentricity; Y = Class
Classification accuracy using KNN: 0.9587
Classification accuracy using Logistic Regression: 0.9583
Classification accuracy using SVM: 0.9598
The results obtained from KNN, Logistic Regression, and SVM are almost the same.
Cross Validation
X = Extent, Eccentricity; Y = Class
Accuracy achieved through cross validation: 0.9584
Cross validation is used to create a model that avoids overfitting and predicts unknown future values accurately. The achieved accuracy demonstrates the effectiveness of this approach.
PCA
X = Extent, Eccentricity; Y = Class
First dimension explains 0.9302 of the variance, while the second dimension explains 0.06970.
Adding AspectRation:
X = Extent, AspectRation, Eccentricity; Y = Class
First dimension explains 0.9523 of the variance, while the second dimension explains 0.0472.
AspectRation increases the importance of the first dimension.
Decision Tree Analysis
Decision Tree:
Top
Left
Right
The decision tree analysis suggests that when Extent and Eccentricity are low, there is a higher probability of classifying the data as Gonen, as there are more Gonen samples on the left side and more Jasmin samples on the right side.
