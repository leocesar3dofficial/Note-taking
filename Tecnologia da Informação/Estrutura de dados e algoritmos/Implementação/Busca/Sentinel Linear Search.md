# Python:

```python
# Function to search x in the given array
def sentinelSearch(arr, n, x):

	# Last element of the array
	last = arr[n - 1]

	# Element to be searched is
	# placed at the last index
	arr[n - 1] = x
	i = 0

	while (arr[i] != x):
		i += 1

	# Put the last element back
	arr[n - 1] = last

	if ((i < n - 1) or (arr[n - 1] == x)):
		print(x, "is present at index", i)
	else:
		print("Element Not found")

# Driver code
arr = [10, 20, 180, 30, 60, 50, 110, 100, 70]
n = len(arr)
x = 180

sentinelSearch(arr, n, x)
```
