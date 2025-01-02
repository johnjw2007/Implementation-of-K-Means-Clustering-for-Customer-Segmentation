# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas and matplotlib.pyplot
2. Read the dataset and transform it
3. Import KMeans and fit the data in the model
4. Plot the Cluster graph

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: John Wilfred Thomas J W
RegisterNumber:  24013517
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
 KMeans(n_clusters=5)
 y_pred = km.predict(data.iloc[:,3:])
 y_pred


 data["cluster"] = y_pred
 df0 = data[data["cluster"]==0]
 df1 = data[data["cluster"]==1]
 df2 = data[data["cluster"]==2]
 df3 = data[data["cluster"]==3]
 df4 = data[data["cluster"]==4]
 plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster")
 plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster")
 plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster")
 plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster")
 plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster")
 plt.legend()
 plt.title("Customer Segments")
```
 
## Output:
![image](https://github.com/user-attachments/assets/ea5feabc-ee82-4f97-9dce-9d468ccb5123)
![image](https://github.com/user-attachments/assets/756ada5a-58fe-484d-9d47-d07e94c09119)
![image](https://github.com/user-attachments/assets/f2f12774-3974-4d6e-81bd-77f734dc5f3f)
![image](https://github.com/user-attachments/assets/4b17da30-64e6-41e6-b059-2c157d2b5f76)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using Python programming.
