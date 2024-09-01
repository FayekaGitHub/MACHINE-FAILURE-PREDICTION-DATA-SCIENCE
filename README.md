# Machine Failure Prediction

## Overview
This project focuses on predicting machine failure using a dataset of operational machine data.
It involves preprocessing the data, engineering features, selecting the most relevant features, and training a model to predict machine failure.

## Feature Engineering
### Temperature Difference
A new feature representing the difference between process temperature and air temperature is created. 
This feature can help in understanding the temperature dynamics affecting the machine.
### Torque per RPM
The torque per RPM feature is computed by dividing the torque by the rotational speed. 
This feature helps in analyzing the efficiency and load on the machine.
### Rolling Mean of Rotational Speed
A rolling mean of the rotational speed with a window size of 3 is calculated to smooth out fluctuations and capture the trend in rotational speed over time.
### Handling Missing Values
Missing values in the rolling mean feature are addressed by filling them with the first valid value found in the dataset.
This step ensures that the dataset remains complete and usable for model training.

## Feature Selection
### Skewness Correction
Features with high skewness are transformed to approximate a normal distribution. 
This step helps in improving the performance of machine learning models by ensuring that features are more normally distributed.
### Feature Scaling
Features are standardized to have a mean of 0 and a variance of 1.
This normalization is crucial for many machine learning algorithms as it ensures that all features contribute equally to the model.

## Model Training and Evaluation
### Training the Model
A RandomForestClassifier is trained with hyperparameter tuning to find the optimal model settings.
GridSearchCV is used to explore various combinations of hyperparameters to improve model performance. 
The trained model is then evaluated on a test dataset to assess its accuracy and generate performance metrics.

