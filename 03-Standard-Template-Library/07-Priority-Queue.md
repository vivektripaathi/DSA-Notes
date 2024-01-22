## Priority Queue
```cpp
void ExplainPQ(){
	priority_queue<int> pq;
	pq.push(5); //{5}
	pq.push(2); //{5, 2}
	pq.push(8); //{8, 5, 2}
	pq.emplace(10); //{10, 8, 5, 2}
	pq.pop(); // {8, 5, 2}
	cout<<pq.top(); //8


	//size swap empty function same as others.

	// Minimum Heap
	priority_queue<int, vector<int>, greater<int>> pq;
	pq.push(5); //{5}
	pq.push(2); //{2, 5}
	pq.push(8); //{2, 5, 8}
	pq.emplace(10); //{2, 5, 8, 19}
	cout<<pq.top(); // 2
}
```