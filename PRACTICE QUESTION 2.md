Practice Questions: 2           (Data loading and exploration[Pandas])



1. Load the dataset `data.csv` into a pandas DataFrame and display the first 5 rows.
2. Show the summary statistics (mean, standard deviation, etc.) of the dataset


```python
import pandas as pd

# Sample dataset to simulate 'data.csv'
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eva'],
    'Age': [25, 30, 35, 40, None],
    'Salary': [50000, 60000, 70000, None, 90000],
    'Department': ['HR', 'IT', 'Finance', 'IT', 'HR']
}

# Loading the dataset into a pandas DataFrame
df = pd.DataFrame(data)

# 1. Display the first 5 rows of the dataset
print("First 5 rows of the dataset:")
print(df.head())

# 2. Display summary statistics
print("\nSummary statistics of the dataset:")
print(df.describe())

# 3. Check for missing values
print("\nMissing values in the dataset:")
print(df.isnull().sum())
```

    First 5 rows of the dataset:
          Name   Age   Salary Department
    0    Alice  25.0  50000.0         HR
    1      Bob  30.0  60000.0         IT
    2  Charlie  35.0  70000.0    Finance
    3    David  40.0      NaN         IT
    4      Eva   NaN  90000.0         HR
    
    Summary statistics of the dataset:
                 Age        Salary
    count   4.000000      4.000000
    mean   32.500000  67500.000000
    std     6.454972  17078.251277
    min    25.000000  50000.000000
    25%    28.750000  57500.000000
    50%    32.500000  65000.000000
    75%    36.250000  75000.000000
    max    40.000000  90000.000000
    
    Missing values in the dataset:
    Name          0
    Age           1
    Salary        1
    Department    0
    dtype: int64
    


```python

```
