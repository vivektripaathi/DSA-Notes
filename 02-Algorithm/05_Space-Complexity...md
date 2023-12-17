# Space Complexity
 Space Complexity of an algorithm is the total space taken by an algorithm with respect to input size.

>[!warning] The term **Space Complexity** is misused for **Auxiliary Space** at many places.

>[!Note] 
>- **Auxiliary Space** is the extra space or temporary space used by an algorithm.
>- Space complexity includes both Auxiliary space and space used by input.

## Space Complexity Examples
> [!Example] Example 1 : O(1) | $\theta$(1)
```cpp
int getSum(int  n){
	return (n*(n+1))/2
}

int getSum1(int  n){ 	
	int sum = 0;
	for (int i = 0; i < n; i++){
 		sum += i;
 	}
 	return i;
}
```

>[!Example] Example 2 : $\theta$(n)
```cpp
int arrSum(int arr[], int n){
	int sum = 0;
	for (int i = 0; i < n i++){
		sum += arr[i];
	}
	return sum;
}
```

