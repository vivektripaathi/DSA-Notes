## Naive Method
```cpp
bool is_prime(int number){
    if (number == 1) return false;
    for(int i = 2; i <= number/2; i++){
        if (number % i == 0) return false;
    }
    return true;
}
```

## Efficient Method
```cpp
bool is_prime(int number){
	    if(number == 1) return false;
	    for(int i = 2; i * i <= number; i++){
        if (number % i == 0) return false;
    }
    return true;
}
```

## More Efficient Method
```cpp
bool isPrime(int number){
	if(number == 1) return false;
	if (number == 2 || number == 3) return true;
	if (number % 2 == 0 || number % 3 == 0) return false;
	for(int i = 5; i * i <= number; i += 6){
		if (number % i == 0 || number % (i+2) == 0) return false;
	}
	return true;
}
```