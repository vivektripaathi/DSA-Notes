# Circular Linked List
The **circular linked list** is a linked list where all nodes are connected to form a circle. In a circular linked list, the first node and the last node are connected to each other which forms a circle. There is no NULL at the end.

![CircularLinkeList](https://media.geeksforgeeks.org/wp-content/uploads/CircularLinkeList.png))

## Implementation  of Circular Linked List(c++)
```cpp
// Declared Node
struct Node{
	int data;
	Node *next;
	Node(int x){
		data = x;
		next = NULL;
	} 
}

int main(void) {
	// Initializing Nodes
	Node *head  = new Node(10);
	head -> next = new Node(20);
	head -> next -> next = new Node(30);
	head -> next -> next -> next = head;
	return 0;
}
```

## Traversal of Circular Linked List
```cpp
void circularTraversal(Node *head){
    if(head == NULL) return;
    Node *p = head;
    do{
        cout<< p -> data <<" ";
        p = p -> next;
    }while(p != head);
}
```

## Insertion in Circular Linked List
### Insertion at beginning
```cpp
// Naive Method
Node *insertAtBegin(Node *head, int x){
	Node *temp = new Node(x);
	if(head == NULL){
		temp -> next = temp;
		return temp;
	}
	else{
		Node *current = head;
		while(current -> next != head){
			current = current -> next;
		}
		current -> next = temp;
		temp -> next = head;
		return temp;
	}
}

// Efficient Solution
Node *insertAtBegin(Node *head, int x){
	Node *temp = new Node(x);
	if(head == NULL){
		temp -> next = temp;
		return temp;
	}
	else{
		temp -> next = head -> next;
		head -> next = temp;
		//swap data
		head -> data += temp -> data;
		temp -> data = head -> data - temp -> data;
		head -> data = head -> data - temp -> data;
	}
}
```
### Insertion at end
```cpp
Node *insertAtEnd(Node *head, int x){
    Node *temp = new Node(x);
	if(head == NULL){
		temp -> next = temp;
		return temp;
	}
	else{
	    Node *current = head;
	    while(current -> next != head){
	        current = current -> next;
	    }
	    current -> next = temp;
	    temp -> next = head;
	    return temp;
	}
}
```

## Deletion in Circular Linked List
### Delete First Node 
```cpp
Node *deleteAtEnd(Node *head){
	if(head == NULL) return NULL;
	if(head -> next == NULL){
	    delete(head);
	    return NULL;
	}
	else{
		Node * temp = head -> next;
	    head -> data = head -> next -> data;
	    head -> next = head -> next -> next;
	    delete(head);
	    return head;
	}
}
```

### Delete Kth Node


# Circular Doubly Linked List