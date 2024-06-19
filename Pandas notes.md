
Sure, here are some crisp Pandas notes for a data science interview:

### Pandas Basics

- **Importing Pandas**:
  ```python
  import pandas as pd
  ```

- **Data Structures**:
  - **Series**: One-dimensional labeled array.
    ```python
    s = pd.Series([1, 3, 5, 7])
    ```
  - **DataFrame**: Two-dimensional labeled data structure.
    ```python
    df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]})
    ```

### DataFrame Creation

- **From Dictionary**:
  ```python
  data = {'col1': [1, 2], 'col2': [3, 4]}
  df = pd.DataFrame(data)
  ```

- **From CSV**:
  ```python
  df = pd.read_csv('file.csv')
  ```

### Data Inspection

- **Top Rows**:
  ```python
  df.head()  # Default is 5 rows
  ```

- **Bottom Rows**:
  ```python
  df.tail()
  ```

- **Info & Summary**:
  ```python
  df.info()
  df.describe()
  ```

### Selection & Filtering

- **Select Columns**:
  ```python
  df['column_name']
  ```

- **Select Rows by Index**:
  ```python
  df.iloc[0]  # First row
  df.loc[0]   # First row (if index is 0)
  ```

- **Conditional Filtering**:
  ```python
  df[df['column_name'] > value]
  ```

### Modifying DataFrames

- **Add Column**:
  ```python
  df['new_column'] = value
  ```

- **Drop Column**:
  ```python
  df.drop('column_name', axis=1, inplace=True)
  ```

- **Rename Columns**:
  ```python
  df.rename(columns={'old_name': 'new_name'}, inplace=True)
  ```

### Handling Missing Data

- **Check for Nulls**:
  ```python
  df.isnull()
  df.isnull().sum()
  ```

- **Drop Missing Values**:
  ```python
  df.dropna()
  ```

- **Fill Missing Values**:
  ```python
  df.fillna(value)
  ```

### Grouping and Aggregation

- **Group By**:
  ```python
  df.groupby('column_name').mean()
  ```

- **Aggregate Functions**:
  ```python
  df.agg({'column1': 'sum', 'column2': 'mean'})
  ```

### Merging and Joining

- **Concatenate**:
  ```python
  pd.concat([df1, df2])
  ```

- **Merge**:
  ```python
  pd.merge(df1, df2, on='common_column')
  ```

### Working with Dates

- **Convert to Datetime**:
  ```python
  df['date_column'] = pd.to_datetime(df['date_column'])
  ```

- **Extract Date Parts**:
  ```python
  df['year'] = df['date_column'].dt.year
  df['month'] = df['date_column'].dt.month
  ```

### Useful Functions

- **Apply**:
  ```python
  df['new_column'] = df['column'].apply(func)
  ```

- **Map**:
  ```python
  df['mapped_column'] = df['column'].map({old_val: new_val})
  ```

- **Sort Values**:
  ```python
  df.sort_values(by='column_name')
  ```

### Exporting Data

- **To CSV**:
  ```python
  df.to_csv('output.csv', index=False)
  ```

### Best Practices

- **Chaining**:
  ```python
  df = (df.dropna()
          .rename(columns={'old': 'new'})
          .sort_values(by='column'))
  ```

- **Vectorization**: Prefer vectorized operations over loops for efficiency.

These notes cover essential Pandas operations that are commonly used in data science tasks and interviews.
