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
df=pd.read_csv(r"C:\Users\admin\Desktop\Python_jupyter\ML LEARN\intro_to_datascience\data_sets\titanic_dataset.csv")
df
df.info()
#DISPLAY NO OF ROWS AND COLUMNS
df.shape
#SET PASSENGER ID AS INDEX COLUMN
df.set_index('PassengerId',inplace=True)
df.describe()
**CATEGORICAL DATA ANALYSIS**
sex_counts = df['Sex'].value_counts()
print("Sex Counts:\n", sex_counts)

embarked_counts = df['Embarked'].value_counts()
print("\nEmbarked Counts:\n", embarked_counts)

pclass_counts = df['Pclass'].value_counts()
print("\nPclass Counts:\n", pclass_counts)
df.nunique()
**UNIVARIATE ANALYSIS**
# USE COUNTPLOT AND PERFORM UNIVARIATE ANALYSIS FOR THE "SURVIVED" COLUMN IN TITANIC DATASET
sns.countplot(data=df,x='Survived')
# IDENTIFY UNIQUE VALUES IN "PASSENGER CLASS" COLUMN
print(' UNIQUE VALUES IN "PASSENGER CLASS" COLUMN :',df['Pclass'].unique())
# RENAMING COLUMN
df.rename(columns = {'Sex':'Gender'}, inplace = True)
df.head()
**BIVARIATE ANALYSIS**
# USE CATPLOT METHOD FOR BIVARIATE ANALYSIS
sns.catplot(x='Gender',col='Survived',kind='count',data=df)
sns.catplot(x='Survived',hue='Gender',kind='count',data=df)
fig, ax1 = plt.subplots(figsize=(8, 5))
graph = sns.countplot(data=df, x='Embarked', ax=ax1)
graph.set_xticklabels(graph.get_xticklabels())
for p in graph.patches:
    height = p.get_height()
    graph.text(p.get_x() + p.get_width() / 2, height + 0.5, int(height), ha="center")
plt.show()
# USE BOXPLOT METHOD TO ANALYZE AGE AND SURVIVED COLUMN
sns.boxplot(data=df,x='Survived',y='Age')
plt.title('Boxplot of Age by Survival Status')
plt.show()
**MULTIVARIATE ANALYSIS**
# USE BOXPLOT METHOD AND ANALYZE THREE COLUMNS(PCLASS,AGE,GENDER)
sns.boxplot(data=df,x='Pclass',y='Age',hue='Gender')
_=plt.title('Boxplot of Age by Pclass and Gender')
# USE CATPLOT METHOD AND ANALYZE THREE COLUMNS(PCLASS,SURVIVED,GENDER)
sns.catplot(data=df,x='Pclass',col='Survived',hue='Gender',kind='count')
import numpy as np 
num_df = df.select_dtypes(include=np.number)
# Heatmap to visualize correlations between numerical features
plt.figure(figsize=(10, 6))
sns.heatmap(num_df.corr(), annot=True, cmap='coolwarm', fmt='.2f')
plt.title('Correlation Heatmap')
plt.show()
# Pairplot to visualize pairwise relationships in the dataset
sns.pairplot(df)
plt.show()

```
### EXPLORATORY DATA ANALYSIS:

#### DATA LOADING:
![image](https://github.com/user-attachments/assets/37572406-0910-41f0-bddb-fc3148f0c62b)

#### Info:
![image](https://github.com/user-attachments/assets/45fb1875-b927-4246-8efb-a40b16d06581)

#### Shape:
![image](https://github.com/user-attachments/assets/48947799-b127-4d85-8d8c-f639f83c5a08)

#### DESC:
![image](https://github.com/user-attachments/assets/00f76e27-9e0b-4309-9030-cc3f28320dc5)

#### CATEGORICAL DATA ANALYSIS:
![image](https://github.com/user-attachments/assets/255c56a0-37b6-4748-b4bc-440292389ba4)
![image](https://github.com/user-attachments/assets/5e21be4c-9627-4d10-a67c-05fdfeb2f542)

#### UNIVARIATE ANALYSIS:
![image](https://github.com/user-attachments/assets/75ccc7e7-9fa9-4d1f-b443-5377a8dffc3e)
![image](https://github.com/user-attachments/assets/49b72ed8-0376-4e28-8788-2cf22caece45)

#### BIVARIATE ANALYSIS:
![image](https://github.com/user-attachments/assets/266370e0-f9f0-43fd-931b-9e5a420cdecf)
![image](https://github.com/user-attachments/assets/926c3ba5-1b9e-46a9-8048-0f40a599bfd7)
![image](https://github.com/user-attachments/assets/4eaee25d-3341-493c-bf48-e372204b14ca)
![image](https://github.com/user-attachments/assets/c2b2b8e8-1753-4638-910f-7f8417abfb27)

#### MULTIVARIATE ANALYSIS:
![image](https://github.com/user-attachments/assets/2a6512c0-9ff7-48a8-8225-edf9819c0253)
![image](https://github.com/user-attachments/assets/d0a29827-8b76-43a3-9c6b-a65fe661bccf)
![image](https://github.com/user-attachments/assets/cca05da1-9fe8-48e1-9bb2-a431d94d845a)
![image](https://github.com/user-attachments/assets/1a18c5ac-7e26-4f81-827b-933f93493638)


# RESULT
        <<INCLUDE YOUR RESULT HERE>>
