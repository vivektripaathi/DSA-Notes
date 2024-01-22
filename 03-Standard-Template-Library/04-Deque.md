## Deque
```cpp
void dequeExplain(){
	deque<int> q;
	q.push_back(2); //{2}
	q.emplace_back(4); //{2, 4}

	q.push_front(5); //{5, 2, 4}
	q.emplace_front(6); //{6, 5, 2, 4}
	
	q.pop_back();
	q.pop_front();
	
	cout<<q.back()<<" "<<q.front()<<endl;

	// rest function are same as vector
	// begin, end, rend, rbegin, clear, insert, swap, and size
}
```