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
