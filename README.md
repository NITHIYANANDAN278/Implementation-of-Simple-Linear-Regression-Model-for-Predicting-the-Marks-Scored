# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas, numpy and sklearn
2. Calculate the values for the training data set
3. Calculate the values for the test data set
4. Plot the graph for both the data sets and calculate for MAE, MSE and RMSE
 

## Program:
```
/*
Program to implement the simple linear regression model for predicting the marks scored.
Developed by: NITHIYANANDAN N
RegisterNumber:212222230099
*/

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.metrics import mean_absolute_error, mean_squared_error
df=pd.read_csv("C:/Users/SEC/Downloads/student_scores.csv")
df.head()
df.tail()
X=df.iloc[:,:-1].values
print(X)
Y=df.iloc[:,-1].values
print(Y)
from sklearn.model_selection import train_test_split
X_train,X_test,Y_train,Y_test=train_test_split(X,Y,test_size=1/3,random_state=0)

from sklearn.linear_model import LinearRegression
regressor=LinearRegression()
regressor.fit(X_train,Y_train)
Y_pred=regressor.predict(X_test)

print(Y_pred)
print(Y_test)
plt.scatter(X_train,Y_train,color="orange")
plt.plot(X_train,regressor.predict(X_train),color="red")
plt.title("Hours vs scores(Training Set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
plt.scatter(X_test,Y_test,color="orange")
plt.plot(X_test,regressor.predict(X_test),color="red")
plt.title("Hours vs scores(Test Data Set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
mse=mean_squared_error(Y_test,Y_pred)
print("MSE = ",mse)
mae=mean_absolute_error(Y_test,Y_pred)
print("MAE = ",mae)
rmse=np.sqrt(mse)
print("RMSE : ",rmse)

*/
```

## Output:
![image](https://github.com/NITHIYANANDAN278/Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored/assets/121784636/b44fa458-07ae-497d-bb9a-14283780ece1)
![image](https://github.com/NITHIYANANDAN278/Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored/assets/121784636/478a22ea-9b6e-4849-aaf6-e515b30efd64)
![image](https://github.com/NITHIYANANDAN278/Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored/assets/121784636/5ab6cf41-014a-4c14-bdaa-84322fbba68c)



## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
