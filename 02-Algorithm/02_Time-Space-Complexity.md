
# Time Complexity
Time complexity can be defined as the time taken to execute each statement of code of an algorithm till its completed with respect to function of length of the input.

## Time Complexity Examples

>[!Example] Example 1: $O(n)$
```cpp
for(i=0; i<n; i++){
	start;        ---- n
}

for(i=0; i<n; i=i+2){
	start;        ---- n/2
}

for(i=0; i<n; i++){
	start;        ---- n
}

for(i=0; i<n; i++){
	start;        ---- n
}
	f(n) = 2n         ---- n
```

> [!Example] Example 2: $O(n^2)$
```cpp
for(i=0; i<n; i++){
	for(j=0; ijn; j=j+2){
		start;
	}
}

for(i=0; i<n; i++){
	for(j=0; j<i; j++){
		start;        ---- n(n+1)/2
	}
}
```

> [!Example] Example 3: $O(\sqrt n)$
```cpp
for(i = 0; i*i<n; i++){
	start;           
}

p = 0;
for(i = 1; i<=n; i++){      ---- n
	p=p+1;                  ---- k(k+1)/2
}
```


> [!Example] Example 4: $O(\log_2 n)$
```cpp
for(i=n; i>=1; i=i/2){
	start;
}

for(i=n; i>=1; i=i*2){
	start;
}
```

> [!Example] Example 5: $O(\log_3 n)$
```cpp
for(i=n; i>=1; i=i/3){
	start;
}

for(i=n; i>=1; i=i*3){
	start;
}
```

> [!Example] Example 6: $O(\log\log n)$
```cpp
p = 0;
for(i = 0; i<n; i = i*2){
	p++;          ---- log n
}
for(j = i; j<p; j = j*2){
	start;        ---- log p
}
```
