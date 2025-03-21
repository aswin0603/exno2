# Ex. No. 02 - Exploratory Data Analysis

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
### Importing the required libraries and csv file.
``` python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df = pd.read_csv('/content/titanic_dataset.csv')
df
```
![image](https://github.com/user-attachments/assets/c2499a8c-4d4b-4218-9752-a6e5acca0426)

### Analysis Processess

``` python
df.info()
```
![image](https://github.com/user-attachments/assets/240975f3-b621-437f-b503-e0f0d1b4a675)

``` python
df.shape
```
![image](https://github.com/user-attachments/assets/2c7eeafa-5a54-4115-ab3b-e9340ff9e1cb)

``` python
df.head(4)
```
![image](https://github.com/user-attachments/assets/68618055-f00d-44d9-8173-927f27b50460)

``` python
df.describe()
```
![image](https://github.com/user-attachments/assets/7cfc1ee6-c5c0-4535-a8a3-b92298058d14)

``` python
df.set_index("PassengerId", inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/ff543a9e-5685-4003-9cb2-093818181d2a)

``` python
df.nunique()
```
![image](https://github.com/user-attachments/assets/c20bf8a9-c514-4f75-82d4-4ff620f5655a)

``` python
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/d632baa3-188e-4b65-9f11-a1dc73811c90)

``` python
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/05dea6e5-78d4-40a0-9551-1a82d4743b58)

``` python
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/419f5490-a6de-401c-8a50-b7729ed302aa)

``` python
df.rename(columns={"Sex":"Gender"},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/73cd0f4d-cb4c-4cc9-bbae-c713db92f975)

``` python
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/e11dd0e1-652b-4aca-bccd-0287ce70fcae)

## Multivariate Analysis

``` python
sns.catplot(x='Survived',hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/ed1197cd-786b-43bd-977e-7ff3d9202207)

``` python
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/fd57e3c9-7624-4a83-9e15-0aee68bffe59)

``` python
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/23a56e8a-27fb-4d55-8657-4b9a0acdddb4)

``` python
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/36031428-0e59-4f41-b5af-faa1ff16f5e7)

``` python
ig,ax1 = plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/96a94b58-8dd4-4786-b6a3-2ed18037d73c)


``` python
sns.catplot(data=df,col = "Survived",x = "Gender",hue="Pclass",kind = "count")
```
![image](https://github.com/user-attachments/assets/91f26ef3-e1ba-430c-874b-97cc22791611)

### Co-Relation
--pending result--

``` python
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/ba70be43-ac2c-414d-b93b-72b65ddf7b0b)


# RESULT
        <<INCLUDE YOUR RESULT HERE>>

### Name : ASWIN B
### Register Number : 212224110007
