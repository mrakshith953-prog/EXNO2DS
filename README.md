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

<img width="1454" height="492" alt="image" src="https://github.com/user-attachments/assets/74c55518-c104-43ac-89b4-be6e0d9e8af8" />
df.shape

<img width="204" height="51" alt="image" src="https://github.com/user-attachments/assets/90129d20-0ff2-4fd3-9ca1-1f5d9b25d8de" />
df.set_index("PassengerId",inplace=True)
df

<img width="1275" height="550" alt="image" src="https://github.com/user-attachments/assets/ed61f5bb-3d5d-4d88-9572-4a49a124abea" />
df.nunique()

<img width="517" height="253" alt="image" src="https://github.com/user-attachments/assets/6096fa2a-3b23-451e-bb99-516350b07682" />
df['Sex'].value_counts()

<img width="286" height="95" alt="image" src="https://github.com/user-attachments/assets/8a89c3fb-00cc-4e68-afdd-93f2d478de4b" />
df.Survived.unique()

<img width="215" height="36" alt="image" src="https://github.com/user-attachments/assets/8ad49eba-f6e2-4d87-b855-96f2753d62e6" />
df.rename(columns={"Sex":"Gender"},inplace=True)
df

<img width="1267" height="550" alt="image" src="https://github.com/user-attachments/assets/747878b3-58e4-4ceb-a516-51aaeb1f999c" />
import seaborn as sns
sns.countplot(data=df)

<img width="795" height="542" alt="image" src="https://github.com/user-attachments/assets/f11ec43a-a2f1-4f9f-b1d6-ab6dbe9c8942" />
sns.countplot(x="Survived",hue="Gender",data=df)

<img width="799" height="566" alt="image" src="https://github.com/user-attachments/assets/1565ace3-a880-4836-b639-19fd6b9ce755" />
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")

<img width="790" height="634" alt="image" src="https://github.com/user-attachments/assets/7e350882-364d-458b-a0fc-9e7e69eb7efb" />
sns.catplot(x="Survived",hue="Gender",data=df,kind="violin")

<img width="786" height="637" alt="image" src="https://github.com/user-attachments/assets/b22ca0e2-732c-4bf7-aec5-60d8da35d297" />
sns.boxplot(data=df)

<img width="756" height="543" alt="image" src="https://github.com/user-attachments/assets/c520cd94-4f38-4276-bceb-d10a7a62bd42" />
df.boxplot(column="Survived",by="Gender")

<img width="781" height="599" alt="image" src="https://github.com/user-attachments/assets/deda1540-202c-4f7a-a3af-61dac323259c" />
sns.scatterplot(data=df)

<img width="752" height="559" alt="image" src="https://github.com/user-attachments/assets/5bd35aba-e8a9-4442-a70e-255d7f2a28ae" />
sns.scatterplot(x=df['Age'],y=df['Fare'])

<img width="738" height="567" alt="image" src="https://github.com/user-attachments/assets/309d9ce1-a07e-4cf3-9887-55434acb5bfe" />
sns.jointplot(x='Age',y='Fare',data=df)

<img width="833" height="752" alt="image" src="https://github.com/user-attachments/assets/9cbb540f-231e-48f9-8e29-506e63d3adfe" />
sns.jointplot(x='Age',y='Fare',data=df,kind="kde")

<img width="825" height="759" alt="image" src="https://github.com/user-attachments/assets/d070a3e7-c7ae-4841-bd71-fb4f580c0aa8" />
sns.jointplot(x='Age',y='Fare',data=df,kind="hist")

<img width="760" height="757" alt="image" src="https://github.com/user-attachments/assets/6c119ee1-7be1-43f4-9e0a-b745d9789965" />
sns.pairplot(data=df)

<img width="1385" height="698" alt="image" src="https://github.com/user-attachments/assets/065f9a32-30fd-4dc9-9602-0cbd62344065" />
<img width="1384" height="706" alt="image" src="https://github.com/user-attachments/assets/23a3ed59-b867-4f0d-a221-9d4ebfcde123" />
corr1=df.select_dtypes(include=['number']).corr()
sns.heatmap(corr1,annot=True)

<img width="667" height="552" alt="image" src="https://github.com/user-attachments/assets/c8615b50-c301-429a-8b21-e88924c89665" />
sns.catplot(x='Gender',col='Survived',data=df,kind='count',color='green')

<img width="1245" height="637" alt="image" src="https://github.com/user-attachments/assets/178613dc-835a-4288-a432-f57e025b408b" />
# RESULT
       All coditions are execute Successfully
