# Neural Network Charity Analysis

This week's project is related with Neural Networks and how it is used in the creation of a binary classifier, capable to predict whether applicants will be successful if funded by Alphabet Soup, a non-profit foundation interested on helping organizations that protect the environment and improve people's well-being.

## Pre-processing Data for a Network Model

A dataset with information about different organizations applying for funding is used in this project. The [dataset](https://githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Resources/charity_data.csv) contains information that can be considered noise or do not have a significant impact on their successfulnes. Therefore, we need to pre-proccess the data in two ways: Excluding columns considered irrelevant for our problem, and bucketing the columns that have too many unique values and that can add errors.

- Target column/feature: **IS_SUCCESSFUL**
- Features columns: **APPLICATION_TYPE**, **AFFILIATION**, **CLASSIFICATION**, **USE_CASE**, **ORGANIZATION**, **INCOME_AMT**, and **ASK_AMT**
- Removed columns: **EIN** and **NAME**. 
- Bucket columns: **APPLICATION TYPE** and **CLASSIFICATION**.

In addition, categorical columns are encoded (`One-hot Encoder`) and numerical values are standarized (`StandardScaler`).

## Compile, Train, and Evaluate the Model

Once the dataset has been processed, the Neural Network Model is designed. Figure 1 shows the structure of the model and its accuracy for the training and testing. 50 epochs were run for the training of the model.

![model](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/NNModel.png)

![training](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/TrainAccuracy.png)

![performance](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/Accuracy.png)
Figure 1. Neural Network Model and its performance.

Our model has three layers: 
- The input layer with 8 neurons, and *RELU* as activation function.
- The hidden layer with 5 neurons and again *RELU* as activation function.
- The ouput layer with 1 neuron and *Sigmoid* as activation function.

And an overall acuraccy of: 72,4%.  The code for this classification uses `TensorFlow` as the machine learning library and it is written in `jupyter notebook` (code is [here](https://github.com/LeidyDoradoM/Neural_Network_Charity_Analysis/blob/main/AlphabetSoupCharity.ipynb))

## Optimize the Model

To optimize the initial model and try to improve its performance to at least 75%.  Three different approaches are considered to get some improvement in its accuracy.

### 1. Dropping off noise columns:

The first approach considers to drop some additional columns that we think can be considered irrelevant for our classification problem. Thus, **ASK_AMT** and **SPECIAL_CONSIDERATIONS** are removed, as it is shown in figure 2. The overall performance of this optimized model is slightly improved to 72,8%. 

![Opt1](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/Optimazation1.png)

![training1](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/TrainAccuracy_Opt1.png)

![performance1](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/Accuracy_Opt1.png)
Figure 2. First approach to optimize the Neural Network Classifier and its performance.

### 2. Changing Model's Parameters:

In the second approach for optimizing our model, it is considered an additional hidden layer of neurons and additional neurons for each layer.  Figure 3 shows this changes in the structure of the model and its performance.

![Opt2](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/Model_Opt2.png)

![training2](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/TrainAccuracy_Opt2.png)

![performance2](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/Accuracy_Opt2.png)
Figure 3. Optimized Neural Network Model and its performance.

In this case, the overall performance is practically the same as the initial model.

### 3. Increasing training Epochs:

For the third intend to optimize the performance of our Neural Network model, we double the number of epochs in the training process. Figure 4 shows the performance for the training and testing.

![training3](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/TrainAccuracy_Opt3.png)

![performance3](https://raw.githubusercontent.com/LeidyDoradoM/Neural_Network_Charity_Analysis/main/Images/Accuracy_Opt3.png)
Figure 4. Performance of the optimized model with 100 epochs of training.

Unfortunately, the perormance of 72,6% does not improve the initial performance of our model, and consequently, neither reaches the goal of 75% of accuracy.

## Summary

A neural network classifier is designed, trained and tested here. In addition, three different ways to optimize the model were considered. Even with all the considered changes of removal of features, addition of layers and neurons in the model, and increasing of number of fitting epochs, the accuracy remains the same (~72%).  Since different changes in the model were considered, and they did not work as expected, a recomendation of using another kind of classification model is given. For example, a Random Forest has a similar accuracy performance than Deep Learning models but its interpretability is much higher.



