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
# Developed By: RITHISH P
# Register Number: 212223230173

1) Read and display DataFrame
```py
import pandas as pd
import numpy as np
data=pd.read_csv("/content/Data_set.csv")
```
output

![Screenshot 2024-09-06 031451](https://github.com/user-attachments/assets/85e9207b-b3be-49d9-9a9c-f64f93c79f78)

2) Display head
```py
df = pd.DataFrame(data)
print(df)
df.head()
```
output

![Screenshot 2024-09-06 031652](https://github.com/user-attachments/assets/12b6061e-de86-44fc-bce8-00b9a1d3fb70)

3) Display tail
```py
df.tail()
```
output

![Screenshot 2024-09-06 031957](https://github.com/user-attachments/assets/9497144f-7a32-403d-b5b1-2b4134c9c6bf)

4) Info of datafram
```py
df.info()
```
output

![Screenshot 2024-09-06 032031](https://github.com/user-attachments/assets/7aa46416-11f3-4ed5-ae4b-6ecfff9ac5f6)

5) To Find Null Value
```py
df.isnull().sum()
```
output

![Screenshot 2024-09-06 032207](https://github.com/user-attachments/assets/de5131d0-d108-4511-8e86-64f740443bfe)

6) Describe
```py
df.describe()
```
output

![Screenshot 2024-09-06 033738](https://github.com/user-attachments/assets/df0c999f-d886-4e15-a416-3f2e8c615015)

7) Fillna Method
```py
df_filled = df.fillna(0)
print(df_filled)
```
output

![Screenshot 2024-09-06 033910](https://github.com/user-attachments/assets/44e39700-fe6d-43c5-9dab-a0ae12956d07)

8) Forward and Backward
```py
df_ffilled = df.ffill()
print(df_ffilled)
```
output

![Screenshot 2024-09-06 033951](https://github.com/user-attachments/assets/2c0fd518-0a84-407b-8833-6dcc772246ba)

```py
df_bfilled = df.bfill()
print(df_bfilled)
```
output

![Screenshot 2024-09-06 034014](https://github.com/user-attachments/assets/e0bee283-5fcf-42ec-ba42-5174f3bae008)

9) Dropna
```py
df.dropna()
```
output

![Screenshot 2024-09-06 034142](https://github.com/user-attachments/assets/7a6cb997-dab6-49ce-b30c-7cb68d0358c4)

10) iloc
```py
df.iloc[:4]
```
output

![Screenshot 2024-09-06 034219](https://github.com/user-attachments/assets/6b802529-2cf5-4119-8837-4f2357782d90)

11) CALCULATE MEAN VALUE OF A COLUMN AND FILL IT WITH NULL VALUES
```py
df_mean1=df['num_episodes'].fillna(df['num_episodes'].mean())
df_mean1
```
output

![Screenshot 2024-09-06 034256](https://github.com/user-attachments/assets/2761c103-3b32-4c5f-98b2-b7aa56d2dfbb)

```py
df_mean3=df['current_overall_rank'].fillna(df['current_overall_rank'].mean())
df_mean3
```

output

![Screenshot 2024-09-06 034311](https://github.com/user-attachments/assets/e95ddcc4-6b1f-421b-9728-5c7b49c4ddb7)

# IQR

12) Read and Display
```py
import pandas as pd
import seaborn as sns
df=pd.read_csv('/content/heights (1).csv')
print(df)
```

output

![Screenshot 2024-09-06 034450](https://github.com/user-attachments/assets/964555a5-2c1a-4cbe-9fd8-f3b7b126d2d4)

13) USE BOXPLOT FUNCTION HERE TO DETECT OUTLIER
```py
sns.boxplot(df)
```
output

![Screenshot 2024-09-06 034559](https://github.com/user-attachments/assets/2ca66f76-8353-4f21-b9aa-780df077d6bc)

# Scatterplot
```py
sns.scatterplot(df)
```
output

![Screenshot 2024-09-06 034626](https://github.com/user-attachments/assets/f22b8822-b353-476c-a455-470c9ef15529)

# Mean
```py
mean=np.mean(data)
mean
std=np.std(data)
std
```
output

![Screenshot 2024-09-06 034658](https://github.com/user-attachments/assets/e97ae487-1a44-4ed9-b5e6-1516a9ebb94c)

# z score
```py
from scipy import stats
import numpy as np
import pandas as pd
import seaborn as sns
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,158]
df=pd.DataFrame(data)
df=pd.DataFrame(data)
mean=np.mean(data)
mean

std=np.std(data)
std
z=np.abs(stats.zscore(df))
z
```
output

![Screenshot 2024-09-06 034753](https://github.com/user-attachments/assets/173be936-363e-420b-9608-b032596bc41b)

# Remove outliers
```py
df_cleaned = df[(z <= threshold)]
df_cleaned
```
output

![Screenshot 2024-09-06 034827](https://github.com/user-attachments/assets/2513178a-71a9-4588-8f22-7b9215471f92)

# USE BOXPLOT FUNCTION HERE TO CHECK OUTLIER IS REMOVED
```py
sns.boxplot(df_cleaned)
```
output

![Screenshot 2024-09-06 034855](https://github.com/user-attachments/assets/d776f31e-f814-436e-923d-b930ee6a65e9)

```py
sns.scatterplot(df_cleaned)
```
output

![Screenshot 2024-09-06 034950](https://github.com/user-attachments/assets/56ba8bfc-d186-4712-96e1-d1333b028be4)

# Result
Thus the code executed successfully.
