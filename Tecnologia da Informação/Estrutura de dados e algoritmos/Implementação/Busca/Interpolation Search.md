# Python:

```python
# If x is present in arr[0..n-1], then
# returns index of it, else returns -1.
def interpolationSearch(arr, low, high, x):
	# Since array is sorted, an element present
	# in array must be in range defined by corner
	if (low <= high and x >= arr[low] and x <= arr[high]):
		# Probing the position with keeping
		# uniform distribution in mind.
		pos = low + ((high - low) // (arr[high] - arr[low]) *
					(x - arr[low])) # // -> floor division

		# Condition of target found
		if arr[pos] == x:
			return pos

		# If x is larger, x is in right subarray
		if arr[pos] < x:
			return interpolationSearch(arr, pos + 1, high, x)

		# If x is smaller, x is in left subarray
		if arr[pos] > x:
			return interpolationSearch(arr, low, pos - 1, x)
	return -1

# Driver code
# Array of items in which
# search will be conducted
arr = [10, 12, 13, 16, 18, 19, 20, 21, 22, 23, 24, 33, 35, 42, 47]
n = len(arr)

# Element to be searched
x = 18
index = interpolationSearch(arr, 0, n - 1, x)

if index != -1:
	print("Element found at index", index)
else:
	print("Element not found")
```
