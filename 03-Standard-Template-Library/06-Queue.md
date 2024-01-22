## Queue
```cpp
void queueExplain(){
	queue<int> q;
	q.push(1); //{1}
	q.push(2); //{1, 2}
	q.emplace(3); //{1, 2, 3}
	q.back() += 5 //{1, 2, 8}
	q.pop(); //{1, 2}
	q.front() // 1
}
```