### Import the library
```bash
$ import pandas as pd
```
```bash
$ filename = "https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0101EN-SkillsNetwork/labs/Module%205/data/diabetes.csv"

$ async def download(url, filename):
    response = await pyfetch(url)
    if response.status == 200:
        with open(filename, "wb") as f:
            f.write(await response.bytes())

$ await download(filename, "diabetes.csv")
$ df = pd.read_csv("diabetes.csv")
```
#### After reading the dataset, we can use the dataframe.head(n) method to check the top n rows of the dataframe, where n is an integer. Contrary to dataframe.head(n), dataframe.tail(n) will show you the bottom n rows of the dataframe.
#### Show the first 5 rows using dataframe.head() method
```bash
$ print("The first 5 rows of the dataframe") 
$ df.head(5)
```
### To view the dimensions of the dataframe, we use the .shape parameter.
```bash
$ df.shape
```
# Statistical Overview of dataset
```bash
$ df.info()
```
#### This method prints information about a DataFrame including the index dtype and columns, non-null values and memory usage.
```bash
$df.describe()
```
### Identify and handle missing values
```bash
$ missing_data = df.isnull()
missing_data.head()
```
### Count missing values in each column
```bash
$for column in missing_data.columns.values.tolist():
    print(column)
    print (missing_data[column].value_counts())
    print("")  
```
### Correct data format
```bash
$ df.dtypes
```
# Visualization
### Seaborn and Matplotlib are two of Python's most powerful visualization libraries
#### Import libraries
```bash
$ import matplotlib.pyplot as plt
import seaborn as sns
```
```bash
$ labels= 'Diabetic','Not Diabetic'
plt.pie(df['Outcome'].value_counts(),labels=labels,autopct='%0.02f%%')
plt.legend()
plt.show()
```














