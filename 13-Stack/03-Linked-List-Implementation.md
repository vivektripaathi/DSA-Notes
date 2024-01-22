# Linked List Implementation  of Stack(c++)
## Using `struct`
```cpp
#include <iostream>
using namespace std;

struct Node{
	int data;
	Node *next;
	Node(int x){
		data = x;
		next = NULL;
	}
}

struct MyStack{
	Node *head;
	int size;
	MyStack(){
	    head = NULL;
	    size = 0;
	}
	void push(int x) {
	    Node *temp = new Node(x);
	    temp -> next = head;
	    head = temp;
	    size++;
	    cout<<"Item Pushed into stack"<<endl;
	    return;
	}
	void pop(){
	    if(head == NULL){
	        cout<<"Stack underflow"<<endl;
	        return;
	    }
	    Node *temp = head;
	    head = head -> next;
	    delete(temp);
	    size--;
	    cout<<"Item poped from stack"<<endl;
	    return;
	}
	int peek(){
	    if(head == NULL){
	        cout<<"Stack underflow"<<endl;
	        return 0;
	    }
	    return head->data;
	}
	int size(){
	    return size;
	}
	bool isEmpty(){
	    return (head == NULL)
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
using namespace std;

// creating a linked list;
class Node {
public:
	int data;
	Node* link;

	// Constructor
	Node(int n)
	{
		this->data = n;
		this->link = NULL;
	}
};

class Stack {
	Node* top;

public:
	Stack() { top = NULL; }

	void push(int data)
	{

		// Create new node temp and allocate memory in heap
		Node* temp = new Node(data);

		// Check if stack (heap) is full.
		// Then inserting an element would
		// lead to stack overflow
		if (!temp) {
			cout << "\nStack Overflow";
			exit(1);
		}

		// Initialize data into temp data field
		temp->data = data;

		// Put top pointer reference into temp link
		temp->link = top;

		// Make temp as top of Stack
		top = temp;
	}

	// Utility function to check if
	// the stack is empty or not
	bool isEmpty()
	{
		// If top is NULL it means that
		// there are no elements are in stack
		return top == NULL;
	}

	// Utility function to return top element in a stack
	int peek()
	{
		// If stack is not empty , return the top element
		if (!isEmpty())
			return top->data;
		else
			exit(1);
	}

	// Function to remove
	// a key from given queue q
	void pop()
	{
		Node* temp;

		// Check for stack underflow
		if (top == NULL) {
			cout << "\nStack Underflow" << endl;
			exit(1);
		}
		else {

			// Assign top to temp
			temp = top;

			// Assign second node to top
			top = top->link;

			// This will automatically destroy
			// the link between first node and second node

			// Release memory of top node
			// i.e delete the node
			free(temp);
		}
	}

	// Function to print all the
	// elements of the stack
	void display()
	{
		Node* temp;

		// Check for stack underflow
		if (top == NULL) {
			cout << "\nStack Underflow";
			exit(1);
		}
		else {
			temp = top;
			while (temp != NULL) {

				// Print node data
				cout << temp->data;

				// Assign temp link to temp
				temp = temp->link;
				if (temp != NULL)
					cout << " -> ";
			}
		}
	}
};

// Driven Program
int main()
{
	// Creating a stack
	Stack s;

	// Push the elements of stack
	s.push(11);
	s.push(22);
	s.push(33);
	s.push(44);

	// Display stack elements
	s.display();

	// Print top element of stack
	cout << "\nTop element is " << s.peek() << endl;

	// Delete top elements of stack
	s.pop();
	s.pop();

	// Display stack elements
	s.display();

	// Print top element of stack
	cout << "\nTop element is " << s.peek() << endl;

	return 0;
}
```