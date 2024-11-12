Practice Questions: 4            (Data selection anad filtering [Pandas])



1. Select only the `Name` and `Age` columns from the DataFrame. 

2. Filter the DataFrame to show only rows where `Age` is greater than 30. 

3. Sort the DataFrame based on `Salary` in descending order. 

4. Select the 5th row using `.loc[]` and display the 3rd to 7th rows using `.iloc[]`. 




```python
import pandas as pd

# Create a sample DataFrame
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eve', 'Frank', 'Grace', 'Heidi'],
    'Age': [24, 35, 45, 29, 50, 28, 33, 41],
    'Salary': [50000, 54000, 58000, 52000, 63000, 45000, 52000, 60000]
}
df = pd.DataFrame(data)

# 1. Select only the `Name` and `Age` columns from the DataFrame
name_age_df = df[['Name', 'Age']]
print("1. Name and Age columns:\n", name_age_df, "\n")

# 2. Filter the DataFrame to show only rows where `Age` is greater than 30
age_above_30_df = df[df['Age'] > 30]
print("2. Rows where Age is greater than 30:\n", age_above_30_df, "\n")

# 3. Sort the DataFrame based on `Salary` in descending order
sorted_by_salary_df = df.sort_values(by='Salary', ascending=False)
print("3. Sorted by Salary in descending order:\n", sorted_by_salary_df, "\n")

# 4. Select the 5th row using `.loc[]` and display the 3rd to 7th rows using `.iloc[]`
fifth_row = df.loc[5]        # Select the 5th row by index
rows_3_to_7 = df.iloc[3:7]   # Select rows from the 3rd to the 7th by position
print("4. 5th row using .loc[]:\n", fifth_row, "\n")
print("4. Rows from 3rd to 7th using .iloc[]:\n", rows_3_to_7)

```

    1. Name and Age columns:
           Name  Age
    0    Alice   24
    1      Bob   35
    2  Charlie   45
    3    David   29
    4      Eve   50
    5    Frank   28
    6    Grace   33
    7    Heidi   41 
    
    2. Rows where Age is greater than 30:
           Name  Age  Salary
    1      Bob   35   54000
    2  Charlie   45   58000
    4      Eve   50   63000
    6    Grace   33   52000
    7    Heidi   41   60000 
    
    3. Sorted by Salary in descending order:
           Name  Age  Salary
    4      Eve   50   63000
    7    Heidi   41   60000
    2  Charlie   45   58000
    1      Bob   35   54000
    3    David   29   52000
    6    Grace   33   52000
    0    Alice   24   50000
    5    Frank   28   45000 
    
    4. 5th row using .loc[]:
     Name      Frank
    Age          28
    Salary    45000
    Name: 5, dtype: object 
    
    4. Rows from 3rd to 7th using .iloc[]:
         Name  Age  Salary
    3  David   29   52000
    4    Eve   50   63000
    5  Frank   28   45000
    6  Grace   33   52000
    


```python

```
