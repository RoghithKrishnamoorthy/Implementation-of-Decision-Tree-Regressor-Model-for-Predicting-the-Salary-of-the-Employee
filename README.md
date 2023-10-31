# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the required libraries.
2.Read the data frame using pandas.
3.Get the information regarding the null values present in the dataframe.
4.Apply label encoder to the non-numerical column inoreder to convert into
numerical values.
5.Determine training and test data set.
6.Apply decision tree regression on to the dataframe.
7.Get the values of Mean square error, r2 and data prediction.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: Roghith.K
RegisterNumber:  212222040135
*/

import pandas as pd
data=pd.read_csv("/content/Salary.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()

x=data[["Position","Level"]]
y=data["Salary"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn import metrics
mse=metrics.mean_squared_error(y_test,y_pred)
mse

r2=metrics.r2_score(y_test,y_pred)
r2

dt.predict([[5,6]])
```

## Output:
![ex 7 1 data.head()](https://github.com/RoghithKrishnamoorthy/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/119475474/e9f8c88e-c9ad-4412-9c09-dd57079b0c4e)
[ex 7 2.data.info()](https://github.com/RoghithKrishnamoorthy/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/119475474/49f72f16-7ae0-41bc-aa4c-39be45716191)
[ex 7 3.isnull()&sum()function](https://github.com/RoghithKrishnamoorthy/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/119475474/1c882a50-52fd-4c31-9652-48402344c894)
[ex 7 4.data.head() for position](https://github.com/RoghithKrishnamoorthy/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/119475474/271a7a1e-7928-4706-9ff4-5e61b38ff17c)
[ex 7 5.MSE value](https://github.com/RoghithKrishnamoorthy/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/119475474/01bfa785-ec74-48a0-9301-be5120b22295)
[ex 7 6.R2.value](https://github.com/RoghithKrishnamoorthy/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/119475474/fa2e385d-a158-4c99-8b2f-15a76d4ad241)
[ex 7 7.prediction value](https://github.com/RoghithKrishnamoorthy/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/119475474/041174c0-4624-48fe-bb82-34fa783792b2)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
