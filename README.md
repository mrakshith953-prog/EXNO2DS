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
        import pandas as pd
df=pd.read_csv('titanic_dataset.csv')
df
<img width="1315" height="500" alt="image" src="https://github.com/user-attachments/assets/2ad1c92b-4252-4cfb-843a-f4000a314bf2" />

df.shape

<img width="158" height="48" alt="image" src="https://github.com/user-attachments/assets/17c84db1-a5cc-4478-8d67-d0b4c085ccb9" />
df.set_index("PassengerId",inplace=True)
df

<img width="1249" height="537" alt="image" src="https://github.com/user-attachments/assets/427dad2a-84e7-49ba-809b-ba8e314afcb9" />
df.nunique()

<img width="151" height="262" alt="image" src="https://github.com/user-attachments/assets/532a4a85-acb6-41c6-aabe-21aaf21d4a19" />
df['Sex'].value_counts()

<img width="231" height="102" alt="image" src="https://github.com/user-attachments/assets/e0df01c4-4144-4577-b215-4095304e1836" />
df.Survived.unique()

<img width="136" height="35" alt="image" src="https://github.com/user-attachments/assets/65a60088-7b3b-4c20-a152-aad924e299e3" />
df.rename(columns={"Sex":"Gender"},inplace=True)
df

<img width="1248" height="525" alt="image" src="https://github.com/user-attachments/assets/73f5571e-225a-43e5-aed4-e726e045f6a7" />
import seaborn as sns
sns.countplot(data=df)

<img width="720" height="540" alt="image" src="https://github.com/user-attachments/assets/f22bd553-0ac2-4abc-9821-3125123ed9f3" />
sns.countplot(x="Survived",hue="Gender",data=df)

<img width="703" height="560" alt="image" src="https://github.com/user-attachments/assets/c06ab4d9-e095-4443-8dd0-a86012c24ea3" />
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")

<img width="708" height="631" alt="image" src="https://github.com/user-attachments/assets/c85ddaee-6adb-4ed5-994f-a0e2f94aa731" />
sns.catplot(x="Survived",hue="Gender",data=df,kind="violin")

<img width="723" height="623" alt="image" src="https://github.com/user-attachments/assets/1c28bfa0-115c-4163-8ddc-aa39a5c0cf31" />
sns.boxplot(data=df)

<img width="682" height="536" alt="image" src="https://github.com/user-attachments/assets/25bdebea-37b9-4161-aaca-b88cd401b579" />
df.boxplot(column="Survived",by="Gender")

<img width="695" height="598" alt="image" src="https://github.com/user-attachments/assets/b2c21a01-39b9-44fd-9049-df39d8c09e97" />
sns.scatterplot(data=df)

<img width="687" height="557" alt="image" src="https://github.com/user-attachments/assets/89a106cb-d4c3-4279-ba37-fe542604abfe" />
sns.scatterplot(x=df['Age'],y=df['Fare'])

<img width="714" height="560" alt="image" src="https://github.com/user-attachments/assets/e74b5f03-2d10-4a6b-b047-935bf35b5ff6" />
sns.jointplot(x='Age',y='Fare',data=df)

<img width="723" height="760" alt="image" src="https://github.com/user-attachments/assets/cba94320-6bb3-42e0-b0c0-276e1ab76ddf" />
sns.jointplot(x='Age',y='Fare',data=df,kind="kde")

<img width="717" height="756" alt="image" src="https://github.com/user-attachments/assets/57e51396-e5a5-4e64-86aa-ed084df2133a" />
sns.jointplot(x='Age',y='Fare',data=df,kind="hist")

<img width="726" height="754" alt="image" src="https://github.com/user-attachments/assets/3831b557-fb8c-4f5c-be32-0da8ad7376fe" />
sns.pairplot(data=df)

<img width="1373" height="691" alt="image" src="https://github.com/user-attachments/assets/24150460-5d79-4129-8d4c-78318dea8429" />

<img width="1391" height="697" alt="image" src="https://github.com/user-attachments/assets/4c71d06e-f584-42b5-a4f9-83adb57b2948" />
corr1=df.select_dtypes(include=['number']).corr()
sns.heatmap(corr1,annot=True)

<img width="657" height="543" alt="image" src="https://github.com/user-attachments/assets/1768ffd2-cb81-4394-994c-8ab230cee32f" />
sns.catplot(x='Gender',col='Survived',data=df,kind='count',color='green')

<img width="1241" height="633" alt="image" src="https://github.com/user-attachments/assets/288c6397-da5e-4200-a4d1-83de8411db3d" />
# RESULT
       All condition are execute Successfully
