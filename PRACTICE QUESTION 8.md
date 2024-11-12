Practice Questions: 8           (Statistical Hypothesis Testing [scipy]).




1. Perform a t-test to check if there is a significant difference in `Salary` between `Male` and `Female`.

2. Conduct a chi-square test on the gender distribution.



```python
import pandas as pd
from scipy.stats import ttest_ind, chi2_contingency

# Sample DataFrame with `Salary` and `Gender` columns
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eve', 'Frank', 'Grace', 'Heidi'],
    'Age': [24, 35, 45, 29, 50, 28, 33, 41],
    'Salary': [50000, 54000, 58000, 52000, 63000, 45000, 52000, 60000],
    'Gender': ['Female', 'Male', 'Male', 'Male', 'Female', 'Male', 'Female', 'Female']
}
df = pd.DataFrame(data)

# 1. Perform a t-test to check if there is a significant difference in `Salary` between `Male` and `Female`
male_salary = df[df['Gender'] == 'Male']['Salary']
female_salary = df[df['Gender'] == 'Female']['Salary']
t_stat, p_value = ttest_ind(male_salary, female_salary, equal_var=False)  # Welch's t-test for unequal variances
print("1. T-test results:")
print(f"T-statistic: {t_stat}")
print(f"P-value: {p_value}\n")

# 2. Conduct a chi-square test on the gender distribution
gender_counts = df['Gender'].value_counts()
chi2_stat, chi2_p_value, _, _ = chi2_contingency([gender_counts])
print("2. Chi-square test results:")
print(f"Chi-square statistic: {chi2_stat}")
print(f"P-value: {chi2_p_value}")
```

    1. T-test results:
    T-statistic: -0.9665953493282832
    P-value: 0.37173689357982376
    
    2. Chi-square test results:
    Chi-square statistic: 0.0
    P-value: 1.0
    

Explanation Of Result

1. T-test (Salary Difference by Gender):

The ttest_ind() function performs an independent t-test on the Salary values of Male and Female.

We use equal_var=False to perform Welch's t-test, which is more reliable if the variances of the two groups are unequal.

The test produces a t-statistic and a p-value. A p-value less than 0.05 would typically indicate a significant difference in salaries between genders.



2. Chi-square Test (Gender Distribution):

chi2_contingency() performs a chi-square test for independence on the observed gender distribution.

The test outputs a chi-square statistic and a p-value. A p-value less than 0.05 suggests that the observed gender distribution significantly deviates from what would be expected if genders were evenly distributed.

