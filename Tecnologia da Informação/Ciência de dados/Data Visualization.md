# Data Visualization

## Matplotlib

### Import
```python
import matplotlib # whole library
import matplotlib.pyplot as plt
```

### Add chart title
```python
plt.title('some title')
```

### Add legend
```python
plt.legend(['legend1', 'legend2', ...])
```

### Labels
```python
plt.plot(<series_labels>, <series_data>)
plt.xlabel('X axis description')
plt.ylabel('Y axis description')
plt.xticks(rotation=75) # rotates x labels in degrees
```

### Styling
```python
# color, linestyle or ls, linewidth or lw, markersize or ms, markeredgecolor or mec, alpha, etc.
plt.plot(<series_labels>, <series_data>, marker='s', c='b', ls='--', lw=2, ms=8, mew=2, mec='red', alpha=0.5)

# Format parameter shorthand
plt.plot(<series_labels>, <series_data>, fmt='o--r') # or fmt='s-b'

# Change graph size in inches
plt.figure(figsize=(6.4, 4.8))

# Edit default style
matplotlib.rcParams['font.size'] = 14
matplotlib.rcParams['figure.figsize'] = (9, 5)
matplotlib.rcParams['figure.facecolor'] = '#00000000'
# and many more parameters
```

### Types of charts

#### Line
```python
plt.plot(<series>) # or (<series_labels>, <series_data>)
# Multiple lines: just invoke plt.plot() multiple times
# Line markers
plt.plot(<series_labels>, <series_data>, marker='o') # or marker='x', check documentation for more options
```

#### Histogram
```python
plt.hist(data_frame.<column>, bins=5) # bins are optional
plt.hist(data_frame.<column>, bins=np.arange(2, 5, 0.25)) # boundaries of each bin
plt.hist(data_frame.<column>, bins=[1, 3, 4, 4.5]) # bins of different size
# Multiple histograms
# Just invoke plt.hist() multiple times or pass a list of columns
# Stacked histogram: add the parameter -> stacked=True
```

#### Bar
```python
plt.bar(<series_labels>, <series_data>)
# With a line chart
plt.plot(<series>, 'o--r') # a red dotted line
# Multiple bars: just invoke plt.bar() multiple times with one plot with the parameter bottom=<series>
```

#### Pie
```python
plt.pie(<series>, labels=<series>, autopct='%1.1f%%') # autopct formats the displayed percentage of each value
```

### Chart grid
```python
plt.tight_layout(pad=2) # add padding between grid charts
fig, axes = plt.subplots(x, y)
axes[0, 0].plot(<arguments>) # insert plot to first grid chart slot
axes[0, 1].set_title('Seaborn chart in grid')
sns.scatterplot(<arguments>) # and so on to fill other grid slots
```

## Seaborn

- Build on top of Matplotlib and has more graph types
- Improve Matplotlib default styles

### Import
```python
import seaborn as sns
```

### Set style
```python
sns.set_style('whitegrid') # or darkgrid, etc.
```

### Load Seaborn sample datasets
```python
sns.load_dataset('iris') # flowers example dataset, or tips dataset
```

### Types of charts

#### Scatter plot
```python
sns.scatterplot(data_frame.<column_name1>, data_frame.<column_name2>, hue=data_frame.<column_name3>, s=100) # s = size of point
sns.scatterplot(data=data_frame, '<column_name1>', '<column_name2>', hue='<column_name3>', s=100) # passing the DataFrame as argument
```

#### Bar
```python
# Automatic mean bar plot with candle
sns.barplot('<column_name_labels>', 'column_name_values', hue='<column_name>' data=data_frame)
# Make it horizontal switching the axes column names
```

#### Heatmap
```python
sns.heatmap(pivot_df, annot=True, cmap='Blues') # annot displays the values numbers and cmap is the color theme
```

#### Count plot
```python
sns.countplot(y=data_frame.<column_name>) # horizontal bar chart with total count
```

#### Distribution plot
```python
sns.distplot(series)
```

## Image processing with Pillow

### Import
```python
from PIL import Image
```

### Show image
```python
img = Image.open(<image_path>)
plt.grid(False)
plt.axis('off')
plt.imshow(img)
img_array = np.array(img) # convert to Numpy array
plt.imshow(img_array[125:325, 105:305]) # display part of the image
```