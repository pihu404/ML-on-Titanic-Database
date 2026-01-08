# Import necessary libraris
import pandas as pd
import numpy as np
from sklearn.preprocessing import LabelEncoder , StandardScaler
import matplotlib.pyplot as plt
import seaborn as sns
# Load the titanic dataset
url = 'https://raw.githubusercontent.com/datasciencedojo/datasets/master/titanic.csv'
df = pd.read_csv(url)
df.head()
# Check for missing values
print("Missing values in each column : ")
print(df.isnull().sum())
# Print the number of duplicate rows
print(f"Number of duplicate rows : {df.duplicated().sum()}")
#drop duplicate rows
df = df.drop_duplicates()
#fill missing values
df['Age'] = df['Age'].fillna(df['Age'].mean()) # Corrected: Fill Age with Age's mean
df['Embarked'] = df['Embarked'].fillna(df['Embarked'].mode()[0]) # Added: Fill Embarked with Embarked's mode
# Encode categorial columns
le = LabelEncoder()
df['Sex']= le.fit_transform(df['Sex'])
df['Embarked']= le.fit_transform(df['Embarked'])
df.head()
#scale numeric features
scaler = StandardScaler()
df[['Age', 'Fare']]= scaler.fit_transform(df[['Age', 'Fare']])
# sort by fare
df_sorted = df.sort_values(by ='Fare' , ascending=False)
df_sorted.head()
#filter passengers who paid more than average fair
high_fare = df[df['Fare']> df['Fare'].mean()]
high_fare.head()
#create a new column (symbolic AgeGroup based on scaled Age)
df['AgeGroup']= pd.cut(df['Age'], bins=[-np.inf, -1,0.0, 0.8, 1.6, 3], labels=['Erorr', 'Child', 'Teen', 'Adult', 'Senior'])
df.head()
#countplot of survival
sns.countplot(data=df, x='Survived')
plt.title('Survival Count')
plt.show()
# histogram of fare
sns.histplot(df['Fare'], kde= True) # Corrected: 'hisplot' to 'histplot'
plt.title('Fare Distribution')
plt.show()
