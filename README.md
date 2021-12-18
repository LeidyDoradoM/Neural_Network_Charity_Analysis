# Neural Network Charity Analysis

This week's project is related with Neural Networks and how it is used in the creation of a binary classifier, capable to predict whether applicants will be successful if funded by Alphabet Soup, a non-profit foundation interested on helping organizations that protect the environment and improve people's well-being.

## Pre-processing Data for a Network Model:

A dataset with information about different organizations applying for funding is used in this project. The [dataset](https://githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Resources/charity_data.csv) contains information that can be considered noise or do not have a significant impact on their successfulnes. Therefore, we need to pre-proccess the data in two ways: Excluding columns considered irrelevant for our problem, and bucketing the columns that have too many unique values and that can add errors.
- Removed columns: **EIN** and **NAME**. 
- Bucket columns: **APPLICATION TYPE** and **CLASSIFICATION**.

In addition, categorical columns are encoded (`One-hot Encoder`) and numerical values are standarized (`StandardScaler`).

## Compile, Train, and Evaluate the Model:

![model](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/NNModel.png)

![training](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/TrainAccuracy.png)

![performance](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/Accuracy.png)

## Optimize the Model:

### 1. Dropping off noise columns:

![Opt1](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/Optimazation1.png)

![training1](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/TrainAccuracy_Opt1.png)

![performance1](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/Accuracy_Opt1.png)

### 2. Changing Model's Parameters:

![Opt2](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/Model_Opt2.png)

![training2](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/TrainAccuracy_Opt2.png)

![performance2](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/Accuracy_Opt2.png)

### 3. Increasing training Epochs:



![training3](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/TrainAccuracy_Opt3.png)

![performance3](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/Accuracy_Opt3.png)
## Summary


