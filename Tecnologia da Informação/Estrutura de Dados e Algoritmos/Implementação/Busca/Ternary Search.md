# Python:

```python
# recursive approach to ternary search
import math as mt

# Function to perform Ternary Search
def ternarySearch(left, right, x, arr):

	if (right >= left):

		# Find the mid1 and mid2
		mid1 = left + (right - left) // 3 # ternary floor division
		mid2 = right - (right - left) // 3

		# Check if x is present at any mid
		if (arr[mid1] == x):
			return mid1

		if (arr[mid2] == x):
			return mid2

		# Since x is not present at mid,
		# check in which region it is present
		# then repeat the Search operation
		# in that region
		if (x < arr[mid1]):
			# The x lies in between left and mid1
			return ternarySearch(left, mid1 - 1, x, arr)

		elif (x > arr[mid2]):
			# The x lies in between mid2 and right
			return ternarySearch(mid2 + 1, right, x, arr)

		else:
			# The x lies in between mid1 and mid2
			return ternarySearch(mid1 + 1, mid2 - 1, x, arr)

	# Key not found
	return -1

# Driver code
left, right, p = 0, 9, 5

# Get the array
# Sort the array if not sorted
arr = [ 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 ]

# Starting index
left = 0

# end element index
right = 9

# Checking for 5
# Key to be searched in the array
x = 5

# Search the x using ternarySearch
p = ternarySearch(left, right, x, arr)

# Print the result
print("Index of", x, "is", p)

# Checking for 50
# Key to be searched in the array
x = 50

# Search the x using ternarySearch
p = ternarySearch(left, right, x, arr)

# Print the result
print("Index of", x, "is", p)
```
