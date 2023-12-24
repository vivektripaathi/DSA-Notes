# Binary Search
**Binary Search** is defined as a searching algorithm used in a sorted array by **repeatedly dividing the search interval in half**.
- The idea of binary search is to use the information that the array is sorted and reduce the time complexity to O(log N).]
- To apply Binary Search algorithm:
  - The data structure must be sorted.
  - Access to any element of the data structure takes constant time.

![Binary Search Example](https://media.geeksforgeeks.org/wp-content/uploads/20220309171621/BinarySearch.png)
## Implementation of Binary Search Algorithm
The **Binary Search Algorithm** can be implemented in the following two ways
- Iterative Binary Search Algorithm
- Recursive Binary Search Algorithm
## Iterative Binary Search Function (c++)
```cpp
int binarySearch(int *arr, int key, int size){
    int low = 0, high = size - 1;
    while(low <= high){
        int mid = (low + high) / 2;
        if(key == arr[mid]) return mid;
        else if(key < arr[mid]) high = mid - 1;
        else low = mid + 1;
    }
    return -1;
}
```

## Recursive Binary Search Function (c++) 
```cpp
int binarySearch(int arr[], int key, int high, int low){
    if(low > high) return -1;
    int mid = (low + high) / 2;
    if(arr[mid] == key) return mid;
    else if(arr[mid] > key) return binarySearch(arr, key, mid - 1, low);
    else return binarySearch(arr, key, high, mid + 1);
}
```

## Complexity Analysis of Binary Search:

**Time Complexity:** 
- **Best Case**: O(1)
- **Average Case**: O(log N)
- **Worst Case**: O(log N)

- **Auxiliary Space:** O(1), If the recursive call stack is considered then the auxiliary space will be O(logN).
