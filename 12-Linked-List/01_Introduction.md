#  Linked List

A linked list is a linear data structure, that consists of collection of nodes are not stored at contiguous memory locations.
- Each node contains a data field and a pointer to the next node in the list.
-  The last node in the list will have a pointer to null.

## Memory Representation of Linked List

## Implementation  of Linked List(c++)
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

int main(void){
	// Initializing Nodes
	Node *head  = new Node(10);
	Node *node2 = new Node(20);
	Node *node3 = new NODE(30);
	// Linking nodes to form linked list
	head -> next = node2;
	node2 -> next = node3;

// Another way to do same

		Node *head  = new Node(10);
		head -> next  = new Node(20);
		head -> next -> next = new Node(30);

	return 0;
}

// OR 
```

## Traversal of Singly Linked List
###  Iterative Traversal of Singly Linked List
```cpp
void singlyTraversal(Node * head){
    Node *pointer = head;
    while(pointer != NULL){
        cout<<pointer->data<<" ";
        pointer = pointer -> next;
    }
}
```
### Recursive Traversal of Singly Linked List
```cpp
void resuriveSinglyTraversal(Node * head){
    if(head == NULL) return;
    cout<<head->data<<" ";
    resuriveSinglyTraversal(head -> next);
}
```

## Insertion in Singly Linked List
### Insertion at beginning
```cpp
Node *insertAtBegin(Node * head, int x){
	Node *temp = new Node(x);
	temp -> next = head;
	return temp;
}
```
### Insertion at End
```cpp
Node *insertAtEnd(Node * head, int x){
    Node *temp = new Node(x);
    if(head == NULL) return temp;
    Node *current = head;
    while(current -> next != NULL) current = current->next;
    current->next = temp;
    return head;
}
```
### Insertion at given position
```cpp
Node *insertAtGivePos(Node * head, int x, int pos){

	Node *current = head;
	Node *temp = new Node(x);
	int count = 1;
	while(count <= pos){
		if(count == pos){
			temp -> next = current -> next;
			current -> next = temp;
		}
		current = current -> next;
	}
	return current;
}
```

## Deletion in Singly Linked List
### Delete First Node 
```cpp
Node *deleteAtBegin(Node * head){
    if (head == NULL) return head;
    return head->next;
}
```
### Delete Last Node
```cpp
Node *deleteLastNode(Node * head){
	if(head == NULL) return NULL;
	if(head -> next == NULL){
		delete(head);
		return NULL;
	}
	Node *current = head;
	while(current -> next -> next != NULL){
		current = current -> next;
	}
	delete(current -> next);
	current -> next = NULL;
	return head;
}
```

## Searching in Singly Linked List
### Iterative searching
```cpp
int searchIterative(Node *head, int x){
    int position = 1;
    Node *current = head;
    while(current != NULL){
        if(current -> data == x) return position;
        else{
            position++;
            current = current -> next;
        }
    }
}
```
### Recursive searching
```cpp
int recursiveSearch(Node *head, int x){
    if(head == NULL) return -1;
    if(head -> data == x) return 1;
    else{
        int res = recursiveSearch(head -> next, x);
        if(res == -1) return -1;
        else return(res + 1);
    }
}
```

