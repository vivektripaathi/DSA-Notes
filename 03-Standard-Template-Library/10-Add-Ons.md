## Sorting Algo
```cpp
void sorting(){
	sort(a, a+n);
	sort(v.begin(), v.end());
	sort(a+2, a+4);
	sort(a, a+n, greater<int>);

	pair<int, int> a[] = {{1, 2}, {2, 1}, {4, 1}};
	// sort it according to second element
	// if second element is same, then sort
	// it according to first element but in descending
	bool comp(pair<int, int>p1, pair<int, int>p2){
	if(p1.second < p2.second) return true;
	if(p1.second > p2.second) return false;
	// if they are same
	if(p1.first > p2.first) return true;
	}
	sort(a, a+n, comp);

}
```

## Count Set Bits
```cpp
void countSetBits(){
	int num = 7;
	int cnt = __builtin_popcount(); //count set bits

	long long num = 123124243242234;
	int cnt = __builtin_popcountll(num); //count set bits
}
```

## Permutation
```cpp
void permutation(string s){
    sort(s.begin(), s.end());
    do{
        cout<<s<<endl;
    }while(next_permutation(s.begin(), s.end()));
}
```

## Maximum Minimum Elements
```cpp
void max(){
	return *max_element(a, a+n); 
}

void min(){
	return *min_element(a, a+n); 
}
```
