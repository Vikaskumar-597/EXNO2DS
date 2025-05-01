# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
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
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sn
```
```
dt=pd.read_csv('/content/titanic_dataset .csv')
dt
```
![Screenshot 2025-05-01 233142](https://github.com/user-attachments/assets/66098780-7eaa-4233-aeae-479ec323b539)

```
dt.info()
```
![Screenshot 2025-05-01 233153](https://github.com/user-attachments/assets/e0e1254d-aa48-40eb-82d1-3b31d00ce283)

```
dt.shape
```
![Screenshot 2025-05-01 233236](https://github.com/user-attachments/assets/af9472a3-c9da-495e-98fb-cb83eabe501c)
```
dt.set_index('PassengerId',inplace=True)
dt.describe()
```
![Screenshot 2025-05-01 233243](https://github.com/user-attachments/assets/b4653071-bcda-4850-8324-a8b3ce483c5c)

```
dt.nunique()
```
![Screenshot 2025-05-01 233251](https://github.com/user-attachments/assets/c8a864ec-ce35-4d16-a2ae-191ad57f8efd)

```
dt["Survived"].value_counts()
```
![Screenshot 2025-05-01 233257](https://github.com/user-attachments/assets/1376deb4-6895-4925-b4ab-908130a0fdad)

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![Screenshot 2025-05-01 233302](https://github.com/user-attachments/assets/5b227b2d-6872-449a-9a22-7fab45d4ea22)

```
sns.countplot(data=dt,x="Survived")
```
![Screenshot 2025-05-01 233308](https://github.com/user-attachments/assets/7b03c110-d9b7-45fa-991c-5603f03f1c44)

```
dt
```
![Screenshot 2025-05-01 233323](https://github.com/user-attachments/assets/94062001-4b01-4487-abc8-91dd599687f0)

```
dt.Pclass.unique()
```
![Screenshot 2025-05-01 233329](https://github.com/user-attachments/assets/318ea324-eb44-49fb-8585-3293d3d61d3f)

```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![Screenshot 2025-05-01 233337](https://github.com/user-attachments/assets/76d0d895-bfd2-4ab6-8cff-930259163c6b)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt, height=5 ,aspect=.7)
```
![Screenshot 2025-05-01 233345](https://github.com/user-attachments/assets/e649e830-c8c6-474a-b53c-bde6b6ff8745)

```
sns.catplot(x="Survived",hue="Gender",data=dt,kind="count")
```
![Screenshot 2025-05-01 233355](https://github.com/user-attachments/assets/af08f7b6-2d13-4435-9430-92626039a6c6)

```
dt.boxplot(column="Age",by="Survived")
```
![Screenshot 2025-05-01 233404](https://github.com/user-attachments/assets/986d4863-18fd-4970-88de-939a90b1507e)

```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![Screenshot 2025-05-01 233412](https://github.com/user-attachments/assets/d4a38da4-f86c-410b-a470-1f7655f8f7de)

```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![Screenshot 2025-05-01 233424](https://github.com/user-attachments/assets/452d1c7e-f453-4fd1-9079-04c9d7370da1)

```
fig, ax1 = plt.subplots(figsize=(8, 5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```

![Screenshot 2025-05-01 233438](https://github.com/user-attachments/assets/ae3385b5-36d8-411f-aac0-dbf8e3635e2c)

```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![Screenshot 2025-05-01 233448](https://github.com/user-attachments/assets/6392af55-3e43-4433-81ff-5379f278c425)

```
## Co-relation
corr=dt.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```

![Screenshot 2025-05-01 233456](https://github.com/user-attachments/assets/b52d4530-7dec-4903-87fb-d495da4c1b1a)

```
sns.pairplot(dt)
```

![2](https://github.com/user-attachments/assets/0550c26b-bb61-4c20-8ea5-1bf05f33fb39)


# RESULT
       Thus the primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis is successfully completed.
