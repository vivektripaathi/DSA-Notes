## Stack
```cpp
void stackExplain(){
	stack<int> s;
	s.push(1); //{1}
	s.push(2); //{1, 2}
	s.push(3); //{1, 2, 3}
	s.emplace(4); //{1, 2, 3, 4}
	cout<<s.top()<<endl; // 4
	s.pop(); //{1, 2, 3}
	cout<<s.size()<<endl; // 3
	cout<<s.empty()<<endl; // False
}
```