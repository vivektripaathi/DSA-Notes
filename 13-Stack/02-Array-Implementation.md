# Array Implementation  of Stack(c++)
## Using `Struct`
```cpp
#include <iostream>
using namespace std;

struct MyStack{
	int *arr;
	int cap;
	int top;
	MyStack(int c){
	    cap = c;
	    arr = new int[c];
	    top = -1;
	}
	void push(int x) {
	    if(top == cap-1){
	        cout<<"Stack overflow"<<endl;
	        return;
	    }
	    arr[++top] = x;
	    cout<<"Item Pushed into stack"<<endl;
	    return;
	}
	void pop(){
	    if(top == -1){
	        cout<<"Stack underflow"<<endl;
	        return;
	    }
	    top--;
	    cout<<"Item poped from stack"<<endl;
	    return;
	}
	int peek(){
	    if(top == -1){
	        cout<<"Stack underflow"<<endl;
	        return 0;
	    }
	    return arr[top];
	}
	int size(){
	    return top+1;
	}
	bool isEmpty(){
	    return top == -1;
	}
	
};


int main(void) {
	MyStack s(3);
	s.push(1);
	cout<<s.peek()<<endl;
	s.push(2);
	cout<<s.peek()<<endl;
	s.push(3);
	s.push(4);
	cout<<s.peek()<<endl;
	s.pop();
	cout<<s.peek()<<endl;
	s.pop();
	cout<<s.peek()<<endl;
	s.pop();
	cout<<s.peek()<<endl;
	return 0;
}
```

## Using `Class`
```cpp
#include <bits/stdc++.h>
using namespace std;
#define MAX 1000

class Stack {
	int top;

public:
	int a[MAX]; // Maximum size of Stack
	Stack() {
		top = -1;
	}
	bool push(int x);
	int pop();
	int peek();
	bool isEmpty();
};

bool Stack::push(int x)
{
	if (top >= (MAX - 1)) {
		cout << "Stack Overflow";
		return false;
	}
	else {
		a[++top] = x;
		cout << x << " pushed into stack\n";
		return true;
	}
}

int Stack::pop()
{
	if (top < 0) {
		cout << "Stack Underflow";
		return 0;
	}
	else {
		int x = a[top--];
		return x;
	}
}
int Stack::peek()
{
	if (top < 0) {
		cout << "Stack is Empty";
		return 0;
	}
	else {
		int x = a[top];
		return x;
	}
}

bool Stack::isEmpty()
{
	return (top < 0);
}

int main()
{
	class Stack s;
	s.push(10);
	s.push(20);
	s.push(30);
	cout << s.pop() << " Popped from stack\n";
	
	//print top element of stack after poping
	cout << "Top element is : " << s.peek() << endl;
	
	//print all elements in stack :
	cout <<"Elements present in stack : ";
	while(!s.isEmpty())
	{
		// print top element in stack
		cout << s.peek() <<" ";
		// remove top element in stack
		s.pop();
	}

	return 0;
}
```
