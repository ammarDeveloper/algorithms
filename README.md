# Bubble Sort Algorithm

## Introduction

Bubble Sort is a simple comparison-based sorting algorithm. It repeatedly traverses the list, compares adjacent elements, and swaps them if they are in the wrong order. The process continues until the list is sorted.

## How Bubble Sort Works

1. Start at the beginning of the list.
2. Compare adjacent elements.
3. If they are out of order, swap them.
4. Move to the next pair and repeat.
5. After each pass, the largest element "bubbles up" to its correct position.
6. Repeat the process for the remaining elements until the list is sorted.

## Time Complexity

| Case             | Time Complexity | Explanation                            |
| ---------------- | --------------- | -------------------------------------- |
| **Best Case**    | **O(n)**        | Already sorted, only one pass needed   |
| **Average Case** | **O(n²)**       | Random order, multiple passes required |
| **Worst Case**   | **O(n²)**       | Reverse sorted, maximum swaps needed   |

## Space Complexity

- **O(1)** (In-place sorting, requires no additional memory apart from variables)

## Stability

Bubble Sort is a **stable sorting algorithm**, meaning it maintains the relative order of equal elements.

## Implementation (JavaScript)

```javascript
function bubbleSort(arr) {
     let n = arr.length;
    let swapped;
    do {
        swapped = false;
        for (let i = 0; i < n - 1; i++) {
            if (arr[i] > arr[i + 1]) {
                [arr[i], arr[i + 1]] = [arr[i + 1], arr[i]]; // Swap
                swapped = true;
            }
        }
        n--; // Reduce the range of elements to check
    } while (swapped);
    return arr;}

// Example usage:
console.log(bubbleSort([5, 3, 8, 4, 2]));
```

## Advantages

- Simple to implement
- Stable sorting algorithm
- Works well on small datasets

## Disadvantages

- **Inefficient for large datasets** due to **O(n²) complexity**
- Performs unnecessary swaps even when the list is nearly sorted
- Other algorithms like **Merge Sort, Quick Sort, and Heap Sort** are more efficient

## When to Use Bubble Sort

- When simplicity is preferred over efficiency
- When working with **small datasets**
- When the dataset is **almost sorted** (best case O(n))

## Conclusion

Bubble Sort is a fundamental sorting algorithm but is inefficient for large-scale use. For better performance, use **Merge Sort (O(n log n))** or **Quick Sort (O(n log n) on average)** instead.

