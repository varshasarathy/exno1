NAME: Varsha Sarathy       
REG NO: 212223040233




# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
import pandas as pd df=pd.read_csv("/content/SAMPLEIDS.csv") df
 ![image](https://github.com/user-attachments/assets/da6292bc-b818-4be8-89da-b3a38fc79eb1)

df.head()
![image](https://github.com/user-attachments/assets/2aadec33-d2bb-4c79-b1de-b03dcb0ed922)

df.tail(5)
![image](https://github.com/user-attachments/assets/6da97a91-7186-4820-9c68-57e130bdacd9)

df.isnull()
![image](https://github.com/user-attachments/assets/c693df0b-ae6b-4ac2-8249-c41369b4f6cc)

df.notnull()
![image](https://github.com/user-attachments/assets/45495a35-d95e-46bd-ac5a-2d3dc74136c8)

df.dropna(axis=0)
![image](https://github.com/user-attachments/assets/4af9a66a-cf25-4340-86f1-adbcb9245fd1)

df.dropna(axis=1)

![image](https://github.com/user-attachments/assets/f9a817f1-bc63-4d7d-9419-2a65cfe4918f)

df.fillna(0)
![image](https://github.com/user-attachments/assets/35a1d03d-56d0-4c47-989e-891864753c64)

print(df.shape)

![image](https://github.com/user-attachments/assets/b5dad093-a8da-4d0c-8cd2-0f697604bf5e)

IQR:

import pandas as pd import seaborn as sns ir=pd.read_csv('/content/iris.csv') ir

![image](https://github.com/user-attachments/assets/1ba6e510-eec3-4e2c-855a-774a788b5118)

ir.describe()

![image](https://github.com/user-attachments/assets/230dc2c3-6e34-4435-82a3-2ec422b239f0)

sns.boxplot(x='sepal_width',data=ir)

![image](https://github.com/user-attachments/assets/da895755-630e-4df7-9c5b-8215b609433a)

c1=ir.sepal_width.quantile(0.25) c3=ir.sepal_width.quantile(0.75) iq=c3-c1 print(c3)

![image](https://github.com/user-attachments/assets/37742cfd-e3e0-4d03-aa88-62248649882d)

rid=ir[((ir.sepal_width<(c1-1.5iq))|(ir.sepal_width>(c3+1.5iq)))] rid['sepal_width']

![image](https://github.com/user-attachments/assets/427fa09a-dfb0-4067-b642-58733c57c407)

delid=ir[~((ir.sepal_width<(c1-1.5iq))|(ir.sepal_width>(c3+1.5iq)))] delid

![image](https://github.com/user-attachments/assets/bbf9b774-c7a3-46b9-8f66-b449501ca5e1)

sns.boxplot(x='sepal_width',data=delid)

![image](https://github.com/user-attachments/assets/656dbc51-16b2-4b27-934e-20033ecf8c50)

Z SQUARE:

import matplotlib.pyplot as plt import pandas as pd import pandas as pd import numpy as np import scipy.stats as stats dataset=pd.read_csv("/content/heights.csv") dataset

![image](https://github.com/user-attachments/assets/b3368bdd-3e7e-4481-8036-7de5d66d39ed)

df = pd.read_csv("heights.csv") q1 = df['height'].quantile(0.25) q2 = df['height'].quantile(0.5) q3 = df['height'].quantile(0.75) iqr = q3-q1 iqr

![image](https://github.com/user-attachments/assets/2d469c38-0ce1-4a5b-919d-39ceda402739)

low = q1 - 1.5*iqr low

![image](https://github.com/user-attachments/assets/f491bec9-479c-4c46-ac8a-463ab38c1ab9)

high = q3 + 1.5*iqr high

![image](https://github.com/user-attachments/assets/bff57623-9178-45ba-88b8-cad840ec4265)

df1 = df[((df['height'] >=low)& (df['height'] <=high))] df1

![image](https://github.com/user-attachments/assets/a49809ae-c28d-4f6e-8a7b-53c848d32b53)

z = np.abs(stats.zscore(df['height'])) z

![image](https://github.com/user-attachments/assets/0afcfa6e-30fc-4f2e-94de-2e9b836a02dd)

df1 = df[z<3] df1

![image](https://github.com/user-attachments/assets/de94c152-5df5-4086-b6d4-d391fb35badf)


# Result
               Thus the Data Cleaning Process and Detecting and Removal of Outliers is executed successfully.   
