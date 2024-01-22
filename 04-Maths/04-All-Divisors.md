## Naive Method
```cpp
void printAllDivisors(int number){
	for(int i = 1; i <= number; i++){
		if (number % i == 0) cout << i << " ";
	}
}
```

## Efficient Method
```cpp
void printAllDivisors(int number){
    int i;
    for (i = 1; i * i <= number; i++){
        if (number % i == 0) cout << i << " ";
    }
    for( ; i >= 1; i--){
        if (number % i == 0)  cout << number / i << " ";
    }
}
```
