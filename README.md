# EXNO2DS
# AIM:
To perform Exploratory Data Analysis on the given data set
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("C:/Users/admin/Downloads/titanic_dataset.csv")
dt
```



<img width="1397" height="505" alt="image" src="https://github.com/user-attachments/assets/8a77d629-4f46-4175-9dbc-16079f4354c1" />



```
dt.info()
```




<img width="605" height="415" alt="image" src="https://github.com/user-attachments/assets/171ca8aa-16c7-4130-85c3-1e3c7ade5f5b" />



```
dt.shape
```




<img width="602" height="35" alt="image" src="https://github.com/user-attachments/assets/8465ab77-50a6-45dc-adfe-7f0b897b7223" />




```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```



<img width="441" height="95" alt="image" src="https://github.com/user-attachments/assets/cd3fcffe-c382-452b-82c2-a84141610339" />







```
dt.nunique()
```





<img width="919" height="272" alt="image" src="https://github.com/user-attachments/assets/ff616088-c1f2-4e2d-b625-6402982b7401" />






```
dt["Survived"].value_counts()
```




<img width="511" height="94" alt="image" src="https://github.com/user-attachments/assets/3f54e1ec-251c-48ce-a2b4-a9ead187bcfd" />



```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```




<img width="441" height="95" alt="image" src="https://github.com/user-attachments/assets/682550f3-0a2d-4221-9244-23fe0a9323fe" />




```
sns.countplot(data=dt,x="Survived")

```




<img width="1025" height="576" alt="image" src="https://github.com/user-attachments/assets/8a4f055a-73e4-4c60-9df4-c8e6ccef50f9" />




```
dt.Pclass.unique()
```



<img width="311" height="46" alt="image" src="https://github.com/user-attachments/assets/9a80eb10-ecd3-48e5-b059-0cd7804000b2" />





```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```



<img width="1422" height="547" alt="image" src="https://github.com/user-attachments/assets/293fa29f-b8cf-4e68-b4de-f536882d7474" />




```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```





<img width="1128" height="647" alt="image" src="https://github.com/user-attachments/assets/40f4f8c8-7e98-4264-9781-1097b77c12bc" />





```
sns.catplot(x='Survived',hue="Gender",data=dt,kind='count')
```




<img width="983" height="664" alt="image" src="https://github.com/user-attachments/assets/cea4bc24-f191-4bcb-b4c3-16b393a8b1ea" />










```
dt.boxplot(column="Age",by="Survived")
```






<img width="941" height="607" alt="image" src="https://github.com/user-attachments/assets/73369434-a7c3-4b98-a5e0-fb8f1127d3ec" />




```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```







<img width="1117" height="555" alt="image" src="https://github.com/user-attachments/assets/1efba35e-d29f-4411-a52d-d201114b7850" />





```
sns.jointplot(x="Age",y="Fare",data=dt)
```


<img width="1156" height="723" alt="image" src="https://github.com/user-attachments/assets/cd01deb5-0e83-4ecc-910f-51b7dd03724d" />












```
fig,ax1=plt.subplots (figsize=(8,5))

sns.boxplot(ax=ax1,x="Pclass", y="Age", hue="Gender", data=dt)
```







<img width="1042" height="597" alt="image" src="https://github.com/user-attachments/assets/46b65d8d-5e69-4f90-b515-c92fab9c2bf0" />





```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```





<img width="1382" height="644" alt="image" src="https://github.com/user-attachments/assets/43e90fd0-4b81-4b84-9b99-2c5801cf1388" />



```
corr = dt.select_dtypes(include='number').corr()
sns.heatmap(corr, annot=True)
```





<img width="937" height="566" alt="image" src="https://github.com/user-attachments/assets/2b59eee2-a49a-4c17-84e5-2b3bf9fcce65" />






```
sns.pairplot(dt)
```



<img width="1477" height="896" alt="image" src="https://github.com/user-attachments/assets/70aed4e5-b1c9-4191-bf2e-68f9b20d6cab" />




## RESULT
Thus the Exploratory  Data Analysis on The Given Data Set Was Performed Sucessfully.
