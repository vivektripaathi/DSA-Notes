# Analysis of Recursion

>[!Example] Example 1
```cpp
void fun(int n){
	if (n > 0){
		return;
	}
	cout<<"Hello World";
	fun(n/2);
	fun(n/2);
}
```
T(n) = 2T($\frac n 2$) + $\theta$(1).
T(0) = O(1)

>[!Example] Example 2
```cpp
void fun(int n){
	if (n > 0){
		return;
	}
	for (int i = 0; i < n; i++){
		print('Hello World');
	}
	fun(n/2);
	fun(n/3);
}
```
T(n) = T($\frac n 2$) + T($\frac n 3$) + $\theta$(n)
T(0) = $\theta$(1)

>[!Example] Example 3
```cpp
void fun(int n){
	if(n <= 1){
		return ;
	}
	cout<<('Hello World');
	fun(n-1);
}
```
T(n) = T(n-1) + $\theta$(1)
T(0) = $\theta$(1)
