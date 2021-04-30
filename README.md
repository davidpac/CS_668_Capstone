# CS_668_Capstone
#codes are as follow


#I have started with importing the  necessary libraries

! pip install seaborn
import matplotlib.pyplot as plt
import seaborn as sns
%matplotlib inline
from scipy import stats
import pandas as pd

from google.colab import drive
drive.mount('/content/drive')

df = pd.read_csv("/content/google.csv",sep=",", encoding='cp1252')

df.info()
df.head()
df.describe()
df.corr()
df.dtypes
df.describe(include='all')
df.isnull().sum()
missing_data = df.isnull()
for column in missing_data.columns.values.tolist():
    print(column)
    print (missing_data[column].value_counts())
    print("")   
   

df.describe(include=['object'])
df.dropna()
df.corr()
from scipy import stats

pearson_coef, p_value = stats.pearsonr(df['Maximum_Installs'], df['Length'])
print("The Pearson Correlation Coefficient for Maximum_Installation is", pearson_coef, " with a P-value of P =", p_value) 
! pip install seaborn
import matplotlib.pyplot as plt
import seaborn as sns
%matplotlib inline 

#The followings are the plots of dependencies between installs and length
sns.regplot(x="Maximum_Installs", y="Length", data=df)
plt.ylim(0,)
sns.boxplot(x="Length", y="Maximum_Installs", data=df)
from sklearn.linear_model import LinearRegression
lm1 = LinearRegression()
lm1

x = df[['Maximum_Installs']]
y = df['Length']
lm1.fit(x,y)
Yhat=lm1.predict(x)
Yhat[0:4]   

lm1.intercept_

lm1.coef_

df.head()

df2=df.drop(['App Name', '1_19', '20_41', '42_50','App_Id',"Category", 
             "Installs", "Free", "Currency", "Size", 
             "Minimum_Android", "Developer_Id", "Developer_Website", 
             "Developer_Email", "Released", "Last_Updated", 
             "Content_Rating", "Privacy_Policy", "Ad_Supported", 
             "In_App_Purchases", "Editors_Choice"], axis='columns')
             
             
             
 df2.isnull().sum()
 
 df_word= df[["Length","Words", "Maximum_Installs", "Minimum_Installs", "Category"]]
 
 from scipy import stats

pearson_coef, p_value = stats.pearsonr(df_word['Maximum_Installs'], df_word['Words'])
print("The Pearson Correlation Coefficient for Maximum_Installation is", pearson_coef, " with a P-value of P =", p_value)

df_word.head()
df_word=df_word.dropna()
df_word.corr()
df_1_10=df[["Length","1_10", "Maximum_Installs", "Minimum_Installs", "Category"]]
df_11_20=df[["Length","11_20", "Maximum_Installs", "Minimum_Installs", "Category"]]
df_21_30=df[["Length","21_30", "Maximum_Installs", "Minimum_Installs", "Category"]]
df_31_40=df[["Length","31_40", "Maximum_Installs", "Minimum_Installs", "Category"]]
df_41_50=df[["Length","41_50", "Maximum_Installs", "Minimum_Installs", "Category"]]

import statistics as stats
print("variance is", stats.mean(df_1_10["1_10"]))

sns.regplot(x="Maximum_Installs", y="Length", data=df_1_19)
plt.ylim(0,)

sns.regplot(x="Maximum_Installs", y="Length", data=df_42_50)
plt.ylim(0,)
