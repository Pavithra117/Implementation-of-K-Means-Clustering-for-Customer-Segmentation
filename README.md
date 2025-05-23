# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
1. Import pandas and mataplotlib.pyplot
2. 2.Read the dataset and transform it
3. 3.Import KMeans and fit the data in the model
4.Plot the cluster graph
```
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Pavithra K
RegisterNumber: 212224240112  
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
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
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
print(y_pred)
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
![K Means Clustering for Customer Segmentation](sam.png)

![Screenshot 2025-05-16 204914](https://github.com/user-attachments/assets/86a572be-6e5a-4203-917e-cdefe00c189e)

![Screenshot 2025-05-16 204925](https://github.com/user-attachments/assets/840cdf81-05da-481b-977a-214ab8e38231)

![Screenshot 2025-05-16 204935](https://github.com/user-attachments/assets/a53d5384-c3ba-4637-b8cd-0d36f2b57d58)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
