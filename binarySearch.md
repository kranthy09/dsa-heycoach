# Mastering Binary Search with Real-World Examples

Binary Search is one of the most fundamental algorithms in computer science, often appearing in coding interviews and competitive programming. Beyond the classic "find an element in a sorted array," binary search can solve a variety of complex problems efficiently.

In this blog, we'll go beyond basics with **two practical applications**:

1. **Finding the smallest number strictly greater than a given number K in a sorted array**
2. **Finding the peak element in an array**

---

## 🚀 What is Binary Search?

Binary search is an efficient algorithm to find an element in a **sorted** array with a time complexity of **O(log n)**. It repeatedly divides the search space in half until the target is found (or not found).

### Alogirithm

To find an element in an array we have to define the search space where the target is located.

1. Search Space: Part of the array where the element is found
2. Update the search space by comparing the mid element with the target element
3. Size of the new search space will be approx. half of the previous search space

```python
# An array of size n, with a 'target' element to be found
l=0, r=n-1 # initial search space (complete array)
while l<=r:
 mid = l + (r-l)//2
 if arr[mid] == target:
  return mid
 elif arr[mid] > target:
  move the search space to left
 else:
  move the search space to right
```

Initially define the search space with 'l', 'r', and 'mid' for comparing with the target.

---

**Note**: mid is updated with `mid = l + (r-l)/2)` instead with `mid = (l+r)/2`. Hence the l, r can be integers of maximum value 2^31^-1. `l+r` will execeed 2^31^. An overflow condition occurs when the result of an arithmetic operation exceeds the maximum value that a given data type can represent, leading to an incorrect or unexpected result.

---

Middle element of the array is compared with the target in each iteration.
There can three cases following:

1. Mid element is the target
2. Mid element is greater than the target
3. Mid element is less than the target

**Case 1:** `arr[mid] == target`
Return the index of the middle element, as the target is found.

**Case 2:** `arr[mid] > target`
Mid element is greater than the target. As the array is sorted,the left part of the array can be ignored . so the search space will be moved to right by updating `l, r`.

- `l` becomes `mid+1` and `r` remains same.

**Case 3:** `arr[mid] < target`
Mid element is less than the target. As the array is sorted, the right part of the array can be ignored. so the search space will be moved to left by updating `l, r`.

- `r` becomes `mid-1` and `l` remains same.

### :nut_and_bolt: Full Code ~python

```python
arr = [1, 2, 5, 7, 9 , 11, 24, 28]
target = 11
l = 0,
r = len(arr) - 1
def binary_search(arr):
	while l <= r:
		mid = l + (r - l)/
		if arr[mid] == target:
			return mid
		elif arr[mid] > target:
			r = mid - 1
		else:
			l = mid + 1
	return -1 # no target found
print(binary_search(arr, target))
# index of target: 5
```

---

## 📌 Problem 1: Find the Smallest Number Strictly Greater than K

### Problem

Given a **sorted array**, find the smallest number that is **strictly greater** than a given number `K`. If no such number exists, return `-1`.

### Example

```text
Input: nums = [2, 4, 6, 8, 10], K = 6
Output: 8
```
