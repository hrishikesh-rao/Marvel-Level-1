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

