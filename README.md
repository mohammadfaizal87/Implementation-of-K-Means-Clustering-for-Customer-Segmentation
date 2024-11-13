# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import the necessary packages using import statement.


2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().


3.Import KMeans and use for loop to cluster the data.


4.Predict the cluster and plot data graphs.


5.Print the outputs and end the program


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: MOHAMMAD FAIZAL SK
RegisterNumber: 212223240092
*/
```

```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Dataset-20230524.zip")
data

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
plt.title("Elbow Method")

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
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="yellow",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="pink",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="purple",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:

## DATA.HEAD():
![ml 8 i1](https://github.com/Rama-Lekshmi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118541549/82146f99-d559-4f32-b98b-341ad7772dca)
## DATA.info():
![ml 8 i2](https://github.com/Rama-Lekshmi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118541549/58d6586f-f177-47c4-ae07-6127697b54a7)
## NULL VALUES:
![ml 8 i3](https://github.com/Rama-Lekshmi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118541549/a8ded473-2c4c-4cf9-baa0-c96a892d61d7)
## ELBOW GRAPH:
![ml 8 i4](https://github.com/Rama-Lekshmi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118541549/5285f689-622f-4050-95c5-54e5ec8a2de3)
## CLUSTER FORMATION:
![ml 8 i5](https://github.com/Rama-Lekshmi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118541549/e651e504-cb44-409a-9a29-badb368d0ffd)
## PREDICICTED VALUE:
![ml 8 i6](https://github.com/Rama-Lekshmi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118541549/d1dfca57-4a4e-4fc8-a889-6754a38fe7a5)
## FINAL GRAPH(D/O):
![ml 8 i7](https://github.com/Rama-Lekshmi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118541549/882449a6-7b80-4ffc-a40b-9f4246f1fbf1)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
