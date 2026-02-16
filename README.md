
AIM:
To perform Exploratory Data Analysis on the given data set

EXPLANATION:
The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

CODING AND OUTPUT
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("C:/Users/admin/Downloads/titanic_dataset.csv")
dt
1
dt.info()
2
dt.shape
3
dt.set_index("PassengerId",inplace=True)
dt.describe()
4
dt.nunique()
5
dt["Survived"].value_counts()
6
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
7
sns.countplot(data=dt,x="Survived")

8
dt.Pclass.unique()
10
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
9
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
10 2
sns.catplot(x='Survived',hue="Gender",data=dt,kind='count')
11
dt.boxplot(column="Age",by="Survived")
12
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
13
sns.jointplot(x="Age",y="Fare",data=dt)
14
fig,ax1=plt.subplots (figsize=(8,5))

sns.boxplot(ax=ax1,x="Pclass", y="Age", hue="Gender", data=dt)
15
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
16
corr = dt.select_dtypes(include='number').corr()
sns.heatmap(corr, annot=True)
17
sns.pairplot(dt)
18
RESULT
Thus the Exploratory Data Analysis on The Given Data Set Was Performed Sucessfully.
