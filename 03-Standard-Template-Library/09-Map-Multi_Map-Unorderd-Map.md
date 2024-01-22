## Map
```cpp
void mapExplained(){
	// Declaration
	map<int, int> mpp;
	map<int, pair<int, int>> mpp;
	map<pair<int, int>, int> mpp;

	//Initialization
	mpp[1] = 2;  //{1, 2}
	mpp.emplace(3, 1); // {3, 1}
	mpp.insert({ 2, 4 }); //{2, 4}
	/*
	{
		{1, 2}
		{3, 1}
		{2, 4}
	}
	*/	
	mpp[{2, 3}] = 10; // {{2, 3}, 10}

	// Accessing
	for(auto i : mpp) cout<<i.first<<" "<<i.second<<endl;
	cout<<mpp[1]; // 2
	cout<<mpp[9]; //0
}
```

## Multi Map
- Everything is same as map only, it can store duplicate keys.
- only `map_name[key]` cannot be used here.
```cpp
multimap<int, int> mltmpp;
```

## Unordered Map
- Everything is same as map only, it is not sorted.
```cpp
unordered_map<int ,int> umpp;
```
