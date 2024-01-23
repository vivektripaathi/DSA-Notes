# Tail Recursion
- <mark class="hltr-orange">Modern compilers eliminates tail call from tail recursive functions that makes them faster for large input values than normal recursive functions.</mark>
- What we see:
```cpp
// To print from n to 1
void print(int n){
	if(n == 0) return;
	cout<<n<<" ";
	func(n-1);
}
```
- what modern compilers do:
```cpp
// To print from n to 1
void print(int n){
	start:
	if(n == 0) return;
	cout<<n<<" ";
	n--;
	goto start; // tail call elimination
}
```
