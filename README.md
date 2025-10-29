# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Load and preprocess the customer dataset (handle missing values, scale numerical features).

2.Select the number of clusters (k) using methods like the Elbow or Silhouette method.

3.Apply the K-Means algorithm to group customers into k clusters.

4.Visualize and analyze the clusters to interpret customer segments and patterns.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: VIJAY KUMAR D
RegisterNumber:25000878  
*/
```
```

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

##  1.DATA.HEAD():
<img width="881" height="271" alt="Screenshot 2025-10-29 112844" src="https://github.com/user-attachments/assets/b0ed187c-148f-4370-a6b7-9ac1c48bc4b6" />



##  2.DATA.INFO():
<img width="582" height="299" alt="Screenshot 2025-10-29 112855" src="https://github.com/user-attachments/assets/c6d940f9-6144-4cec-ae17-fa0a70bf8e72" />



##  3.DATA.ISNULL().SUM():
<img width="357" height="335" alt="Screenshot 2025-10-29 112903" src="https://github.com/user-attachments/assets/bc078160-7fb8-45ce-8dbc-7a88f5719b07" />


##  4.PLOT USING ELBOW METHOD:
<img width="750" height="572" alt="Screenshot 2025-10-29 112951" src="https://github.com/user-attachments/assets/0c12574e-c330-47ba-90b8-36f8916d1b21" />


##  5.K-MEANS CLUSTERING:
<img width="329" height="90" alt="Screenshot 2025-10-29 112911" src="https://github.com/user-attachments/assets/15b08891-e8ef-4b49-a1c7-6195c9b59e92" />


##  6.Y-PRED ARRAY:
<img width="759" height="240" alt="Screenshot 2025-10-29 112926" src="https://github.com/user-attachments/assets/ab250294-fd18-41b8-ac31-ce441b36f7be" />


# 7.CUSTOMER SEGMENT:

<img width="1062" height="833" alt="Screenshot 2025-10-29 113019" src="https://github.com/user-attachments/assets/f30b23c8-d41e-438c-b760-104d07dca035" />

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
