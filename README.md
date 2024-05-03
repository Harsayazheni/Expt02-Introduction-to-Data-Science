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
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
![Screenshot 2024-04-23 135230](https://github.com/Harsayazheni/Expt02-Introduction-to-Data-Science/assets/118708467/f9c52b29-674b-475e-a317-7f717494c4d2)
```
dt.info()
```
![Screenshot 2024-04-23 135326](https://github.com/Harsayazheni/Expt02-Introduction-to-Data-Science/assets/118708467/806a43c9-dbf7-4337-a76d-eb26133ce1d8)
```
dt.shape
dt.head(4)
dt.tail(4)
dt.set_index("PassengerId",inplace=True)
```
![Screenshot 2024-04-23 135828](https://github.com/Harsayazheni/Expt02-Introduction-to-Data-Science/assets/118708467/782b770c-6a48-4102-8ef1-087fd853418d)
```
dt.describe()
dt.nunique()
dt["Survived"].value_counts()
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![Screenshot 2024-04-23 135942](https://github.com/Harsayazheni/Expt02-Introduction-to-Data-Science/assets/118708467/45d05238-a279-412b-9d5e-dd2c64b5fdc9)
```
sns.countplot(data=dt,x="Survived")
dt
dt.Pclass.unique()
dt.rename(columns = {"Sex":"Gender"},inplace = True)
dt
```
![Screenshot 2024-05-03 154343](https://github.com/Harsayazheni/Expt02-Introduction-to-Data-Science/assets/118708467/29cdec7c-9c4e-4a9c-866b-15d1d7817a0a)
![Screenshot 2024-05-03 154352](https://github.com/Harsayazheni/Expt02-Introduction-to-Data-Science/assets/118708467/5223d5af-86bc-42b8-be53-4642074a4df2)
![Screenshot 2024-05-03 154408](https://github.com/Harsayazheni/Expt02-Introduction-to-Data-Science/assets/118708467/dd16d9ed-cda3-45d7-a17c-438b5f703e04)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![Screenshot 2024-05-03 154605](https://github.com/Harsayazheni/Expt02-Introduction-to-Data-Science/assets/118708467/e355a7e6-28db-4417-92c9-60ca3a868925)

```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![Screenshot 2024-05-03 154613](https://github.com/Harsayazheni/Expt02-Introduction-to-Data-Science/assets/118708467/3c7ce365-3736-4066-9a72-4c6bb907dbeb)

```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![Screenshot 2024-05-03 154624](https://github.com/Harsayazheni/Expt02-Introduction-to-Data-Science/assets/118708467/9e8f2261-8290-44be-9e6b-ec116561326b)

```
fig, ax1 = plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x="Pclass",y='Age',hue='Gender',data=dt)
```
![Screenshot 2024-05-03 154634](https://github.com/Harsayazheni/Expt02-Introduction-to-Data-Science/assets/118708467/c1fb126f-b73a-49d6-9e5f-8cc2ad6f3f5f)

```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![Screenshot 2024-05-03 154643](https://github.com/Harsayazheni/Expt02-Introduction-to-Data-Science/assets/118708467/eb6d5f15-c3b3-4c88-a4ef-abfe07b009e4)

```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![Screenshot 2024-05-03 154657](https://github.com/Harsayazheni/Expt02-Introduction-to-Data-Science/assets/118708467/2ebef9a2-7e58-4e77-81ac-2d65d3eb03af)

```
sns.pairplot(dt)
```
![Screenshot 2024-05-03 154723](https://github.com/Harsayazheni/Expt02-Introduction-to-Data-Science/assets/118708467/d9fefb7d-5730-4c12-8638-42441020f636)
![Screenshot 2024-05-03 154739](https://github.com/Harsayazheni/Expt02-Introduction-to-Data-Science/assets/118708467/32cac6cc-7397-4215-8575-484e3643b9fb)

# RESULT
      Thus, Exploratory Data Analysis for the given dataset is done successfully.
