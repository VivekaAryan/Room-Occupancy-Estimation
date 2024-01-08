# Room Occupancy Estimation

## Introduction

Estimating occupancy can be beneficial in many fields. A few possible applications include energy management through optimising heating, ventilation and air conditioning systems, crowd management, and safety and security by detecting unusual activity patterns in public buildings such as libraries, museums, train stations, airports, hospitals, and homes.

The project aims to estimate the occupancy in a room in the event of a “break and enter”. It is a classification task. Data from multiple non-intrusive environmental sensors like temperature, sound, CO2, and PIR (motion detection) were used to estimate occupancy without a computer vision solution. The structured data, of 10129 instances and 16 variables, were collected over 4 days in a controlled manner. The target occupancy varies between 0 and 3 people. A detailed description of variables is given in the table below.

## Data Pre-processing

Real-world data is always messy. The phrase “garbage in, garbage out” is often quoted when building a machine learning model. This means that if you use dirty data, you will end up with a poor model because machine learning models often perform better with cleaned datasets. According to Shah (2020), in the data pre-processing section of “A Hands-on Introduction to Data Science” (Chapter 2, Section 2.4, pp. 47-58), the main steps in data pre-processing are Data Cleaning, Data Integration, Data Transformation, Data Reduction and Data Discretization. 
The dataset is free of any missing data. After dropping the 'Date' and 'Time' columns, we noticed a few duplicate values that were not present before. These columns were not dropped as they are independent readings and not duplicates. From univariate outlier analysis using violin plots, we noticed outliers in light and CO2 variables which are considered typical readings. These values were not removed as excluding these values solely based on their extremeness could lead to the loss of valuable information. To reduce the processing and storage capacity, we reduced the decimal places of the “CO2 slope variable” to two decimal places. Finally, the light variables were dropped to address the problem statement.

Figure 1: Univariate outlier analysis using violin plots.
![image](https://github.com/VivekaAryan/Room-Occupancy-Estimation/assets/52493029/6c8cb73d-47ed-4543-b701-8f5170e2de53)

## Models
All single models were applied to our dataset to estimate room occupancy. The predictions of all the models with their hyperparameters tuned, were evaluated using the test set. The dummy classifier was used as a benchmark to compare the performance of other models. The two best models are Random Forest Classifier with 99.56% accuracy and MLP with 98.33% accuracy. KNN, decision trees, and SVM with non-linear kernel models also gave significant accuracy.

Table 2: Performance of all single models
![image](https://github.com/VivekaAryan/Room-Occupancy-Estimation/assets/52493029/e8ed2ae2-0190-406d-8abf-4881e117581d)





 


