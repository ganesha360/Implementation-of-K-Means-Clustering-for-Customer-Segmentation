# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the required libraries,read the data set.find the number of null data.

2.Find the number of null data.

3.Import sklearn library.

4.Find y predict and plot the graph.

## Program:
```PYTHON
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: GANESH R
RegisterNumber:  2122222400029
*/
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: A.Anbuselvam
RegisterNumber:  212222240009

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range (1,11):
    kmeans=KMeans(n_clusters = i,init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow matter")

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
plt.title("Customer Segmets")
```

## Output:

## data.head():
![ML1](https://github.com/ganesha360/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120884552/a7459d0c-6f8b-4ef3-83ab-f5a543e0969d)

## data.info():
![ML2](https://github.com/ganesha360/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120884552/974aa021-15ab-4f88-aefc-4932336f5cc7)

## data.isnull().sum():
![ML3](https://github.com/ganesha360/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120884552/f02d1962-8684-4142-8e27-50f16d9b703e)

## Elbow method:
![ML4](https://github.com/ganesha360/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120884552/34659507-5ab7-416c-a993-d368d1d512b7)

## K-Means:
![ML5](https://github.com/ganesha360/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120884552/7066262e-c185-4725-b7f7-da80365c0f36)

## Array value of Y:
![ML6](https://github.com/ganesha360/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120884552/d47ec1fb-0d41-497c-ab1a-0aade2b11265)

## Customer Segmentation:
![ML7](https://github.com/ganesha360/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120884552/120a8b6a-d395-4d69-a70f-fe67baea01e1)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
