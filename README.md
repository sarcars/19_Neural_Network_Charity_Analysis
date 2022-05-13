# 19_Neural_Network_Charity_Analysis

## Overview of the analysis:
Using machine learning and neural networks, features in the provided dataset (a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years)  were used to create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.

## Resources
- Data Source: charity_data.csv
- Software: Jupyter Notebook 6.4.5

## Results: 

#### Data Preprocessing
- What variable(s) are considered the target(s) for your model?
  - Target for the model would be the `IS_SUCCESSFUL` column 
- What variable(s) are considered to be the features for your model?
  - Features of the model would be the `APPLICATION_TYPE`,` AFFILIATION`, `CLASSIFICATION`, `USE_CASE`, `ORGANIZATION`, `STATUS`, `INCOME_AMT`, `SPECIAL_CONSIDERATIONS`, and `ASK_AMT` 
- What variable(s) are neither targets nor features, and should be removed from the input data?
  - the columns `EIN` and `NAME` contain identification data and were removed from the input data
#### Compiling, Training, and Evaluating the Model
- The original deep-learning neural network is made up of two hidden layers.  First hidden layer has 80 neurons and the second has 30 neurons
- The original model achieved a 72.6% Accuracy measure, which is below the target model performance of over 75%
![Original Accuracy](/images/1staccuracy.png)

- Hoping to improve the performance, I took the following steps:
  - I applied bucketing to the ASK_AMT feature (which had the largest amount of unique numbers of all the features)
![ASK_AMT buckets](/images/ASK_AMT.png)

  - I increased the number of neurons on the hidden layers (to 100 and 50 neurons) 
  - I added a third hidden layer (with 25 neurons)
![Optimized Hidden Layer](/images/hiddenlayer.png)

None of the steps optimization steps improved the Accuracy, and in fact the Accuracy went down slightly (to 72.58%)
![Accuracy after Optimization](/images/OptimizAccuracy.png)


## Summary: 
The deep learning neural network model did not achieve the over 75% accuracy target.  Since we are looking for a classification (funded or not funded) perhaps a supervised machine learning model such as  decision tree might be useful in this situation
