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
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/2cc77cad-f973-44f9-bc9b-75f480fd730f)
```
df.info()
```
![image](https://github.com/user-attachments/assets/03f5b33e-b64e-4bcd-b30e-29f51bbaa386)
```
df.shape
```
![image](https://github.com/user-attachments/assets/a1719c5f-95a0-425a-a2cd-6a2f107fa7d1)
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/ee971918-fa69-43cd-92b7-cedbb540cdaf)
```
df.shape
```
![image](https://github.com/user-attachments/assets/65d36958-6d4b-4c2c-86f6-299ff66fab3e)
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/e7f8d709-24c3-4e23-b424-02a265a66923)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/75d80cc9-c725-4a1b-8259-3aebcf9a088a)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/b5001ced-9dc1-4727-a9c5-7fc39f9398bf)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/eb38de84-99fc-467d-828b-e7e264d36b73)
```
df
```
![image](https://github.com/user-attachments/assets/2415560a-5a35-4999-947f-9d2241d80b17)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/934480ee-f734-49e6-9f01-326d647671d0)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/effc86a1-8d1d-49ee-88e3-df85b2734858)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/464f99c0-544c-437a-a76d-56a965af357e)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/1204e0f1-6ec6-4ca6-afb3-202e169c75a8)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/72d06431-b32f-474e-bbac-a989bafe855f)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/88026c58-c171-4161-b4fa-cb3640f8ab02)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/7a0a0e0c-06dd-465e-b56b-aae3f228e433)
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/1baa0e7b-4c7b-47b7-8d95-12130da738a2)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/447a89ee-b93d-4d91-b83c-d868eedf7ee0)
```
numeric_df = df.select_dtypes(include=[np.number])
corr = numeric_df.corr()
sns.heatmap(corr, annot=True)
```
![image](https://github.com/user-attachments/assets/5e7b741b-5a7a-4a72-9621-ff5d57b41d75)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/f3547122-82af-4467-a312-9f46407b9ec0)


# RESULT
 We have performed Exploratory Data Analysis on the given data set successfully.       
