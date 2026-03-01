# Task 1 : Matlab Onramp

## Aim:

To do the course 

## Learnings

Matlab is a math platform wherein a person can do advanced math and programming for solving 
This course was about Character recognition on the MNIST dataset

The coursework stressed on major ML workflow whilst training a model like
- Loading the dataset
- Cleaning the dataset
- Scaling data before using
- Training the model
- Evaluation of Scores
- Hyper Parameter Tuning

  My matlab account crashed so i couldnt put the certificate.

# Task 2 :  Publish Your Own Dataset

## Aim

To craft a synthetic dataset of choice using python functions and libraries.

## Learning 

To create a synthetic dataset, the library **Faker** was used. Faker has dedicated functions to generate custom required feature entries like credit card,ID,aadhar card number,transaction id and etc.\
The type of dataset done by me was a fake transaction which contained some features for fraud detection.

### Steps Taken:
- Installed faker using 'pip install faker'
- Made a list of all required features like "Transaction_ID,Account_ID,Transaction_Date,Transaction_Amount,Merchant_Category,Transaction_Type,Location,is_fraud".
- Used Faker and Random to gather synthetic values
- Appended everything using a loop for total 50 data entries
- Converted to DataFrame and exported

Here's my notebook: [Click Here](https://github.com/hrishikesh-rao/Marvel-Level-1/blob/main/Synthetic_Datset.ipynb)

---

# Task 3 : Data Detox - Data Cleaning using Pandas

## Aim 

To clean the given dataset using Pandas.

## Learning 

**Pandas** is an open source library in python which is mainly used for data manipulation.
It is one of the building blocks of *Machine Learning* as when we need to deal with data like cleaning, extracting or duplicating **Pandas** are extremely helpful.

**Pandas** often abbrieviated as pd are built on *NumPy*. Pandas provide high-performance, fast, easy-to-use data structures, and data analysis tools for manipulating numeric data and time series. Most of the functions in Pandas are coded in **C/C++** as **C/C++** is very fast and most of the computational logic occurs there and we get to use the easiness of Python

### Steps Taken:

- Loaded the dataset and inspected it using the .read_csv() function.
- Noticed some common errors in the first 200 entries of every features.
- Used str.replace() function to correct typos.
- Dropped duplicates.
- Droppped Null values in some features.
- Imputed values for some features using .fillna() function.

Here's my notebook : ![My Notebook](https://www.kaggle.com/code/hrishikeshsrao/datadetox/edit)

---

# Task 4 :  Anomaly Detection

## Aim
To implement 2 anomaly detection methods one using statistical approach and other using Unsupervised ML


## Learning 

Anomaly detection is the technique of using algorithms to figure out the extreme outliers using trends and variations in the data. Anomaly detection is done based on viewing the data and defining as whats normal and whats considered  abnormal. Based on this i have applied two approachs

### **1. IQR[Inter Quartile Range]:**

IQR calculates the Lower edge of the typical behavior, Range and the higher edge of the typical behavior by defining whats larger than 25% and 75% of the total data respectively,thereby defining ranges.
Now based on this Range a threshold or a defining boundary can be set as to what is acceptable and what goes beyond limits.

A hyperparameter is used usually taken as 1.5 for defining the lower and upper bounds.

This is used in the numerical features like'data_accessed','files downloaded' and 'duration'.

Later the anomalies are flagged if the entry value of that particular feature exceeds the threshold.

The 'OR' logic is used to flag combined anomalies

Thereby figuring the top 5 anomalies.

### **2. Isolation Forest:**

This is a type of Unsupervised ML approach(there is exactly no target label).In this algorithm the core idea is that anomalies are easier to locate as they are usually the extereme outliers and occur in fewer splits of shallow branches(wrt to a decision tree branches). Here the feature is picked randomly and in thaat feature a random value is split randomly, and since its a forest,it is implemented using many trees.

Anomalies are found out using the shortest path possible.

A contamination clause is associated while import the model such that the model assumes a small number of anomalies to set the threshold. It is basically a decision control boundary marking.It is taken to be 0.05.

Model flags 1 as normal and -1  as anomalous.

### Steps Taken:

- Data is loaded.
- It is cleaned and scaled using the preprocessing function of sklearn.
- IQR is implemented
- Isolation Forest is implemented
- Both are compared
- The top 5 suspects are found

Heres my notebook: [Click Here](https://github.com/hrishikesh-rao/Marvel-Level-1/blob/main/Anomaly_Detection.ipynb)

---


# Task 5 :  Logistic Regression from Scratch

## Aim

To understand and implement Logistic Regression from scratch on the framingham heart disease dataset.

## Learning 

**Understanding Classication Algorithm :**

A classification algorithm is such an algorithm which classifies data on the basis of a condition in to groups

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

  Heres my notebook: [Click here](https://github.com/hrishikesh-rao/Marvel-Level-1/blob/main/Logistic_Regression%20(1).ipynb)
---


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

Heres the plot:

![](https://github.com/hrishikesh-rao/task/blob/main/image_2026-03-01_112848863.png)
Heres my notebook [Click Here](https://github.com/hrishikesh-rao/Marvel-Level-1/blob/main/SVM.ipynb)

---

# Task 7: Decision Trees from Scratch

## Aim:

To understand and build a **Decision Tree** from scratch using the utrecht fairness dataset and perform the fairness analysis

## Learnings:

### About Decision Trees:

Decison Trees are Supervised ML Algorithm which can be used for Classification or Regression purposes.

Here the Decision Tree is a classifier which predicts if a person gets the job or not.

**Understanding Entropy**:

Entropy or also called the Expected Value, which is used to measure the uncertainity or the impureness of the classified node.\
If all samples belong to one class,low entropy and if samples are mixed then entropy is high among the low nodes.\
Our aim is to have low entropy amongst classes,i.e have all related smaples under a class.\
Simplest algorithms are Gini Impurity Method which assigns an impurity value to all classes to determine the root node for the decision classifier based on the lowest impurity score.\
The one which is used here is the ID3 Algorithm which stands for Iterative Dichotomiser 3\
This is the conventionally used formula for calculating the entropy

![](https://github.com/hrishikesh-rao/task/blob/main/Screenshot%202026-03-01%20130215.png?raw=true)

P(i) is the probability of class.\
Base two is used since there are two outcomes which is hired(encoded as 1) or not hired(encoded as 0) 

**Understanding Information Gain**:

Information Gain is parameter which is used to determine how much the entropy reduces after a split.\
Information Gain is calculated by total entropy of the dataset minus weighted entropy after the split per feature .\
Weights are usually the probabilty associated to that dataset.\
Formula for Information Gain is given by

![](https://github.com/hrishikesh-rao/task/blob/main/image_2026-03-01_180126948.png?raw=true)

**ID3**:

The ID3 algorithm is built on entropy and information gain\
Inorder to proceed , we must calculate the total entropy of the dataset and entropy after split per feature.\
Next we determine Information gain of that feature and compare.
The feature with the max information gain is chosen as the root node.\
This procedure is repeated keeping the root node's entropy in place of the total entropy and done until no features remain.\
Acts very simiilar to a recursive function.


### Steps Taken:

- Loaded and Cleaned the dataset.
- Split the ages ranges, and did the overall train_test_split
-  Built ID3 algorithm
- Did metric evaluation.
- Did fairness analysis

Heres my notebook :[](https://github.com/hrishikesh-rao/Marvel-Level-1/blob/main/Decision_Trees.ipynb) 
---

# Task 8: KNN Ablation Study

## Aim

To understand and implement knn using sklearn to the Wisconsin breast cancer dataset

## Learnings:

KNN or Kth nearest neighbour is a type of Supervised ML algorithm which is used to classify a data point by the using the vicinity of the other data points.

The proximity of the test data point with t respect to a group or related data points decides its nature and character

The K in the KNN is a hyper parameter and is the measure of number of data points to be considered for determine the character of the data point.

Bias-Variance trade off occurs here as well since based of K value either bias is high or 

**Euclidean distance and Manhattan distance:**

Euclidean distance is the straight line distance between two points. Uses squares and square roots to penalise large differences more.

Manhattan distance is the sum of absolute differences of features.

Euclidean is used here because it produces a shorter distance path from the test data point and the data point already present and it’s also better for optimisation.

Class Imbalance also occurs here since one parameter can have more samples and can be dominating, it can be solved by us g weighted balance of classes.

### Steps Taken

- Dataset is loaded,cleaned and scaled
- Id is dropped and diagnosis is encoded as 0 or 1.
- The hyper parameter K is chosen as 5.
- Ablation study is performed whilst removing one feature at a time.
- Training is done

Heres my notebook [Click Here](https://github.com/hrishikesh-rao/Marvel-Level-1/blob/main/knn_ablation.ipynb)

---

# Task 9: Evaluation Metrics

## Aim:

To evaluate five pretrained machine learning models saved as .pkl files using the Iris dataset, compare their performance using appropriate classification evaluation metrics, and identify the best-performing model.

## Learnings:

**Understanding Joblib**:

Joblib is a Python library used for efficient serialization and deserialization of Python objects. In machine learning, it is commonly used to\
-Save trained models into .pkl (pickle) files.\
-Load trained models without retraining.\
-Handle large NumPy arrays efficiently compared to standard pickle.

**Evaluation Metrics**:

F1 score, Accuracy,Precsion and Recall are all derived from Confusion Matrix.\
Confusion Matrix is the Matrix derived from 4 elements 

![](https://github.com/hrishikesh-rao/task/blob/main/image_2026-03-01_224240054.png?raw=true)

True Positive,False Positive,False Negative and True Negative are the 4 parameters required for calculation of evaluation metrics.

1.**Accuracy**: Measures overall correctness\
**(TP+TN)/(TP+TN+FP+FN)**

2.**Precision**: Out of all positive samples predicts actual postives,Penalises False Positives\
**(TP)/(TP+FP)**

3.**Recall**: Out of actual positive samples,how much did model predict correctly,Penailses False Negatives\
**(TP)/(TP+FN)**

4.**F1 Score**: Penalises imbalances.\
**2(Precison*Recall)/(Precision + Recall)**

5.**R^2**: Based on prediction error distance\
Measure closeness to continuous target values 

### Steps Taken:

- Load the iris dataset 
- Load the Models(.pkl) using Joblib
- Dropped the id
- Stratify ensures class imbalance doesnt occur while doing train_test_split()
- Train the models
- Evaluate Metrics
- Compare the models

Heres my notebook [Click Here](https://github.com/hrishikesh-rao/Marvel-Level-1/blob/main/Evalutation_Metrics.ipynb)

---

