# Neural_Network_Charity_Analysis

## Overview

In this project, we were working on a dataset to create a binary classifier that is capable of predicting using 
machine learning and neural networks techniques. The data set used in this project is a CSV containing more
than 34000 organizations that have received funding from the Alphabet Soup over the years.

## Purpose
The purpose of this project was to create a binary classifier to predict whether applicants will be successful
if funded by the Alphabet Soup.

## Results

### Data Preprocessing

-   **What variable(s) are considered the target(s) for your model?**
    The "IS_SUCCESSFUL" column has been selected as the target variable for the model.

-   **What variable(s) are considered to be the features for your model?**
    The following columns have been considered as the features for the model:
    - APPLICATION_TYPE
    - AFFILIATION
    - CLASSIFICATION
    - USE_CASE
    - ORGANIZATION
    - INCOME_AMT
    - ASK_AMT
    - STATUS
    - SPECIAL_CONSIDERATIONS

    However, when I attempted to improve the performance of the model following columns were removed from the
    input feature set used above:
    - STATUS
    - SPECIAL_CONSIDERATIONS

-   **What variable(s) are neither targets nor features, and should be removed from the input data?**
    The following columns were removed from the input data:
    - EIN
    - Name

    However, when I attempted to improve the performance of the model following columns were removed from the
    input feature set used above:
    - STATUS
    - SPECIAL_CONSIDERATIONS

### Compiling, Training, and Evaluating the Model

-   **How many neurons, layers, and activation functions did you select for your neural network model, and why?**

    Following parameters were used for the base model:
-   Number of neurons: 8, 5, and 1 neurons respectively for layer1, layer2 and layer3
-   Number of layers: 2 hidden layer + 1 output layer
-   Activation functions: `relu`, `relu` and `sigmoid` respectively for layer1, layer2 and layer3

    I chose the above activation function combinations as relu converges fast and requires fairly less amount of memory.

-   **Were you able to achieve the target model performance?**

    No, I was not able to achieve the target model performance.

-   **What steps did you take to try and increase model performance?**

    The following steps were taken to improve the model performance:

-   I observed that the columns 'STATUS' and 'SPECIAL_CONSIDERATIONS' was not having enough data for both classes of target,
    so I tried dropping them in each of my optimization attempts.

-   I tried to decrease the number of neurons from 8 to 3 in the first layer.

-    I tried to change the # of bins in the 'APPLICATION_TYPE' and 'CLASSIFICATION' columns so as to distribute data points equally amongst
    bins.

-   I even tried to change the activation functions from `relu` to `leaky_relu` but that did not help and I did not
    record those observations in my attempts.

-   I also tried increasing the number of neurons from 4 to 8 in the second layer but that did not help and I did not
    record those observations in my attempts.

    ## Summary

    We used the `accuracy` metric to measure the performance of the model. The maximum accuracy of the model that was achieved in my attempts was
    `0.7288`. The number of input parameters considered for the model seem to be correct and it is just that the parameters used to compile the model
    can be tuned a little more to achieve higher performance.

    We can also make use of a `random forest` model for this binary classification. I recommend to use a random forest model as it adds additional
    randomness to the model while growing the trees instead of searching for the most important feature while splitting the node it searches for the
    best feature among a random subset of features. This results in a wide diversity that generally results in a better model. 