# Numpy

## Benefits

- Numpy arrays are easy to use and have better performance than native Python arrays.
- Numpy arrays can be multidimensional.
- Inspect array dimensions with:
    - `numpy_array.shape`
    - Output: `(first dimension or rows, second dimension or column, etc.)`

## Installation in Jupyter Notebook

```bash
!pip install numpy
```

## Import

```python
import numpy as np
```

## Array Operations

- Get array data type: `numpy_array.dtype`
- Get help: `help(np.function)`
- Basic mathematics: `np.sum`, `exp`, `round`, arithmetic operators
  - Adding a scalar: `array + number`
  - Element-wise subtraction: `array1 - array2`
  - Division by scalar: `array / number`
  - Element-wise multiplication: `array1 * array2`
  - Modulus with scalar: `array % number`

## Linear Algebra

- `np.matmul`, `dot`, `transpose`, `eigvals`
  - Calculate the dot product: `np.dot(first array, second array)`
  - Matrix multiplication: `np.matmul(first array, second array)` or `first array @ second array`
  - Identity matrix: `np.eye(3)`  # Number of rows in the output

## Statistics

- `np.mean`, `median`, `std`, `max`, `min`, `count`

## Array Manipulation

### Creating Arrays

- `np.array([a, b, c])`
- Random array: `np.random.rand(5)`  # uniform distribution
- Random matrix: `np.random.randn(2, 3)`  # Gaussian distribution
- Fixed value: `np.full([2, 3], 42)`
- Range with start, end, and step: `np.arange(10, 90, 3)`  # analog range
- Equally spaced numbers in a range: `np.linspace(3, 27, 9)`  # 9 is the number of elements

### Manipulation Functions

- `np.reshape` (turn a one-dimensional array to 2D, 3D, etc.), `stack`, `concatenate`, `split`
- Join arrays to add new columns:

  ```python
  np.concatenate((column to add, existing array.reshape(number of rows, number of columns to add)), axis=1)
  ```

### Indexing and Slicing

- Single element: `numpy_array[1, 1, 2]`
- Ranges: `numpy_array[1:, 0:1, :2]`

### Get Ones and Zeros Values, Null Matrix

- `np.zeros((3, 2))` and `np.ones([2, 2, 3])`  # argument can be a tuple or list

## Comparison Operations

It is supported. The result is an array of booleans.

## Working with Files

### Interact with the OS and Filesystem

```python
import os
```

- Get working directory: `os.getcwd()`
- List files in a directory: `os.listdir('relative "." or absolute path "/usr"')`
- Create directory: `os.makedirs('./new_directory_name', exist_ok=True)`

### Read File from Online Source

```python
import urllib.request
```

- Retrieve and save file: `urllib.request.urlretrieve(online CSV file URL, path and file name to save file)`

### TXT Files

- Generate data from TXT file: `np.genfromtxt(file_name.txt, delimiter=',', skip_header=1)`
- Save file: `np.savetxt(file_name, numpy_array, fmt='%.2f', header='column header 1, column header 2, etc.', comments='')`
- Open file: `file = open('./data/filename.txt', mode='r')`  # open for reading
- Read file contents: `file_contents = file.read()`
- Close the file: `file.close()`  # this file can no longer be read

### Reading Files Automatically

```python
with open('./data/filename.txt') as file:
    file_contents = file.read()
    print(file_contents)  # the close method is invoked automatically
```

### Read Line by Line

```python
with open('./data/filename.txt') as file:
    file_lines = file.readlines()  # return a list
```

### Utility Functions

```python
def parse_headers(header_line):
    return header_line.strip().split(',')

def parse_values(data_line):
    values = []
    for item in data_line.strip().split(','):
        if item == '':
            values.append(0.0)
        else:
            values.append(float(item))
    return values

def create_item_dict(headers, values):
    result = {}
    for value, header in zip(headers, values):
        result[header] = value
    return result

def read_csv(path):
    result = []
    with open(path, 'r') as f:
        lines = f.readlines()
        headers = parse_headers(lines[0])
        for data_line in lines[1:]:
            values = parse_values(data_line)
            item_dict = create_item_dict(headers, values)
            result.append(item_dict)
    return result
```