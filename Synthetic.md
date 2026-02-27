# Task 3 :  Publish Your Own Dataset

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


