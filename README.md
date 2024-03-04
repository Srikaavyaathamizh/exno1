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
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![Screenshot 2024-03-04 104658](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/2f8bfa9d-fd49-40aa-ab8c-d16ed6624019)

```
df.head()
```
![Screenshot 2024-03-04 102046](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/72981ba0-5e30-40e2-926c-61618f12c793)
```
df.tail()
```
![Screenshot 2024-03-04 102216](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/69b6acec-1208-4bd9-9a57-d4d590458200)

```
df.info()
```

![Screenshot 2024-03-04 102345](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/1c95c9cc-c202-4c99-bb01-5930abe7252f)
```
df.describe()
```

![WhatsApp Image 2024-03-04 at 10 53 18_1be13ee0](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/96730e51-b915-4a40-8144-e3c20f69c698)

```
df.shape
```

![Screenshot 2024-03-04 102726](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/f25d6210-e458-4917-9b59-a024f13da4dd)
```
df.isnull().sum()
```
![Screenshot 2024-03-04 102812](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/0cc80477-122e-40c1-b31d-ac213e34c108)

```
df.nunique()
```

![Screenshot 2024-03-04 102916](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/a6137126-38dd-4e20-b113-ca2148a492de)
```
df['GENDER'].value_counts()
```

![Screenshot 2024-03-04 103010](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/6ccb54b1-41c6-4239-a41b-2c03338cca26)

```
mn=df.TOTAL.mean()
mn
```

![Screenshot 2024-03-04 103143](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/84472749-3143-4c24-b33f-30e46f58788f)
```
df.TOTAL.fillna(mn,inplace=True)
df
```

![Screenshot 2024-03-04 103552](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/f6f78d3b-f410-45dc-ac14-8ac483e02f05)
```
x=df.M4.min()
x
```

![Screenshot 2024-03-04 103646](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/c8cfc9b2-1e43-43d2-8b54-d0ad14cc700a)

```
df.M4.fillna(x,inplace=True)
df
```

![Screenshot 2024-03-04 103815](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/a033715d-9856-4fde-a698-7036947284b1)
```
df.duplicated()
```

![Screenshot 2024-03-04 103904](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/0528f877-563e-4eed-a7b5-59300279c996)

```
df.drop_duplicates(inplace=True)
df
```

![Screenshot 2024-03-04 103954](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/c8f66e55-a94b-41cf-96c6-558f0fef0865)
```
df['DOB']
```

![Screenshot 2024-03-04 104036](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/721d26d2-3825-4efe-89aa-9ded79ca615a)
```
r=pd.to_datetime(df['DOB'])
r
```

![Screenshot 2024-03-04 104216](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/a8f145b3-8442-44fa-b726-8457ec4cf9f3)
```
df['DOB']=pd.to_datetime(df['DOB'])
df
```

![Screenshot 2024-03-04 104319](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/f9e3f2ee-71d5-4bd0-aebc-156f8813501e)
```
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```

![Screenshot 2024-03-04 104431](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/4982b6b6-7685-4f57-9979-4767b64e9fd7)
```
df.dropna(inplace=True)
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```

![Screenshot 2024-03-04 104547](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/c994cf3b-73c2-47c6-8b47-f933257a415d)
```
df.shape
```

![Screenshot 2024-03-04 104628](https://github.com/Srikaavyaathamizh/exno1/assets/144870938/a76e2462-97d5-4ba1-b3b7-11dbb66c1ce0)


# Result
          The data clearning has beeen done successfully.
