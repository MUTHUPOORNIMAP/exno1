# Exno:1
Data Cleaning Process
## NAME:MUTHU POORNIMA P
## REGISTER NO:212224240099
## DATE:17-09-2025
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
```
import numpy as np
import pandas as pd
data=pd.read_csv("/content/SAMPLEIDS.csv")
data
```
OUTPUT:

<img width="1085" height="882" alt="image" src="https://github.com/user-attachments/assets/8639cd7a-160a-4531-b055-8cfbf4ae934e" />

```
data.head(4)
```
OUTPUT:

<img width="1097" height="321" alt="image" src="https://github.com/user-attachments/assets/fab955db-a66b-4a60-8685-46cb6d286a73" />

```
data.tail(7)
```
OUTPUT:

<img width="1136" height="393" alt="image" src="https://github.com/user-attachments/assets/35a672f8-e1d9-467f-a3ad-6f11d00c47f6" />

```
data.isnull()
```
OUTPUT:

<img width="951" height="924" alt="image" src="https://github.com/user-attachments/assets/751e8ecc-809f-446d-bd03-715364a39992" />

```
data.notnull()
```
OUTPUT:

<img width="927" height="924" alt="image" src="https://github.com/user-attachments/assets/084dc210-434e-4244-ab95-0552d84fb9a0" />

```
data.isnull().sum()
```
OUTPUT:

<img width="304" height="619" alt="image" src="https://github.com/user-attachments/assets/040038c5-722f-4a3e-9052-0d8c3b0e6cbf" />

```
data.isnull().any()
```

OUTPUT:

<img width="275" height="618" alt="image" src="https://github.com/user-attachments/assets/9f230b6a-681b-47a3-bff1-7f518f876316" />

```
data.dropna(axis=0)
```
OUTPUT:

<img width="1151" height="615" alt="image" src="https://github.com/user-attachments/assets/93f6d351-1fc8-40de-9991-db1dd69967b7" />

```
data.dropna(axis=1)
```
OUTPUT:

<img width="394" height="925" alt="image" src="https://github.com/user-attachments/assets/f81070fe-ce12-42c1-8333-8bb6114acb47" />

```
data.fillna(0)
```
OUTPUT:

 <img width="1139" height="932" alt="image" src="https://github.com/user-attachments/assets/f4de8985-8d2d-4327-a839-640be917bc8d" />

```
data.fillna(method="ffill")
```
OUTPUT:

<img width="1065" height="884" alt="image" src="https://github.com/user-attachments/assets/bec9fb85-c09b-45eb-b346-d16f87bedfb2" />

```
data.bfill()
```
OUTPUT:

<img width="1025" height="840" alt="image" src="https://github.com/user-attachments/assets/35027a6f-bc8d-4b39-bc9b-f256ab770e9d" />

```
data.fillna({'REGNO':0, 'NAME':'PRAVEEN'})
```

OUTPUT:

<img width="996" height="837" alt="image" src="https://github.com/user-attachments/assets/f90f0c5e-04aa-488a-a0ad-44310320e029" />

```
ir=pd.read_csv("/content/iris.csv")
ir
```
OUTPUT:

<img width="740" height="603" alt="image" src="https://github.com/user-attachments/assets/5cf93507-5435-44ef-9b94-057761207bb4" />

```
ir.describe()
```

OUTPUT:

<img width="632" height="391" alt="image" src="https://github.com/user-attachments/assets/080e6598-a156-4245-9cd8-2533659c8688" />

```
import seaborn as sns
sns.boxplot(x="sepal_width",data=ir)
```
OUTPUT:

<img width="673" height="584" alt="image" src="https://github.com/user-attachments/assets/be897996-6b57-4703-b767-28af86ded3f1" />

```
q1=ir.sepal_width.quantile(0.25)
q3=ir.sepal_width.quantile(0.75)
iqr=q3-q1
print(iqr)
```
OUTPUT:

<img width="383" height="147" alt="image" src="https://github.com/user-attachments/assets/5c266e5a-e011-4cef-aee1-ddab039e9b4a" />

```
rid=ir[((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']
```

OUTPUT:

<img width="666" height="325" alt="image" src="https://github.com/user-attachments/assets/e48ed735-6550-44a6-820b-a21e15782a21" />

```
rid=ir[~((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid
```
OUTPUT:

<img width="705" height="550" alt="image" src="https://github.com/user-attachments/assets/61cec941-bcba-4605-849b-795407a0931d" />

```
rid=ir[((ir.sepal_width>(q1-1.5*iqr))&(ir.sepal_width<(q3+1.5*iqr)))]
rid['sepal_width']
```
OUTPUT:

<img width="675" height="608" alt="image" src="https://github.com/user-attachments/assets/a9545f27-6fa3-475a-869d-8928eb37ec7f" />

```
import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(ir.sepal_width))
z
```
OUTPUT:

<img width="651" height="728" alt="image" src="https://github.com/user-attachments/assets/8f14aa3e-8880-4f5e-8d81-c46398e386d5" />




# Result:
Thus the programs are executed successfully.

