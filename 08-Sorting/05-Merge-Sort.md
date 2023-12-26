# Merge Sort
- Divide and conquer Algorithm: (Divide, Conquer and merge).
- Stable Algorithm
- $\theta(n logn)$ time and $O(n)$ auxiliary space.
- Well suited for linked list. Works in O(n) auxiliary space.
- Used in external sorting.
- In general for arrays, Quick sort outperforms it.

![Merge Sort](https://media.geeksforgeeks.org/wp-content/cdn-uploads/Merge-Sort-Tutorial.png)

## Merge Function of Merge Sort
1. Create an array `arr3[]` of size n1 + n2.
2. Simultaneously traverse `arr1[]` and `arr2[]`.   
   - Pick smaller of current elements in `arr1[]` and `arr2[]`, copy this smaller element to next position in `arr3[]`and move ahead in `arr3[]` and the array whose element is picked.
3. If there are remaining elements in `arr1[]` or `arr2[]`, copy them also in `arr3[]`.

Below image is a dry run of the above approach:

![Merge Function of Merge Sort](https://media.geeksforgeeks.org/wp-content/uploads/20190708230512/editedMerge-two-sorted-arrays1.png)

## Merge Function
```cpp
void merge(int arr[], int low, int mid, int high){
    int n = mid-low+1;
    int m = high-mid;
    int arr1[n];
    int arr2[m];
    for(int i = 0; i < n; i++) arr1[i] = arr[low+i];
    for(int j = 0; j < m; j++) arr2[j] = arr[mid+1+j];
    int i = 0, j = 0, k = low;
    while(i < n && j < m){
        if(arr1[i] <= arr2[j]){
            arr[k] = arr1[i];
            i++;
        } else {
            arr[k] = arr2[j];
            j++;
        }
        k++;
    }
    while(i < n){
        arr[k] == arr1[i];
        i++;
        k++;
    }
    while(j < m){
        arr[k] == arr2[j];
        j++;
        k++;
    }
}
```

- **Time Complexity :** O(n1 + n2)   
- **Auxiliary Space :** O(n1 + n2)


## Merge Sort Function
```cpp
void mergeSort(int arr[], int begin, int end){
    if(end > begin){
        int mid = begin + (end - begin)/2;
        mergeSort(arr, begin, mid);
        mergeSort(arr, mid+1, end);
        merge(arr, begin, mid, end);
    }
}
```

## Complexity Analysis of Insertion Sort Algorithm:

**Time Complexity**:
- **Best Case** (i.e. Already Sorted): $\theta(n)$.
- **Worst Case** (i.e. Reverse Sorted): $\theta(n^2)$.
- **Average Case**:  $\theta(n logn)$.

**Space Complexity**: $\theta(n)$.