## Set
```cpp
void setExplain(){
	set<int> s;
    s.insert(1); //{1}
    s.insert(1); //{1}
    s.insert(2); //{1, 2}
    s.insert(3); //{1, 2, 3}
    s.insert(4); //{1, 2, 3, 4}
    s.erase(2); //{1, 3}
    s.count(1); //1
	//Functionality in insert of vector can be used also, that will only increase efficiency.
	// begin(), end(), rbegin(), rend(), swap() and size() are same as those above.

	auto it = s.find(1);
	auto it = s.find(3);

	s.erase(4); //takes logartmuc time

	int count = st.count(1);

	auto it = s.find(4);
	s.erase(it);//it takes constant time

	//{1, 2, 3, 4, 5}
	auto it = s.find(2);
	auto it2 = s.find(4);
	v.erase(it, it2); // [2, 4)

	auto it = s.lower_bound(2);
	auto it = s.upper_bound(2);
}
```

## Multi Set
- It can store duplicate value.
```cpp
void multiSet(){
	multiset<int> ms;
    ms.insert(1); //{1}
    ms.insert(1); //{1, 1}
    ms.insert(1); //{1, 1, 1}
    
    //all 1's erased
    ms.erase(1);
    
    //only a single one erased
    ms.erase(ms.find(1));
}
```

## Unordered Set
- It does not stores in any particular order, also it has better time complexity in most of the cases, except some when collision happens.
- `lower_bound()` and `upper_bound()` functions does not work.
- rest all functions are same as above.

```cpp
void explainUSet(){
	unorderd_set<int> us;
}
```