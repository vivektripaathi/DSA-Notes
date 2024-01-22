```cpp
void selectionSort(int arr[], int n){
	int i, j;
	for(i = 0; i < n-1; i++){
		int min = i;
		for(j = i + 1; j < n; j++){
			if(arr[min] > arr[j]) min = j;
		}
		if(min != i){
			swap(arr[min], arr[i]);
		}
	}
}
```