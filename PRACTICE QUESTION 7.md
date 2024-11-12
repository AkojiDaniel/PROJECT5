Practice Questions: 7         (Data Transformation And Aggregation [Pandaas]).





1. Group the data by `Gender` and calculate the mean `Salary` for each group. 

2. Find the mean and maximum `Salary` and the minimum and maximum `Age` using `agg()`. 

3. Increase all `Age` values by 1 using `apply()`. 

4. Create a pivot table showing average `Salary` for each `Department` and `Gender`. 



```python
import pandas as pd

# Sample DataFrame with an additional `Department` column
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eve', 'Frank', 'Grace', 'Heidi'],
    'Age': [24, 35, 45, 29, 50, 28, 33, 41],
    'Salary': [50000, 54000, 58000, 52000, 63000, 45000, 52000, 60000],
    'Gender': ['Female', 'Male', 'Male', 'Male', 'Female', 'Male', 'Female', 'Female'],
    'Department': ['HR', 'Engineering', 'Marketing', 'Engineering', 'HR', 'Marketing', 'HR', 'Engineering']
}
df = pd.DataFrame(data)

# 1. Group the data by `Gender` and calculate the mean `Salary` for each group
mean_salary_by_gender = df.groupby('Gender')['Salary'].mean()
print("1. Mean Salary by Gender:\n", mean_salary_by_gender, "\n")

# 2. Find the mean and maximum `Salary`, and the minimum and maximum `Age` using `agg()`
salary_age_stats = df.agg({
    'Salary': ['mean', 'max'],
    'Age': ['min', 'max']
})
print("2. Mean and Max Salary, Min and Max Age:\n", salary_age_stats, "\n")

# 3. Increase all `Age` values by 1 using `apply()`
df['Age'] = df['Age'].apply(lambda x: x + 1)
print("3. DataFrame with Age increased by 1:\n", df[['Name', 'Age']], "\n")

# 4. Create a pivot table showing average `Salary` for each `Department` and `Gender`
pivot_table = df.pivot_table(values='Salary', index='Department', columns='Gender', aggfunc='mean')
print("4. Pivot Table (Average Salary by Department and Gender):\n", pivot_table)

```

    1. Mean Salary by Gender:
     Gender
    Female    56250.0
    Male      52250.0
    Name: Salary, dtype: float64 
    
    2. Mean and Max Salary, Min and Max Age:
            Salary   Age
    mean  54250.0   NaN
    max   63000.0  50.0
    min       NaN  24.0 
    
    3. DataFrame with Age increased by 1:
           Name  Age
    0    Alice   25
    1      Bob   36
    2  Charlie   46
    3    David   30
    4      Eve   51
    5    Frank   29
    6    Grace   34
    7    Heidi   42 
    
    4. Pivot Table (Average Salary by Department and Gender):
     Gender        Female     Male
    Department                   
    Engineering  60000.0  53000.0
    HR           55000.0      NaN
    Marketing        NaN  51500.0
    

Explanation

1. Mean Salary by Gender: Groups the data by Gender and calculates the average Salary for each group.


2. Mean and Max Salary, Min and Max Age: Uses agg() to apply multiple aggregations on Salary (mean and max) and Age (min and max).


3. Increase All Age Values by 1: Uses apply() with a lambda function to increment every Age value by 1.


4. Pivot Table (Average Salary by Department and Gender): Creates a pivot table to display the average Salary for each combination of Department and Gender.

