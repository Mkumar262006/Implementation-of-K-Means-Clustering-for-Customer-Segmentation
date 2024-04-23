# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. import pandas as pd
2. impoet the necessary libraries from sklearn
3. by using kmeans predict y
4. by using plt.scatter predict the graph of customer segments

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: MANOJ KUMAR S
RegisterNumber: 212223240082
*/

import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
  
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")

```

## Output:
data.info():

![image](https://github.com/Mkumar262006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/147139472/c3af5d5e-8a0b-4fee-88e3-5e19169743a3)

data.isnull().sum() function

![image](https://github.com/Mkumar262006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/147139472/4b47b376-172e-400b-995c-b9e9a22a9d0f)


Elbow method graph:

![image](https://github.com/Mkumar262006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/147139472/555d904e-91b7-4180-bdbe-f318c3fc8f31)

KMeans clusters

![image](https://github.com/Mkumar262006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/147139472/5fa0dd14-df43-4933-b261-dbb0bce5cca4)

y_predict

![image](https://github.com/Mkumar262006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/147139472/1050571c-96ed-4b0a-9d0e-39f560c215a2)

 Customer segments Graph
 
![image](https://github.com/Mkumar262006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/147139472/29e2814b-df2c-4284-8643-769c3a184f98)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
