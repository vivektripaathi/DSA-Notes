# Insertion Sort


```cpp
void insertionSort(int arr[], int n){
	int i , j;
	for(i = 1; i < n; i++) {
		int key = arr[i];
		j = i - 1;
		while(j >= 0 && arr[j] > key){
			arr[j+1] = arr[j];
			j--;
		}
		arr[j+1] = key;
	}
}
```

## Complexity Analysis of Insertion Sort Algorithm:

**Time Complexity**:
- **Best Case** (i.e. Already Sorted): $\theta(n)$.
- **Worst Case** (i.e. Reverse Sorted): $\theta(n^2)$.
- **Average Case**:  $O(n^2)$.

**Space Complexity**: 
