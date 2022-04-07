# Ex-03EDA

## AIM
To perform EDA on the given data set. 

# Explanation
The primary aim with exploratory analysis is to examine the data for distribution, outliers and 
anomalies to direct specific testing of your hypothesis.
 

# ALGORITHM
### STEP 1
Read the given Data

### STEP 2
Get the information about the data

### STEP 3
Remove the null values from the data

### STEP 4
Save the Clean data to the file




# CODE
# DATA ANALYSIS STEPS
import numpy as np

import pandas as pd

import seaborn as sns

df=pd.read_csv("titanic_dataset.csv")

df.info()
![GITLOGO](1.jpg)

df.head()
![GITLOGO](2.jpg)

df.isnull().sum()

![GITLOGO](3.jpg)

df.drop("Cabin",axis=1,inplace=True)

df.isnull().sum()

![GITLOGO](4.jpg)

df['Age']=df['Age'].fillna(df['Age'].median())

df['Embarked']=df['Embarked'].fillna(df['Embarked'].mode()[0])

df.isnull().sum()

![GITLOGO](5.jpg)

df.boxplot()

![GITLOGO](6.jpg)

df["Embarked"].value_counts()

df["Pclass"].value_counts()

df["Survived"].value_counts()

![GITLOGO](7.jpg)

pd.crosstab(df["Pclass"],df["Age"])

![GITLOGO](8.jpg)

df.corr()

![GITLOGO](9.jpg)

 sns.countplot(x="Survived",data=df)

![GITLOGO](10.jpg)

sns.countplot(x="Pclass",data=df)

![GITLOGO](11.jpg)

sns.countplot(x="Sex",data=df)

![GITLOGO](12.jpg)

sns.displot(df["Age"])

![GITLOGO](13.jpg)

sns.displot(df["Fare"])

![GITLOGO](14.jpg)

sns.countplot(x="Pclass",hue="Survived",data=df)

![GITLOGO](15.jpg)

sns.countplot(x="Age",hue="Sex",data=df)

![GITLOGO](16.jpg)

sns.countplot(x="Age",hue="Survived",data=df)

![GITLOGO](17.jpg)

sns.displot(df[df['Survived']==0]["Age"])

![GITLOGO](18.jpg)

sns.displot(df[df['Survived']==1]["Age"])

![GITLOGO](19.jpg)

sns.heatmap(df.corr(),annot=True)

![GITLOGO](20.jpg)

# OUTPUT
Finally, the given data's were analyzed successfully.




















