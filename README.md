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
# RESULT
      Thus, Exploratory Data Analysis for the given dataset is done successfully.
