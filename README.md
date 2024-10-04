# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. 1:Start.
2. Data Preparation: Load and explore customer data.
3. Determine Optimal Clusters: Use the Elbow Method to find the best number of clusters.
4. Apply K Means Clustering: Perform clustering on customer data.
5. Visualize Segmented Customers: Plot clustered data to visualize customer segments.
6. End

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: V.POOJAA SREE
RegisterNumber: 212223040147
*/


import pandas as pd 
import matplotlib.pyplot as plt 
data=pd.read_csv("C:/Users/Admin/Desktop/Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No.of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
KMeans(n_clusters=5)
y_pred=km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
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

![o1](https://github.com/user-attachments/assets/63a3e599-c5d7-48b5-8a06-ac3a9aa35ba6)

![o2](https://github.com/user-attachments/assets/1ee0367a-c04d-4a25-8267-7a72598ceeb2)

![o3](https://github.com/user-attachments/assets/1d94b2c1-816b-488c-aa84-cd7b7794db78)

![o4](https://github.com/user-attachments/assets/804f6695-3ada-4e70-85f6-43692a75dacc)

![o5](https://github.com/user-attachments/assets/84d88d32-7791-4fe2-b6fd-ce7b40387f64)

![o6](https://github.com/user-attachments/assets/30dd9b45-1bb8-4a27-a43e-ff20ff161ddf)




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
