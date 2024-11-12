Practice Questions: 5            (Statistical Operation [Pandas and Numpy])



1. Calculate the mean, median, and standard deviation of the `Income` column. 
2. Display the correlation matrix for all numeric columns in the dataset. 
                                 
 ANSWER


```python
import pandas as pd

# Sample DataFrame with an `Income` column
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eve', 'Frank', 'Grace', 'Heidi'],
    'Age': [24, 35, 45, 29, 50, 28, 33, 41],
    'Salary': [50000, 54000, 58000, 52000, 63000, 45000, 52000, 60000],
    'Income': [48000, 53000, 59000, 51000, 64000, 46000, 50000, 61000]
}
df = pd.DataFrame(data)

# 1. Calculate the mean, median, and standard deviation of the `Income` column
income_mean = df['Income'].mean()
income_median = df['Income'].median()
income_std_dev = df['Income'].std()
print("1. Income Statistics:")
print(f"Mean: {income_mean}")
print(f"Median: {income_median}")
print(f"Standard Deviation: {income_std_dev}\n")

```

    1. Income Statistics:
    Mean: 54000.0
    Median: 52000.0
    Standard Deviation: 6546.536707079771
    
    


```python
import pandas as pd

# Sample DataFrame with an `Income` column
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eve', 'Frank', 'Grace', 'Heidi'],
    'Age': [24, 35, 45, 29, 50, 28, 33, 41],
    'Salary': [50000, 54000, 58000, 52000, 63000, 45000, 52000, 60000],
    'Income': [48000, 53000, 59000, 51000, 64000, 46000, 50000, 61000]
}
df = pd.DataFrame(data)


# 2. Display the correlation matrix for all numeric columns
correlation_matrix = df.corr()
print("2. Correlation Matrix:")
print(correlation_matrix)

```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[5], line 14
         10 df = pd.DataFrame(data)
         13 # 2. Display the correlation matrix for all numeric columns
    ---> 14 correlation_matrix = df.corr()
         15 print("2. Correlation Matrix:")
         16 print(correlation_matrix)
    

    File ~\anaconda2\Lib\site-packages\pandas\core\frame.py:11049, in DataFrame.corr(self, method, min_periods, numeric_only)
      11047 cols = data.columns
      11048 idx = cols.copy()
    > 11049 mat = data.to_numpy(dtype=float, na_value=np.nan, copy=False)
      11051 if method == "pearson":
      11052     correl = libalgos.nancorr(mat, minp=min_periods)
    

    File ~\anaconda2\Lib\site-packages\pandas\core\frame.py:1993, in DataFrame.to_numpy(self, dtype, copy, na_value)
       1991 if dtype is not None:
       1992     dtype = np.dtype(dtype)
    -> 1993 result = self._mgr.as_array(dtype=dtype, copy=copy, na_value=na_value)
       1994 if result.dtype is not dtype:
       1995     result = np.asarray(result, dtype=dtype)
    

    File ~\anaconda2\Lib\site-packages\pandas\core\internals\managers.py:1694, in BlockManager.as_array(self, dtype, copy, na_value)
       1692         arr.flags.writeable = False
       1693 else:
    -> 1694     arr = self._interleave(dtype=dtype, na_value=na_value)
       1695     # The underlying data was copied within _interleave, so no need
       1696     # to further copy if copy=True or setting na_value
       1698 if na_value is lib.no_default:
    

    File ~\anaconda2\Lib\site-packages\pandas\core\internals\managers.py:1753, in BlockManager._interleave(self, dtype, na_value)
       1751     else:
       1752         arr = blk.get_values(dtype)
    -> 1753     result[rl.indexer] = arr
       1754     itemmask[rl.indexer] = 1
       1756 if not itemmask.all():
    

    ValueError: could not convert string to float: 'Alice'



```python

```
