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

## CODING AND OUTPUT:

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
<img width="1357" height="614" alt="image" src="https://github.com/user-attachments/assets/e1d51ffe-c15e-4bbd-8de7-617f24f6a177" />

```
df.info()
```
<img width="545" height="514" alt="image" src="https://github.com/user-attachments/assets/cffc0dd1-0d38-4242-8334-a2f69f1eb5ca" />

```
df.describe()
```
<img width="985" height="450" alt="image" src="https://github.com/user-attachments/assets/aaf0aeee-805a-4095-a689-765e3eb66aaf" />

```
df.dtypes
```
<img width="289" height="637" alt="image" src="https://github.com/user-attachments/assets/fb38c5cb-5d55-4c83-990a-62a2e8974b62" />

```
df.shape
```
<img width="820" height="125" alt="image" src="https://github.com/user-attachments/assets/5c948857-5d51-432f-86e4-2fe76c60a64d" />

```
df.value_counts()
```
<img width="1383" height="657" alt="image" src="https://github.com/user-attachments/assets/d9b30e53-3b9a-48cf-b427-fef0415c423f" />

```
df['Age'].value_counts()
```
<img width="280" height="633" alt="image" src="https://github.com/user-attachments/assets/0b3c2878-2ead-4156-9d5b-5661247236fa" />

```
df.set_index("PassengerId", inplace=True)
df
```
<img width="1382" height="684" alt="image" src="https://github.com/user-attachments/assets/e66242b9-f3e8-46bc-8435-4026c8f70c0b" />

```
df.nunique()
```
<img width="251" height="584" alt="image" src="https://github.com/user-attachments/assets/fec80c6f-8065-4528-8a65-40aff6297b28" />

```
sns.countplot(data=df,x='Survived')
```
<img width="862" height="651" alt="image" src="https://github.com/user-attachments/assets/fd2eb0bc-a010-426b-8073-064d296f70fb" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1398" height="645" alt="image" src="https://github.com/user-attachments/assets/f284d448-43b8-40ff-ac2e-b1a91930baa4" />


```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=0.7)
```
<img width="990" height="707" alt="image" src="https://github.com/user-attachments/assets/cbbfaef6-34cb-4484-b9ac-1a7c7e408875" />

```
df.boxplot(column="Age",by="Survived")
```
<img width="828" height="678" alt="image" src="https://github.com/user-attachments/assets/16be5316-a4a6-4613-920d-cd59253fa12f" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="866" height="638" alt="image" src="https://github.com/user-attachments/assets/eef3f87c-792e-4bee-aef0-5186fab16e38" />

```
fig, axl=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=axl,x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="844" height="585" alt="image" src="https://github.com/user-attachments/assets/de11f52b-eea1-46ba-834b-939d13459db5" />


```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="803" height="613" alt="image" src="https://github.com/user-attachments/assets/66972409-cb33-4b28-aade-b645bb6ffe23" />

```
import seaborn as sns
sns.catplot(x='Pclass',y="Age",hue="Gender",col="Survived",kind="box",data=df)
```
<img width="1385" height="720" alt="image" src="https://github.com/user-attachments/assets/f8e8f957-aef8-40f8-a1b9-45795d2bbbeb" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue='Pclass',kind="count")
```
<img width="1378" height="702" alt="image" src="https://github.com/user-attachments/assets/ea28f9be-c44a-42ce-8487-9bb9518470ff" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)

```
<img width="733" height="675" alt="image" src="https://github.com/user-attachments/assets/f862c560-916f-47cc-a6f7-0ed4ff70105e" />

```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```
![Uploading image.png…]()




# RESULT
        <<INCLUDE YOUR RESULT HERE>>
