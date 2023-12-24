# Linear Search
**Linear Search** is defined as a sequential search algorithm that starts at one end and goes through each element of a list until the desired element is found, otherwise the search continues till the end of the data set.

![Linear Search Example](https://media.geeksforgeeks.org/wp-content/cdn-uploads/Linear-Search.png)

## Implementation of Binary Search Algorithm (c++)
```cpp
int linearSearch(int arr[], int key, int size){
	for(int i = 0; i < size; i++){
		if(arr[i] == key) return i;
	}
	return -1;
}

```

## Complexity Analysis of Linear Search:

**Time Complexity:**
- **Best Case:** In the best case, the key might be present at the first index. So the best case complexity is O(1)
- **Worst Case:** In the worst case, the key might be present at the last index i.e., opposite to the end from which the search has started in the list. So the worst-case complexity is O(N) where N is the size of the list.
- **Average Case:** O(N)

**Auxiliary Space:** O(1) as except for the variable to iterate through the list, no other variable is used.
