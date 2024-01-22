>[!Question] Find out all the prime number that are smaller than or equal to `n`
## Naive Method
```cpp
void primes(int number){
	for(int i = 2; i <= number; i++){
		if(isPrime(number)) cout<<i<<" ";
	}
}
```

## Efficient Method
```cpp
void seive(int number){
	vector<bool> isPrime(number + 1, true);
	for(int i = 2; i * i <= number; i++){
		if(isPrime[i]){
			for(int j = 2 * i; j <= number; j += i){
				isPrime[j] = false;
			}
		}
	}
	for(int i = 2; i <= number; i++){
		if(isPrime[i]) cout << i << " ";
	}
}
```

## Optimized Method
```cpp
void seive(int number){
	vector<bool> isPrime(number+1, true);
	for(int i = 2; i * i <= number; i++){
		if(isPrime[i]){
			for(int j = i * i; j <= number; j+= i){
				isPrime[j] = false;
			}
		}
	}
	for(int i = 2; i <= number; i++){
		if(isPrime[i]) cout<< i << " ";
	}
}
```

## Shorter Optimized Code
```cpp
void seive(int number){
	vector<bool> isPrime(number + 1, true);
	for(int i = 2; i <= number; i++){
		if(isPrime[i]){
			cout << i << " ";
			for(int j = i * i; j <= number; j+= i) isPrime[j] = false;
		}
	}
}
```
