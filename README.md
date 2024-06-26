# Implementation-of-Logistic-Regression-Using-Gradient-Descent

## AIM:
To write a program to implement the the Logistic Regression Using Gradient Descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the data file and import numpy, matplotlib and scipy.

2.Visulaize the data and define the sigmoid function, cost function and gradient descent.

3.Plot the decision boundary.

4.Calculate the y-prediction.

## Program:
```
Program to implement the the Logistic Regression Using Gradient Descent.
Developed by: SRI SAI PRIYA. S
RegisterNumber: 212222240103
```
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
dataset=pd.read_csv("Placement_Data.csv")
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
```
```
dataset["gender"]=dataset["gender"].cat.codes
dataset["ssc_b"]=dataset["ssc_b"].cat.codes
dataset["hsc_b"]=dataset["hsc_b"].cat.codes
dataset["degree_t"]=dataset["degree_t"].cat.codes
dataset["workex"]=dataset["workex"].cat.codes
dataset["specialisation"]=dataset["specialisation"].cat.codes
dataset["status"]=dataset["status"].cat.codes
dataset["hsc_s"]=dataset["hsc_s"].cat.codes
dataset
x=dataset.iloc[:, :-1].values
y=dataset.iloc[: ,-1].values
y
theta=np.random.randn(x.shape[1])
Y=y
def sigmoid(z):
    return 1/(1+np.exp(-z))

def loss(theta,x,Y):
      h=sigmoid(x.dot(theta))
      return -np.sum(y*np.log(h)+(1-y)*np.log(1-h))
def gradient_descent(theta,x,Y,alpha,num_iterations):
    m=len(y)
    for i in range(num_iterations):
        h=sigmoid(x.dot(theta))
        gradient=x.T.dot(h-y)/m
        theta-=alpha * gradient
    return theta

theta=gradient_descent(theta,x,Y,alpha=0.01,num_iterations=1000)

def predict(theta,x):
    h=sigmoid(x.dot(theta))
    y_pred=np.where(h>=0.5,1,0)
    return y_pred
y_pred=predict(theta,x)

accuracy=np.mean(y_pred.flatten()==Y)
print("Accuracy:",accuracy)

print(y_pred)
print(y)

xnew=np.array([[0,87,0,95,0,2,78,2,0,0,1,0]])
y_prednew=predict(theta,xnew)
print(y_prednew)

xnew=np.array([[0,0,0,0,0,2,8,2,0,0,1,0]])
y_prednew=predict(theta,xnew)
print(y_prednew)
```

## Output:
![324398750-04081b8f-1bdf-45da-8309-b448ff876d16](https://github.com/SriSaiPriyaSenthilvel/-Implementation-of-Logistic-Regression-Using-Gradient-Descent/assets/119475702/137635ac-bd57-4c78-b326-83efd4c022f9)

![324399700-7c6baca2-7393-458e-a884-4978fb80e3ad](https://github.com/SriSaiPriyaSenthilvel/-Implementation-of-Logistic-Regression-Using-Gradient-Descent/assets/119475702/99b42bb6-4603-4c7d-a00b-7eabc1cbf6e0)

![image](https://github.com/SriSaiPriyaSenthilvel/-Implementation-of-Logistic-Regression-Using-Gradient-Descent/assets/119475702/42430aeb-75d7-49a3-b5ed-26e48e03ad50)

![image](https://github.com/SriSaiPriyaSenthilvel/-Implementation-of-Logistic-Regression-Using-Gradient-Descent/assets/119475702/cb938aa3-ccb1-4a16-b0f4-ac37a6f21a56)

![image](https://github.com/SriSaiPriyaSenthilvel/-Implementation-of-Logistic-Regression-Using-Gradient-Descent/assets/119475702/288ac5fb-399e-480a-a89f-2e349e7505cb)

![image](https://github.com/SriSaiPriyaSenthilvel/-Implementation-of-Logistic-Regression-Using-Gradient-Descent/assets/119475702/bbbb2901-488e-4cd2-992c-a09c787c3e6f)

![image](https://github.com/SriSaiPriyaSenthilvel/-Implementation-of-Logistic-Regression-Using-Gradient-Descent/assets/119475702/24d68b9e-433d-43d0-8b7b-bf71654e3b56)

![image](https://github.com/SriSaiPriyaSenthilvel/-Implementation-of-Logistic-Regression-Using-Gradient-Descent/assets/119475702/c1ae63a3-7abb-48cf-a3b5-f52495d70e9d)

## Result:
Thus the program to implement the the Logistic Regression Using Gradient Descent is written and verified using python programming.

