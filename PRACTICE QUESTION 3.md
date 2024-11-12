Practice Questions: 3              (Data Loading [Pandas]).

1. Remove all rows with missing values from the DataFrame
2. Fill missing values in the 'Age' column with the mean of that column
3. Drop the column 'Age' from the dataset
4. Rename the column 'Salary' to 'Income'

   ANSWER


```python
import pandas as pd

# Sample dataset
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eva'],
    'Age': [25, 30, 35, 40, None],
    'Salary': [50000, 60000, 70000, None, 90000],
    'Department': ['HR', 'IT', 'Finance', 'IT', 'HR']
}

# Loading the dataset into a pandas DataFrame
df = pd.DataFrame(data)

# 1. Remove all rows with missing values from the DataFrame
df_no_na = df.dropna()
print("DataFrame with rows containing missing values removed:")
print(df_no_na)

# 2. Fill missing values in the 'Age' column with the mean of that column
df_filled_age = df.copy()
df_filled_age['Age'].fillna(df['Age'].mean(), inplace=True)
print("\nDataFrame with missing values in 'Age' filled with the mean:")
print(df_filled_age)

# 3. Drop the column 'Age' from the dataset
df_no_age = df.drop('Age', axis=1)
print("\nDataFrame with 'Age' column dropped:")
print(df_no_age)

# 4. Rename the column 'Salary' to 'Income'
df_renamed_salary = df.rename(columns={'Salary': 'Income'})
print("\nDataFrame with 'Salary' column renamed to 'Income':")
print(df_renamed_salary)

```

    DataFrame with rows containing missing values removed:
          Name   Age   Salary Department
    0    Alice  25.0  50000.0         HR
    1      Bob  30.0  60000.0         IT
    2  Charlie  35.0  70000.0    Finance
    
    DataFrame with missing values in 'Age' filled with the mean:
          Name   Age   Salary Department
    0    Alice  25.0  50000.0         HR
    1      Bob  30.0  60000.0         IT
    2  Charlie  35.0  70000.0    Finance
    3    David  40.0      NaN         IT
    4      Eva  32.5  90000.0         HR
    
    DataFrame with 'Age' column dropped:
          Name   Salary Department
    0    Alice  50000.0         HR
    1      Bob  60000.0         IT
    2  Charlie  70000.0    Finance
    3    David      NaN         IT
    4      Eva  90000.0         HR
    
    DataFrame with 'Salary' column renamed to 'Income':
          Name   Age   Income Department
    0    Alice  25.0  50000.0         HR
    1      Bob  30.0  60000.0         IT
    2  Charlie  35.0  70000.0    Finance
    3    David  40.0      NaN         IT
    4      Eva   NaN  90000.0         HR
    

    C:\Users\hp\AppData\Local\Temp\ipykernel_10752\1251015304.py:21: FutureWarning: A value is trying to be set on a copy of a DataFrame or Series through chained assignment using an inplace method.
    The behavior will change in pandas 3.0. This inplace method will never work because the intermediate object on which we are setting values always behaves as a copy.
    
    For example, when doing 'df[col].method(value, inplace=True)', try using 'df.method({col: value}, inplace=True)' or df[col] = df[col].method(value) instead, to perform the operation inplace on the original object.
    
    
      df_filled_age['Age'].fillna(df['Age'].mean(), inplace=True)
    


```python

```
