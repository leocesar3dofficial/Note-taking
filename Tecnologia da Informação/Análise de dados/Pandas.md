# Pandas

**Stands for:**
- Panel data
- Multidimensional structured datasets
- Python data analysis

**Import:**
```python
import pandas as pd
```

**Working with files:**

- **CSV:**
  - Sometimes the client will provide a file with the data schema (`<column_name>`, `<column_description>`, `<column_type>`).
  - Read file: `my_data_frame_df = pd.read_csv('<file_path>')`
  - Write file: `my_data_frame_df.to_csv('<filename>', index=None)` # create a CSV file without the index column

- **JSON:**
  - Read file: `my_data_frame_df = pd.read_json('<file_path>')`

**Getting information from Data Frames:**

- Basic info: `data_frame.info()`
- Stats for numerical columns: `data_frame.describe()`
- List of columns: `data_frame.columns`
- Shape: `data_frame.shape`
- List column values:
  - `data_frame[<column_name>]` # single column
  - `data_frame[[<column_name1>, <column_name2>, ...]]` # multiple columns
  - `data_frame.<column_name>` # only works for column names without spaces or special characters
- Get one value:
  - `data_frame[<column_name>][<numeric_index_value>]`
  - `data_frame.at[<numeric_index_value>, <column_name>]`
- NaN values: value is not present in the source data file or is blank, it is not a number or zero
- Get first valid index number: `data_frame.<column_name>.first_valid_index()` # value != NaN
- Get interval: `data_frame.loc[<first_index>:<last_index>]`
- Get row: `data_frame.loc[index]`
- Random sample of rows: `data_frame.sample(number)`
- First rows: `data_frame.head(number_of_rows)`
- Last rows: `data_frame.tail(number_of_rows)`
- Get unique values: `data_frame.<column>.unique()`
- Get count for each value in column: `data_frame['<column_name>'].value_counts()` # count NaN passing argument `dropna=False`

**Copy DataFrame:**
```python
data_frame.copy()
```

**Set index column:**
```python
data_frame.set_index('<column_name>', inplace=True) # inplace = true doesn't create another DataFrame
```

**Create a subset aggregated DataFrame:**
```python
subset_df = data_frame[['<column_name1>', '<column_name2>', ...]]
def split_multicolumn(<column_series>):
    # Function details as provided
```

**Add new column to a DataFrame:**
```python
data_frame['<new_column_name>'] = series
data_frame['<new_column_name_per_million>'] = data_frame.<column> * 1e6
data_frame['<new_column_name>'] = data_frame.<column_name>.cumsum() # add a cumulative sum column
```

**Remove column from a DataFrame:**
```python
data_frame.drop(columns=['<column_name1>', '<column_name2>'], inplace=True)
```

**Create a Series from a Python list:**
```python
pd.Series(list_name)
```

**Pivot table:**
```python
pivot_df = data_frame.pivot('<column_name_y>', '<column_name_x>', '<column_name_values>')
# Display it with a heatmap in Seaborn:
# sns.heatmap(pivot_df)
```

**Cleaning:**

- Change column type:
```python
data_frame['<column_name>'] = pd.to_numeric(data_frame.<column>, errors='coerce') # coerce replaces string to NaN
```

- Assign new value (used to clean data):
```python
data_frame.at[<index>, '<column_name>'] = new_value
```

- Replace values based on condition:
```python
data_frame.where(<expression>, np.nan, inplace=True) # replaces values inplace with NaN if match condition
```

- Format date column:
```python
data_frame['<date_column>'] = pd.to_datetime(data_frame.<date_column>)
data_frame['year'] = pd.DatetimeIndex(data_frame.<date_column>).year
data_frame['month'] = pd.DatetimeIndex(data_frame.<date_column>).month
data_frame['day'] = pd.DatetimeIndex(data_frame.<date_column>).day
data_frame['weekday'] = pd.DatetimeIndex(data_frame.<date_column>).weekday # Monday = 0
```

**Querying:**
```python
subset_series = data_frame[data_frame.<column_name> > number] # expression with logic operators
totals_series = data_frame.sum() # returns the sum series of all numeric columns
data_frame = data_frame[data_frame.month == 5][['<column_name1>', '<column_name2>', ...]].sum() # or mean()
```

**Sorting:**
```python
sorted_df = data_frame.sort_values('<column_name>', ascending=False).head(10)
```

**Grouping:**
```python
grouped_df = data_frame.groupby('<column_name>')[list_of_columns].sum() # or mean(), max(), etc.
```

**Merging data from multiple sources:**
```python
merged_df = data_frame.merge(data_frame_to_add, on='<key_column>')
```

**Display output:**

- Display large number of rows with IPython:
```python
# Import:
from IPython.display import display

# Display data:
with pd.option_context('display.max_rows', <max_rows_number>):
    display(data_frame[<query>])
```

**Plotting:**

- Pandas can create basic graphs:
```python
data_frame.<column>.plot() # default line graph
# Optional arguments: title='title', kind='bar'
# If you call another plot function of another column in another line Pandas displays one graph with the two series
```