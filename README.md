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

Here's my notebook: [Click Here](https://github.com/hrishikesh-rao/Marvel-Level-1/blob/main/Synthetic_Datset.ipynb?raw=true)

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

Here's my notebook : [My Notebook](https://www.kaggle.com/code/hrishikeshsrao/datadetox/edit)

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

Heres my notebook: [Click Here](https://github.com/hrishikesh-rao/Marvel-Level-1/blob/main/Anomaly_Detection.ipynb?raw=true)

---


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

Heres my notebook [Click Here](https://github.com/hrishikesh-rao/Marvel-Level-1/blob/main/SVM.ipynb?raw=true)

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

# Task 9: Evaluation Metrics:

## Aim
To compare models based on evaluation parameters

## Learnings

Joblib is a machine learning library which is used to load models of the form pkl files

Also the Evaluation Metrics in this are Precision,Recall,Accuracy and F1_score

Heres my notebook [Click Here](https://github.com/hrishikesh-rao/Marvel-Level-1/blob/main/Evalutation_Metrics.ipynb?raw=true)


