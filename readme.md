# Boston Housing Price Dataset

Boston Dataset is a very popular dataset that consists of house prices in Boston. Each row represents a county and each variable represents some information related to that county. The dataset contains other information such as crime rate, age of house owners, nonretail business areas (INDUS), average number of rooms, pupil to teacher ratio of town, percentage of low income people in the area etc. This dataset is mostly used to predict the price of housing but I intend to predict the crime rate while using all other features as model parameters.

## Data Exploration:

The is a small dataset consisting of 506 rows and 14 features. The features are continuous. So, it is a regression problem rather than a classification problem. This is a clean dataset that is there are no missing values. Features are on a different scale. Like Age variable ranges from 2 to 100. While Chas ranges from 0 to 1. So, there is a need to scale the feature set to get rid of any biases. In order to further explore the data, I used Pearson Correlation to check the association among variables in the dataset.