# Python:

```python
# Function to find the partition position
def partition(array, left, right):
	# Choose the rightmost element as pivot
	pivot = array[right]

	# Pointer for greater element
	i = left - 1

	# Traverse through all elements
	# compare each element with pivot
	for j in range(left, right):
		if array[j] <= pivot:
			# If element smaller than pivot is found
			# swap it with the greater element pointed by i
			i = i + 1

			# Swapping element at i with element at j
			array[i], array[j] = array[j], array[i]

	# Swap the pivot element with
	# the greater element specified by i
	array[i + 1], array[right] = array[right], array[i + 1]

	# Return the position from where partition is done
	return i + 1


# Function to perform quicksort
def quicksort(array, left, right):
	if left < right:
		# Find pivot element such that
		# element smaller than pivot are on the left
		# element greater than pivot are on the right
		pi = partition(array, left, right)

		# Recursive call on the left of pivot
		quicksort(array, left, pi - 1)

		# Recursive call on the right of pivot
		quicksort(array, pi + 1, right)


# Driver code
if __name__ == '__main__':
	array = [10, 7, 8, 9, 1, 5]
	N = len(array)

	# Function call
	quicksort(array, 0, N - 1)
	print('Sorted array:')

	for x in array:
		print(x, end=" ")
```
