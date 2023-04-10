# Ex-04-Multivariate-Analysis
# AIM
To perform Multivariate EDA on the given data set.

# Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:
# STEP 1
Import the built libraries required to perform EDA and outlier removal.

# STEP 2
Read the given csv file

# STEP 3
Convert the file into a dataframe and get information of the data.

# STEP 4
Return the objects containing counts of unique values using (value_counts()).

# STEP 5
Plot the counts in the form of Histogram or Bar Graph.

# STEP 6
Use seaborn the bar graph comparison of data can be viewed.

# STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

# STEP 8
Save the final data set into the file
# PROGRAM
```
Name : KIRUTHIKA S
Register Number : 212221040085
```
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("SuperStore.csv")
df
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sns.scatterplot(df['Row ID'],df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Row ID"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Row ID")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("ROW ID")
plt.show()
states=df.loc[:,["Segment","Row ID"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("ROW ID")
plt.show()
sns.barplot(df['Sales'],df['Ship Mode'],hue=df['Region'])
df.corr()
sns.heatmap(df.corr(),annot=True)
```
# OUTPUT
# DATA
![image](https://user-images.githubusercontent.com/128348968/230833603-1c79a524-b9cc-4eea-9cf4-a15550ce0b6e.png)
# Data.info
![image](https://user-images.githubusercontent.com/128348968/230833736-577ff98f-e433-48e1-bcba-50bebbaa1c06.png)
# Data.describe
![image](https://user-images.githubusercontent.com/128348968/230833826-e7eab9cc-38ff-4eae-a7a7-175c94fb56c6.png)
# Checking the null values and Cleaning it
![image](https://user-images.githubusercontent.com/128348968/230833912-6ddb6cc1-b828-486e-9f81-88b81831768b.png)

![image](https://user-images.githubusercontent.com/128348968/230834780-b9ea86b3-815f-45b6-8893-a46fe78f5786.png)

# DATA TYPES
![image](https://user-images.githubusercontent.com/128348968/230834894-f727ac0a-9382-4e34-84d7-174f5c6c1bd3.png)
# SCATTER PLOT
![image](https://user-images.githubusercontent.com/128348968/230834936-be8b1b9a-38b2-4db6-8a6c-8ff5eaf37212.png)
# BAR PLOT
![image](https://user-images.githubusercontent.com/128348968/230834983-b4354010-9ab6-466c-ba20-9b5a6c347638.png)
![image](https://user-images.githubusercontent.com/128348968/230835019-0f3bc5e4-405b-4a5a-b395-1803bc25a6a7.png)
![image](https://user-images.githubusercontent.com/128348968/230835039-27b40bab-daac-461f-9c9c-26b3196b629d.png)
![image](https://user-images.githubusercontent.com/128348968/230835069-434ba5ba-ff23-443e-b54d-919c878c8619.png)
# CORRELATION COEFFICIENT INTERPRETATION
![image](https://user-images.githubusercontent.com/128348968/230835116-e68ca32f-05fe-4173-99ea-b01c9fb5d730.png)
# HEATMAP
![image](https://user-images.githubusercontent.com/128348968/230835194-dfb4f69a-1856-4dee-9770-ab75d3fc52f2.png)
# RESULT
Thus we have read the given data and performed the multivariate analysis with different types of plots.
