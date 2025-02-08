# Quick Sort Algorithm

## Introduction
Quick Sort is a highly efficient and widely used sorting algorithm that follows the **divide and conquer** strategy. It works by selecting a "pivot" element and partitioning the array around the pivot, ensuring that elements smaller than the pivot are on the left and elements greater than the pivot are on the right.

## How Quick Sort Works
1. Select a pivot element from the array (commonly the last, first, or a random element).
2. Partition the array so that elements smaller than the pivot are on the left, and elements greater are on the right.
3. Recursively apply Quick Sort to the left and right partitions.
4. Combine the sorted partitions to form the final sorted array.

## Time Complexity
| Case         | Time Complexity | Explanation |
|-------------|---------------|-------------|
| **Best Case**  | **O(n log n)** | Evenly divides the array into halves |
| **Average Case**  | **O(n log n)** | Partitions effectively, maintaining balance |
| **Worst Case**  | **O(n²)** | Unbalanced partitioning (e.g., sorted or reverse-sorted array with bad pivot selection) |

## Space Complexity
- **O(log n) on average** (due to recursion stack)
- **O(n) in worst case** (highly unbalanced partitions)

## Stability
Quick Sort is **not a stable sorting algorithm**, meaning equal elements may change their relative order.

## Implementation (JavaScript)
```javascript
function quickSort(nums, low, high) {
    if (low < high) {
        const pivotIndex = partition(nums, low, high);
        quickSort(nums, low, pivotIndex - 1);
        quickSort(nums, pivotIndex + 1, high);
    }
}

function partition(nums, low, high) {
    const pivot = nums[high];
    let i = low - 1;
    for (let j = low; j <= high - 1; j++) {
        if (nums[j] < pivot) {
            i += 1;
            [nums[i], nums[j]] = [nums[j], nums[i]];
        }
    }

    [nums[i + 1], nums[high]] = [nums[high], nums[i + 1]];
    return i + 1;
}

// Example usage
const nums = [5,1,1,2,0,0]
quickSort(nums, 0, nums.length - 1);
```

## Advantages
- **Faster than O(n²) algorithms** like Bubble Sort, Selection Sort, and Insertion Sort
- **Efficient for large datasets**
- **In-place sorting with optimized implementations** (Lomuto or Hoare partitioning)

## Disadvantages
- **Worst-case time complexity is O(n²)** (but can be avoided with good pivot selection strategies)
- **Not stable**, meaning relative order of equal elements is not maintained
- **Recursive nature may cause stack overflow** on very large datasets

## When to Use Quick Sort
- When a **fast sorting algorithm** is needed
- When **extra space is limited** (optimized in-place versions exist)
- When **randomized pivot selection** can be used to minimize worst-case scenarios

## Conclusion
Quick Sort is one of the fastest and most efficient sorting algorithms for general use. For best performance, **Merge Sort** is a good alternative when **stability is required** or for **linked lists**.

