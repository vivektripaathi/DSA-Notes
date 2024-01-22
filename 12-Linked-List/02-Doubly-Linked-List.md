# Doubly Linked List
A **doubly linked list** (DLL) is a special type of linked list in which each node contains a pointer to the previous node as well as the next node of the linked list.

![Doubly Linked List](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2014/03/DLL1.png)

## Implementation  of Doubly Linked List(c++)
```cpp
// Declared Node
struct Node{
	int data;
	Node *prev;
	Node *next;
	Node(int x){
		data = x;
		next = NULL;
		prev = NULL;
	} 
}

int main(void) {
	// Initializing Nodes
	Node *head  = new Node(10);
	Node *node2 = new Node(20);
	Node *node3 = new NODE(30);
	// Linking nodes to form linked list
	head -> next = node2;
	node2 -> prev = head;
	node2 -> next = node3;
	node3 -> prev = node2;
	return 0;
}
```

## Insertion in Doubly Linked List
### Insertion at beginning
```cpp
Node * insertAtBegin(Node *head, int x){
    Node *temp = new Node(x);
    temp -> next = head;
    if(head !== NULL) head -> prev = temp;
    return temp;
}
```
### Insertion at End
```cpp
Node * insertAtGivenPosition(Node *head, int x){
    Node *temp = new Node(x);
    if(head == NULL) return temp;
    Node * current = head;
    while(current -> next != NULL){
        current = current -> next;
    }
    current -> next = temp;
    temp -> prev = current;
    return head;
}
```

## Reverse a Doubly Linked List
```cpp
Node *reverseDoubly(Node *head){
    if(head == NULL || head->next == NULL) return head;
    Node *previous = NULL;
    Node *current = head;
    while(current != NULL){
        previous = current -> prev;
        current -> prev = current -> next;
        current -> next = previous;
        current = current -> prev;
    }
    return previous -> prev;
}
```

## Deletion in Doubly Linked List
### Delete First Node 
```cpp
Node *deleteFirstNode(Node *head){
    if(head == NULL) return NULL;
    if(head -> next == NULL){
        delete(head);
        return NULL;
    }
    else{
        head -> next -> prev = NULL;
        return head -> next;
    }
}
```
### Delete Last Node
```cpp
Node *deleteLastNode(Node *head){
    if(head == NULL) return NULL;
    if(head -> next == NULL){
        delete(head);
        return NULL;
    }
    else{
        Node *current = head;
        while(current -> next -> next != NULL){
            current  = current -> next;
        }
        current -> next = NULL;
        delete(current -> next);
        return head;
    }
}
```
