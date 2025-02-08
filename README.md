# Insertion Sort Algorithm

## Introduction
Insertion Sort is a simple and efficient comparison-based sorting algorithm. It builds the final sorted array one element at a time by inserting each element into its correct position.

## How Insertion Sort Works
1. Start with the second element (index 1) and compare it with the elements before it.
2. Shift larger elements to the right to make space for the current element.
3. Insert the current element into its correct position.
4. Repeat the process for all elements in the list.

## Time Complexity
| Case         | Time Complexity | Explanation |
|-------------|---------------|-------------|
| **Best Case**  | **O(n)**       | Already sorted, only one comparison per element |
| **Average Case**  | **O(n²)**     | Random order, requires shifting elements |
| **Worst Case**  | **O(n²)**     | Reverse sorted, maximum shifting needed |

## Space Complexity
- **O(1)** (In-place sorting, requires no extra memory apart from variables)

## Stability
Insertion Sort is a **stable sorting algorithm**, meaning it maintains the relative order of equal elements.

## Implementation (JavaScript)
```javascript
function insertionSort(arr) {
    for (let i = 1; i < arr.length; i++) {
        let key = arr[i];
        let j = i - 1;
        
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j]; // Shift element to the right
            j--;
        }
        arr[j + 1] = key; // Insert key in the correct position
    }
    return arr;
}

// Example usage:
console.log(insertionSort([5, 3, 8, 4, 2]));
```

## Advantages
- Simple to implement
- Efficient for **small datasets** or nearly sorted lists
- **Stable sorting algorithm**
- Works well for **online sorting** (sorting data as it arrives)

## Disadvantages
- **Inefficient for large datasets** due to **O(n²) complexity**
- Requires **shifting elements**, making it slower than other O(n log n) sorting algorithms

## When to Use Insertion Sort
- When sorting **small datasets** (less than ~50 elements)
- When data is **almost sorted** (best case O(n))
- When needing a **stable and simple** sorting method

## Conclusion
Insertion Sort is an intuitive sorting algorithm suitable for small or nearly sorted datasets. For large datasets, **Merge Sort (O(n log n))** or **Quick Sort (O(n log n) on average)** are more efficient choices.

