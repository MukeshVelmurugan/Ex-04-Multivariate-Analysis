# Ex-04-Multivariate-Analysis
## AIM
To perform Multivariate Exploratory Data Analysis on the given data set.

## EXPLANATION
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM
### STEP 1:
Import the built libraries required to perform EDA and outlier removal.

### STEP 2:
Read the given csv file

### STEP 3:
Convert the file into a dataframe and get information of the data.

### STEP 4:
Return the objects containing counts of unique values using (value_counts()).

### STEP 5:
Plot the counts in the form of Histogram or Bar Graph.

### STEP 6:
Use seaborn the bar graph comparison of data can be viewed.

### STEP 7:
Find the pairwise correlation of all columns in the dataframe.corr()

### STEP 8:
Save the final data set into the file

## CODE
``` PYTHON 
# program developed by : Mukesh V
# reg no : 212222230086SZ
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot SZ
data=pd.read_csv("SuperStore.csv")
data
data.head()

data.info()
data.describe()
data.tail()
data.shape
data.columns
data.isnull().sum()
data.duplicated()
data['Postal Code'] = data['Postal Code'].fillna(data['Postal Code'].mode()[0])
data.isnull().sum()

states=data.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()

states=data.loc[:,["State","Postal Code"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Postal Code",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("STATES") 
plt.ylabel=("Postal Code") 
plt.show()

states=data.loc[:,["Segment","Sales"]]
states=data.groupby(by=["Segment"]).sum()
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("SALES")
plt.show()

sns.barplot(x="Ship Mode",y="Sales",hue=data["Category"],data=data)

data.corr()
sns.heatmap(data.corr(),annot=True)
plt.figure(figsize=(10,7))
sns.scatterplot(x='Sub-Category', y='Sales', hue=data['Ship Mode'],data=data)
plt.xticks(rotation = 90)
```
## OUTPUT:
### DATASET
![A](./4.1.png)
### INFO 
![A](./4.2.png)
### DESCRIBE 
![A](./4.3.png)
### TAIL
![A](./4.4.png)
### SHAPE
![A](./4.5.png)
### COLUMNS
![A](./4.6.png)
### NULL SUM
![A](./4.7.png)
### DUPLICATED
![A](./4.8.png)
### POST CLEANING
![A](./4.9.png)
### BAR PLOT (STATES AND SALES) 
![A](./4.10.png)
### BAR PLOT (STATES AND POSTAL CODE)
![A](./4.11.png)
### BAR PLOT (SALES AND SEGMENT)
![A](./4.12.png)
### BAR PLOT (Ship Mode & Category vs Sales)
![A](./4.13.png)
### Correlation coefficient
![A](./4.14.png)
### Heatmap
![A](./4.15.png)
### SCATTER PLOT
![A](./4.16.png)

## RESULT:
Thus the program to perform EDA on the given data set is successfully executed.
