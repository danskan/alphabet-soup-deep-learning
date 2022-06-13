# Charity Funding Predictor

## Overview

Given a dataset of 34,000 organizations' historical requests for funding from Alphabet Soup over the years, develop a machine-learning algorithm that will predict an organizations' successful employment of capital received as a part of this charitable effort (1 for successful, 0 for unsuccessful).

* **EIN** and **NAME**—Identification columns
* **APPLICATION_TYPE**—Alphabet Soup application type
* **AFFILIATION**—Affiliated sector of industry
* **CLASSIFICATION**—Government organization classification
* **USE_CASE**—Use case for funding
* **ORGANIZATION**—Organization type
* **STATUS**—Active status
* **INCOME_AMT**—Income classification
* **SPECIAL_CONSIDERATIONS**—Special consideration for application
* **ASK_AMT**—Funding amount requested
* **IS_SUCCESSFUL**—Was the money used effectively

2. **Results**:

  * Data Preprocessing
    * The target variable for this model will be the **IS_SUCCESSFUL** column of the dataset
    * The main features used in this model are the **APPLICATION_TYPE**, **CLASSIFICATION**, **AFFILIATION**, *USE_CASE**, **ORGANIZATION**, **INCOME_AMT**, **ASK_AMT**, and **NAME** columns of the dataset
    * Specifically, because the **NAME** column had many orgs with multiple submissions, any org that had less than 3 submissions were placed into an "Other" group to simplify the data and reduce outliers
    * About a half dozen **CLASSIFICATION** and **APPLICATION_TYPES** counts accounted for the majority of the dataset, so the rest were placed into an "Other" column to simplify processing.
    * Irrelevant columns in the dataset were **EIN**, **STATUS**, and **SPECIAL_CONSIDERATIONS**
  * Compiling, Training, and Evaluating the Model
    * Given the pre-processing steps above, this model was able to achieve 79.51% accuracy and 0.5510 loss ratio with 400 nodes across 4 hidden layers through 40 epochs. The strategy here was to find the maximum accuracy in the minimum number of epochs. RELU was used to initialize the first node and all the hidden layers. Specifically, RELU was heavily used due to computational efficiency of those node (the passing of information forwards and backwards is done with a simple "IF" statement) making these layers able to process more data efficiently. SIGMOID was used on the output layer, due to it performing better when classifying things as a 1 or a 0.
    * Empirically-speaking, deeper networks with more layers tend to perform better in a wider variety of tasks, and although this task was simple compared to image recognition, the same approach was used to try and maximize efficiency. **It is important to note that efficiency was sacrificed for accuracy in this particular model.**
    * This model performed best when trained across 40 epochs.
    * Random Forest Classifier Met the standard with n_estimators of 64. It achieved 77.8% accuracy.

- - -

## Rubric

[Unit 21 - Deep Learning Homework Rubric - Charity Funding Predictor](https://docs.google.com/document/d/1SLOROX0lqZwa1ms-iRbHMQr1QSsMT2k0boO9YpFBnHA/edit?usp=sharing)

___
© 2021  Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.	
