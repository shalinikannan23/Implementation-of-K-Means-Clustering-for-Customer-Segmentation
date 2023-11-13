# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:

1. Import the required libraries .
2. Read the data frame using pandas.
3. Get the information regarding the null values present in the dataframe.
4. Apply label encoder to the non-numerical column inoreder to convert into numerical values.
5. Determine training and test data set.
6. Apply k means clustering for customer segmentation.
   

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SHALINI.K
RegisterNumber: 212222240095
```
```py
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss=[]   #Within-Cluster Sum of Squares.

for i in range(1,11):
    kmeans=KMeans(n_clusters=i, init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
    
plt.plot(range(1,11),wcss)
plt.xlabel("No.of Clusters")
plt.ylabel("wcss")
plt.title("ELBOW METHOD GRAPH")
plt.show()
km = KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="green",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="purple",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="gold",label="cluster4")
plt.legend()
plt.title("Customer Segments")
 
*/
```

## Output:

### data.head()

![EXP8-1](https://github.com/AnnBlessy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477835/4aa0e648-c55c-482b-8a9e-e7045dcc1cb0)

### data.info()

![EXP8-2](https://github.com/AnnBlessy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477835/5b7c6adb-09cd-4f8f-b2e1-48f88e1ace52)

### data.isnull().sum()

![EXP8-3](https://github.com/AnnBlessy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477835/93abcc5d-b598-4dc6-8465-cbcaaa45d671)

### Elbow Method Graph

![EXP8-4](https://github.com/AnnBlessy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477835/ed032d5e-830d-4725-938b-45795022d44a)

### KMeans Clusters

![EXP8-5](https://github.com/AnnBlessy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477835/d37f64a4-47eb-4d9c-9758-b6ca015e312f)

### Y_pred

![EXP8-6](https://github.com/AnnBlessy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477835/e962be05-290c-4d7c-ae5f-64ae5f73290b)

### Customers Segments Graph

![EXP8-7](https://github.com/AnnBlessy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119477835/0c0ade5b-fe1d-4afe-958c-5a99ae2d1af3)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
