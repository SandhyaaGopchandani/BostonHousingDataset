# Boston Housing Dataset: Crime Rate Prediction

Boston Dataset is a very popular dataset that consists of house prices in Boston. Each row represents a county and each variable represents some information related to that county. The dataset contains other information such as crime rate, age of house owners, nonretail business areas (INDUS), average number of rooms, pupil to teacher ratio of town, percentage of low income people in the area etc. This dataset is mostly used to predict the price of housing but I intend to predict the crime rate while using all other features as model parameters.

The is a small dataset consisting of 506 rows and 14 features. The features are continuous. So, it is a regression problem rather than a classification problem. This is a clean dataset that is there are no missing values. Features are on a different scale. Like Age variable ranges from 2 to 100. While Chas ranges from 0 to 1. So, there is a need to scale the feature set to get rid of any biases. In order to further explore the data, I used Pearson Correlation to check the association among variables in the dataset.

## Predictive Task

Feature selection is an important step in order to avoid overfitting in the models and to reduce the model complexity. It helps in making model with better accuracy while requiring less data. I am experimenting with various sklearn and techniques discussed in the class for feature selection.

#### Univariate Feature Selection

This method examines each feature individually and see the relationship of the feature with the response variable and assign a strength score to it. The higher the score is, the stronger the relationship is. This method is simple to understand but might not be the optimal for feature selection since it only considers each variable separately

#### Recursive Feature Selection

This method selects features by recursively considering smaller and smaller sets of features. Least important features are pruned from current set of features. It is recursively repeated on the pruned set until the desired number of features to select is eventually reached.

#### Random Forest Regressor

This method is based on impurity reduction. It uses variance as the measure to compute the importance of each feature. Though this method is robust, it is biased towards preferring variables with more categories.

For this assignment, I considered the features chosen from Random Forest method and train a model on the dataset. i-e RAD, MEDV and RM.

#### Normalization and standardization

Since the features in this dataset are on different scales, both normalization and standardization are techniques to rescale the feature set but there are some differences. From my study about these, it seems that standardization works better than normalization when comes to model building but it depends on the methods we are using. Also, some ML methods are robust to unscaled features. In this assignment, I build the same models first on normalized data and then on standardized data to see the difference in models’ performance.

#### Overfitting

To avoid the overfitting, I used cross-validation with 10 k-fold on 80% training data and reported the average mean squared error along with mean standard deviation of 10 k-folds. After that I fit a model on full 80% train data and tested it on unseen 20% dataset and reported the test set mean squared error.

#### Models’ Performance and Comparison:

I trained 3 Linear models and 4 non-linear models on the normalized and standardized data separately. The data contains three features selected after feature selection. I used Linear Regression, LASSO and Ridge Regression for linear models. And Decision Tree Regression, Support Vector Regression methods for non-linear models.

Linear Regression and Support Vector Regression (SVR) RBF seems to perform well from all of the methods. There is not drastic difference in Mean Squared Error (MSE) of these models but overall linear regression seems to perform better out of all the methods. The results table are reported in the python notebook. Moreover, normalized data seems to produce lower mean squared error as compared to models run on standardized data. Again, the performance is drastically different in both. Initially, I also trained these models on the unscaled data including all the features. The MSE of those models were much higher as compared to the models trained on scaled data with subset of features.

Jupyter notebook file contains all the code along with plots for exploratory data analysis and predictive models.