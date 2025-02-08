# Merge Sort Algorithm

## Introduction
Merge Sort is a **divide and conquer** sorting algorithm that splits an array into smaller subarrays, sorts them, and then merges them back together to form a sorted array.

## How Merge Sort Works
1. **Divide:** Split the array into two halves until each subarray contains a single element.
2. **Conquer:** Recursively sort each half.
3. **Merge:** Combine the sorted halves into a single sorted array.

## Time Complexity
| Case         | Time Complexity | Explanation |
|-------------|---------------|-------------|
| **Best Case**  | **O(n log n)**   | Always divides array and merges efficiently |
| **Average Case**  | **O(n log n)** | Consistently divides and merges elements |
| **Worst Case**  | **O(n log n)** | Recursively splits and merges in every case |

## Space Complexity
- **O(n)** (Requires additional space for temporary subarrays)

## Stability
Merge Sort is a **stable sorting algorithm**, meaning it maintains the relative order of equal elements.

## Implementation (JavaScript)
```javascript
function mergeSort(nums) {
    if (nums.length <= 1) {
        return nums;
    }

    const mid = Math.floor(nums.length / 2);
    const leftHalv = mergeSort(nums.slice(0, mid));
    const rightHalv = mergeSort(nums.slice(mid));

    return merge(leftHalv, rightHalv);
}

function merge(leftHalv, rightHalv) {
    const result = [];
    let [i, j] = [0, 0];

    while (i < leftHalv.length && j < rightHalv.length) {
        if (leftHalv[i] <= rightHalv[j]) {
            result.push(leftHalv[i]);
            i += 1;
        } else {
            result.push(rightHalv[j]);
            j += 1;
        }
    }

    return [...result, ...leftHalv.slice(i), ...rightHalv.slice(j)]
}

// Example usage:
console.log(mergeSort([5, 3, 8, 4, 2]));
```

## Advantages
- **Efficient for large datasets** with O(n log n) complexity
- **Stable sorting algorithm**
- **Performs well on linked lists** (avoids expensive shifting)

## Disadvantages
- Requires **additional space** (O(n)) for merging subarrays
- **Slower for small datasets** compared to simpler algorithms like Insertion Sort

## When to Use Merge Sort
- When sorting **large datasets**
- When **stability** is required
- When working with **linked lists** (avoids shifting elements)

## Conclusion
Merge Sort is a powerful sorting algorithm that ensures **consistent O(n log n) performance**. Although it requires additional space, it is ideal for **large datasets** and scenarios where a **stable sorting method** is needed.

