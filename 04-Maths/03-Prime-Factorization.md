## Naive Method
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

void printPrimeFactor(int number){
	for (int i = 2; i < number; i++){
		if(isPrime(i)){
			int x = i;
			while(number % x == 0){
				cout << i << " ";
				x *= i;
			}
		}
	}
}
```

## Efficient Method
```cpp
void printPrimeFactor(int number){
	if (number <= 1) return;
	for(int i = 2; i * i <= number; i++){
		while(number % i == 0){
			cout << i << " ";
			number /= i;
		}
	}
}
```

##  More Efficient Method
```cpp
void printPrimeFactor(int number){
	if (number <= 1) return;
	while(number % 2 == 0){
		cout << 2 << " ";
		number /= 2;
	}
	while(number % 3 == 0){
		cout << 3 << " ";
		number /= 3;
	}
	for (int i = 5; i * i <= n; i+=6){
		while(number % i == 0){
			cout << i << " ";
			number /= i;
		}
		while (number % (i + 2) == 0){
			cout << i + 2 << " ";
			number /= (i + 2);
		}
	}
	if(number >= 3) cout << number;
}
```