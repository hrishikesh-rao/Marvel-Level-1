# Task 6 : SVM  

## Aim

To understand and implement an SVM on a wine quality dataset.

## Learning:

The Support Vecotr Machine or SVM is a Supervised ML algorithm which is used to find for classification or regression,is used for finding the optimal boundary to separate classes.

The main principle of the SVM is to find a hyper plane(A plane of many dimensions) which can maiximise the distance bewteen the classes an minimise the number of missclassifications(extreme outliers).

SVM works on this principle of Soft Margins where a certain amount of missclasifications are allowed.

This control of decision boundary is guarded by a Regularization/Hyperparameter called as C.

C is the parameter whichs controls with what magintude should the missclassification be penalised,initially we take C=2.

If a large C value is taken stricter the boundary,Small C is taken the more tolerant the boundary.This is the bias-variance tradeoff
Large C causes error due to more sensitive to data.
Small C causes error due to oversimplification.

C is found using cross validation, a method which is used to determine a hyper paramter value uusing various trials.

**Kernels:** They map data into a higher dimension if the decision boundary isnt linearly separated.

Here the kernel used is a rbf(radial basis function). This is creates a very flexible non linear boundary.

**Class Imbalance:** Means unequal number of samples per feature,was solvedby introducing a balanced class weight.

### Steps Taken:
- Loaded,Cleaned and scaled the data
- Implemented SVM using sklearn
- Injected noise
- Found accuracy wrt noise injected.
- Did hyper parameter tuning using cross validation.