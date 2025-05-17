# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import dataset and print head,info of the dataset  
2.check for null values   
3.Import kmeans and fit it to the dataset    
4.Plot the graph using elbow method    
5.Print the predicted array    
6.Plot the customer segments    

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: ABISHEIK RAJ .J
RegisterNumber:  212224230006
*/
```
```python

import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss=[]

for i in range(1,11):

kmeans=KMeans(n_clusters=i,init="k-means++")

kmeans.fit(data.iloc[:,3:])

wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)

plt.xlabel("No_of_Clusters")

plt.ylabel("wcss")

plt.title("Elbow Method")

km=KMeans(n_clusters=5)

km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])

y_pred

data["cluster"]=y_pred

df0=data[data["cluster"]==0]

df1=data[data["cluster"]==1]

df2=data[data["cluster"]==2]

df3=data[data["cluster"]==3]

df4=data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")

plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")

plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")

plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")

plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")

plt.legend()

plt.title("Customer Segment")

```

## Output:
### 1.DATA.HEAD():
![image](https://github.com/user-attachments/assets/14e9fa29-4edd-48cc-aec1-891c6a6c97b1)

### 2.DATA.INF0():
![image](https://github.com/user-attachments/assets/0b29b4d5-bf35-4461-b045-c1451860597d)

### 3.DATA.ISNULL().SUM():
![image](https://github.com/user-attachments/assets/d4332286-52a0-4ed4-be05-404628103a13)

### 4.PLOT USING ELBOW METHOD:
![image](https://github.com/user-attachments/assets/fe097c7b-2ace-4c28-946c-570652e7214a)

### 5.K-MEANS CLUSTERING:
![image](https://github.com/user-attachments/assets/9bf8767d-f46b-47cb-99a4-3b7e1a0316ae)

### 5.K-MEANS CLUSTERING:
![image](https://github.com/user-attachments/assets/4f6c2957-6d85-4ae6-abb5-202a339a6230)
### 7.CUSTOMER SEGMENT:
![image](https://github.com/user-attachments/assets/6e651abc-1085-4ae7-bbe9-614a3b3dff7a)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

