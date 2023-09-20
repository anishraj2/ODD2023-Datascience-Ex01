# Ex-01_DS_Data_Cleansing

## AIM
To read the given data and perform data cleaning and save the cleaned data to a file. 

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. 
Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information. 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Get the information about the data
### STEP 3
Remove the null values from the data
### STEP 4
Save the Clean data to the file

# CODE and OUTPUT
## PROGRAM 1:
```
import numpy as np
import pandas as pd
df=pd.read_csv("/content/Data_set.csv")
print(df.info())
df.head(10)
df.shape
print(df.isnull().sum())
df['aired_on'] = df['show_name'].fillna(df['aired_on'].mode()[0])
print(df.isnull().sum())
df['original_network'] = df['original_network'].fillna(df['original_network'].mode()[0])
df.head(5)
print(df.isnull().sum())
df['watchers'] = df['watchers'].fillna(df['watchers'].median())
df.head(5)
print(df.isnull().sum())
df['rating'] = df['rating'].fillna(df['rating'].mean())
df.head(5)
print(df.isnull().sum())
df = df.dropna(subset=['show_name'])
df.head(5)
print(df.isnull().sum())
df = df.dropna(subset=['current_overall_rank'])
df.head(5)
print(df.isnull().sum())
print(df.info())
```
## PROGRAM 2:
```
import pandas as pd
import numpy as np
df=pd.read_csv("/content/Loan_data.csv")
df.describe()
df.info()
df.isnull().sum()
df = df.dropna(subset="Gender")
df.head(5)
df.isnull().sum()
df = df.dropna(subset=["Dependents"])
df.isnull().sum()
df['Self_Employed'] = df['Self_Employed'].fillna(df['Self_Employed'].mode()[0])
df.head(5)
df.isnull().sum()
df['LoanAmount'] = df['LoanAmount'].fillna(df['LoanAmount'].mean ())
df.head(5)
df.isnull().sum()
df['Loan_Amount_Term'] = df['Loan_Amount_Term'].fillna(df['Loan_Amount_Term'].median())
df.head(5)
df.isnull().sum()
df['Credit_History'] = df['Credit_History'].fillna(df['Credit_History'].mean())
df.head(5)
df.isnull().sum()
```
# OUTPUT

## DATA 1:
![DATA 1](1.png)<BR>
## NON NULL BEFORE:
![NON NULL BEFORE](2.png)<br>
![NON NULL BEFORE](3.png)<br>
## NON NULL AFTER:
![NON NULL AFTER](4.png)<br>
![NON NULL AFTER](5.png)<br>
![NON NULL AFTER](6.png)<br>
![NON NULL AFTER](7.png)<br>
## OUTCOME:
![OUTCOME](8.png)<BR>
## DATA 2:
![DATA 2](9.png)<br>
## NON NULL BEFORE:
![NON NULL BEFORE](10.png)<br>
## NON NULL AFTER:
![NON NULL AFTER](11.png)<br>
![NON NULL AFTER](12.png)<br>
![NON NULL AFTER](13.png)<br>
![NON NULL AFTER](14.png)<br>
![NON NULL AFTER](15.png)<br>
![NON NULL AFTER](16.png)<br>
## OUTCOME:
![OUTCOME](17.png)
## RESULT:
Thus,the given data is read,cleansed and the cleaned data is saved into the file.
