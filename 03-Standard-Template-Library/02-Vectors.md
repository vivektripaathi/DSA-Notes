## Vector

### Declaration & Initialisation
```cpp
void vectorExample(){
	vector<int> v;
	v.push_back(1);
	v.emplace_back(2);

	vector<pair<int, int>>vec;
	v.push_back({1, 2});
	v.emplace_back(1, 2);

	vector<int> v(5, 100); // {100, 100, 100, 100, 100}

	vector<int> v(5); // {0, 0, 0, 0, 0}

	vector<int> v1(5, 20);
	vector<int> v2(v1);
}

```

### Traversal
```cpp
void vectorTraversal(){
	cout<<v[0]<<" "<<v.at(0)<<endl;
	cout<<*v.back();*\\

	vector<int>::iterator it = v.begin();
	it++;
	cout<<*it<<" ";
	
	vectot<int>::iterator it = v.end();
	vectot<int>::iterator it = v.rend();
	vector<int>::iterator it = v.begin();

	for(vector<int>::iterator i = v.begin(); i != v.end(); i++){
		cout<<*i<<" ";
	}

	for(auto i = v.begin(); i != v.end(); i++){
		cout<<*i<<" "; 
	}

	for(auto i : v){
		cout<<i<<" "; 
	}
}
```

### Deletion
```cpp
void vectorDeletion(){
	vector<int> v = {1, 2, 3, 4, 5};
	v.erase(v.begin() + 1); // {1, 3, 4, 5}
	v.erase(v.begin() + 1, v.end() - 2); // {1, 4, 5}
}
```

### Insertion
```cpp
void vetorInsertion(){
	vector<int> v = {1, 2, 3, 4, 5};
	v.insert(v.begin(), 6); // {6, 1, 2, 3, 4, 5}
	v.insert(v.begin()+1, 2, 6); // {1, 6, 6,  2, 3, 4, 5}
	
	vector<int> v2 = {6, 6};
	v.insert(v.begin()+1, v2.begin(), v2.end()); // {1, 6, 6,  2, 3, 4, 5}
}
```

### More functions
```cpp
void moreAboutVector(){
	vector<int> v = {1, 2, 3, 4, 5};
	v.size();
	v.pop_back;
	v1.swap(v2);
	v.empty();
}
```