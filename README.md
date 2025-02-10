# Search Algorithms

This repository contains documentation and explanations of four fundamental search algorithms: Linear Search, Binary Search, Jump Search, and Interpolation Search. These algorithms are used to find elements in an array efficiently based on different conditions and constraints.

---

## 1. Linear Search

**Definition:**
Linear Search is a simple search algorithm that sequentially checks each element of the list until a match is found or the whole list has been searched.

### **Algorithm:**
1. Start from the leftmost element.
2. Compare each element with the target element.
3. If a match is found, return the index.
4. If the element is not found, return -1.

### **Time Complexity:**
- Best Case: **O(1)** (Element found at the first position)
- Worst Case: **O(n)** (Element found at the last position or not present)
- Average Case: **O(n)**

### **Usage:**
- Works on both sorted and unsorted lists.
- Useful for small or unsorted datasets.

---

## 2. Binary Search

**Definition:**
Binary Search is an efficient algorithm for finding an element in a sorted list by repeatedly dividing the search interval in half.

### **Algorithm:**
1. Set `low` to the first index and `high` to the last index.
2. Compute the middle index: `mid = (low + high) / 2`.
3. If `arr[mid]` is equal to the target, return `mid`.
4. If `arr[mid]` is greater than the target, search in the left half (`high = mid - 1`).
5. If `arr[mid]` is less than the target, search in the right half (`low = mid + 1`).
6. Repeat until `low` exceeds `high` or the element is found.

### **Time Complexity:**
- Best Case: **O(1)** (Element found at the middle index)
- Worst Case: **O(log n)**
- Average Case: **O(log n)**

### **Usage:**
- Works only on sorted arrays.
- Commonly used in searching large datasets efficiently.

---

## 3. Jump Search

**Definition:**
Jump Search is a searching algorithm for sorted arrays that reduces the number of comparisons by jumping in fixed steps instead of searching sequentially.

### **Algorithm:**
1. Set `step = sqrt(n)`, where `n` is the length of the array.
2. Jump `step` indices ahead until the target is greater than or equal to the current element.
3. Perform a linear search in the block where the element may be present.
4. If found, return the index; otherwise, return -1.

### **Time Complexity:**
- Best Case: **O(1)**
- Worst Case: **O(sqrt(n))**
- Average Case: **O(sqrt(n))**

### **Usage:**
- Works on sorted arrays.
- Useful when binary search is not feasible due to expensive middle element access.

---

## 4. Interpolation Search

**Definition:**
Interpolation Search is an improvement over Binary Search that estimates the position of the target element using a formula based on the distribution of values.

### **Algorithm:**
1. Compute the probable position:
   ```
   pos = low + ((target - arr[low]) * (high - low)) / (arr[high] - arr[low])
   ```
2. If `arr[pos]` matches the target, return `pos`.
3. If `arr[pos]` is greater, search in the left subarray.
4. If `arr[pos]` is smaller, search in the right subarray.
5. Repeat until `low` exceeds `high` or the element is found.

### **Time Complexity:**
- Best Case: **O(1)**
- Worst Case: **O(n)** (When elements are not uniformly distributed)
- Average Case: **O(log log n)**

### **Usage:**
- Works best on uniformly distributed, sorted data.
- More efficient than Binary Search when the data is evenly spread.

---

## Conclusion
Each of these search algorithms has its own strengths and ideal use cases. The choice of algorithm depends on factors like dataset size, whether the data is sorted, and the efficiency required. Here’s a quick comparison:

| Algorithm            | Best Case | Worst Case  | Average Case | Sorted Data Required |
|----------------------|----------|-------------|--------------|----------------------|
| Linear Search       | O(1)     | O(n)        | O(n)         | No                   |
| Binary Search      | O(1)     | O(log n)    | O(log n)     | Yes                  |
| Jump Search        | O(1)     | O(sqrt(n))  | O(sqrt(n))   | Yes                  |
| Interpolation Search | O(1)     | O(n)        | O(log log n) | Yes                  |

These algorithms are essential in computer science and software development, helping to optimize search operations in various applications.

---