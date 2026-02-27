# Task 5 :  Logistic Regression from Scratch

## Aim

To understand and implement Logistic Regression from scratch on the framingham heart disease dataset.

## Learning 

**Understanding Classication Algorithm :**

A classification algorithm is such an algorithm which classifies data on the basis of a conidtion in to groups

Logisitc Regression is such a type of classification algorthim spits out a probabilisitc valule of 0.00 or 1.00 based on the given threshold. If the given threshold is 5 lets say on a scale of 1 to 10, then the predicted vallue(lets say 7) would be considered 1 if value>5->1 and 0 if its lesser than 5.

**How different its from Linear Regression:**

Linear Regression perform gradient descent on the loss function and gives a numerical value of any range as the final output.

Logisitic Regression on the other hand determines where the final output of Linear Regression lies based on the threshold set.

The only difference is that the linear model(y=wx+b) is fed to a sigmoid function on the which gradient descent is performed

**Need of Different Loss Function:** 

A separate Loss function is employed as MSE fails to Penalise the difference in data point and the predicated value during the difference with a higher magnitude of error, whereas the new loss function(Negative Log Loss Function) is successful in penalising the error in the distance with a higher magnitude. 

Like Linear Regression the calculation of optimal parameters(w,b) takes place using optimization and gradient descent.

### Steps Taken:

- Dataset is loaded and cleaned using pandas
- Data is scaled using the preprocessing function from sklearn.
- The logistic Regression Model is implemented from scratch
- Sklearn's Model is also imported
- The performance parameters are compared
