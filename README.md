# Implementation-of-Logistic-Regression-Using-Gradient-Descent

## AIM:
To write a program to implement the the Logistic Regression Using Gradient Descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import necessary libraries (pandas, numpy, matplotlib).

2.Load dataset from 'Placement_Data.csv' using Pandas Library.

3.Drop unnecessary columns ('sl_no', 'salary').

4.Convert categorical variables to category data type.

5.Encode categorical variables to numerical values.

6.Set features X (all columns except 'status').

7.Set target variable Y (column 'status').

8.Initialize weights theta randomly.

9.Define sigmoid function.

10.Define loss function.

11.Implement gradient descent function.

12.Compute predicted probabilities.

13.Update weights using gradients.

14.Train the model by calling gradient descent function.

15.Define prediction function.

16.Evaluate the model by calculating accuracy.

17.Test with new input data and print predictions.

18.Print accuracy and predictions.


## Program:
```
/*
Program to implement the the Logistic Regression Using Gradient Descent.
Developed by: ROHAN J
RegisterNumber: 212223040171
*/
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

dataset=pd.read_csv("C:/Users/admin/Downloads/Placement_Data.csv")
dataset

dataset=dataset.drop('sl_no',axis=1)
dataset=dataset.drop('salary',axis=1)

dataset["gender"]=dataset["gender"].astype('category')
dataset["ssc_b"]=dataset["ssc_b"].astype('category')
dataset["hsc_b"]=dataset["hsc_b"].astype('category')
dataset["degree_t"]=dataset["degree_t"].astype('category')
dataset["workex"]=dataset["workex"].astype('category')
dataset["specialisation"]=dataset["specialisation"].astype('category')
dataset["status"]=dataset["status"].astype('category')
dataset["hsc_s"]=dataset["hsc_s"].astype('category')
dataset.dtypes

dataset["gender"]=dataset["gender"].cat.codes
dataset["ssc_b"]=dataset["ssc_b"].cat.codes
dataset["hsc_b"]=dataset["hsc_b"].cat.codes
dataset["degree_t"]=dataset["degree_t"].cat.codes
dataset["workex"]=dataset["workex"].cat.codes
dataset["specialisation"]=dataset["specialisation"].cat.codes
dataset["status"]=dataset["status"].cat.codes
dataset["hsc_s"]=dataset["hsc_s"].cat.codes

dataset

X=dataset.iloc[:,:-1].values
Y=dataset.iloc[:,-1].values

Y

theta=np.random.randn(X.shape[1])
y=Y
def sigmoid(z):
    return 1 /(1+np.exp(-z))

def loss(theta,X,y):
    h=sigmoid(x.dot(theta))
    return -np.sum(y*np.log(h)+(1-y)*np.log(1-h))

def gradient_descent(theta,X,y,alpha,num_iterations):
    m=len(y)
    for i in range(num_iterations):
        h=sigmoid(X.dot(theta))
        gradient=X.T.dot(h-y)/m
        theta-=alpha*gradient
    return theta

theta=gradient_descent(theta,X,y,alpha=0.01,num_iterations=1000)

def predict(theta,X):
    h=sigmoid(X.dot(theta))
    y_pred=np.where(h>=0.5,1,0)
    return y_pred 

y_pred=predict(theta,X)

accuracy=np.mean(y_pred.flatten()==y)
print("Accuracy:",accuracy)

print(y_pred)

print(Y)

xnew=np.array([[0,87,0,95,0,2,78,2,0,0,1,0]])
y_prednew=predict(theta,xnew)
print(y_prednew)

xnew=np.array([[0,0,0,0,0,2,8,2,0,0,1,0]])
y_prednew=predict(theta,xnew)
print(y_prednew)
```

## Output:
![image](https://github.com/user-attachments/assets/b85446f2-79b5-4c91-9fde-992242da0eb1)

## Result:
Thus the program to implement the the Logistic Regression Using Gradient Descent is written and verified using python programming.

