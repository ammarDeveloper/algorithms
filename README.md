# Selection Sort Algorithm

## Introduction
Selection Sort is a simple comparison-based sorting algorithm. It works by repeatedly selecting the smallest (or largest) element from the unsorted portion of the array and moving it to the sorted portion.

## How Selection Sort Works
1. Divide the array into two parts: **sorted** and **unsorted**.
2. Find the **smallest element** in the unsorted part.
3. Swap it with the **first element** of the unsorted part.
4. Move the boundary between the sorted and unsorted parts one step forward.
5. Repeat until the entire array is sorted.

## Time Complexity
| Case         | Time Complexity | Explanation |
|-------------|---------------|-------------|
| **Best Case**  | **O(n²)**       | Always scans the entire unsorted part, even if sorted |
| **Average Case**  | **O(n²)**     | Always makes (n-1) swaps in worst case |
| **Worst Case**  | **O(n²)**     | Reverse sorted, requires maximum swaps |

## Space Complexity
- **O(1)** (In-place sorting, requires no extra memory apart from variables)

## Stability
Selection Sort is **not a stable sorting algorithm** because swapping may change the relative order of equal elements.

## Implementation (JavaScript)
```javascript
function selectionSort(arr) {
    let n = arr.length;
    
    for (let i = 0; i < n - 1; i++) {
        let minIndex = i;
        for (let j = i + 1; j < n; j++) {
            if (arr[j] < arr[minIndex]) {
                minIndex = j;
            }
        }
        // Swap the found minimum element with the first element
        [arr[i], arr[minIndex]] = [arr[minIndex], arr[i]];
    }
    return arr;
}

// Example usage:
console.log(selectionSort([5, 3, 8, 4, 2]));
```

## Advantages
- Simple to implement
- Performs **at most n swaps**, which is better than Bubble Sort
- Works well for **small datasets**

## Disadvantages
- **Inefficient for large datasets** due to **O(n²) complexity**
- **Not stable**, which means equal elements may lose their relative order

## When to Use Selection Sort
- When the number of **swaps should be minimized**
- When sorting **small datasets** where performance is not critical
- When **stability is not required**

## Conclusion
Selection Sort is an intuitive sorting algorithm, but it is inefficient for large datasets. For better performance, use **Merge Sort (O(n log n))** or **Quick Sort (O(n log n) on average)** instead.

