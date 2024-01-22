# Linked List Implementation of Queue `C++`

# Using `struct`
```cpp
struct Queue{
    int size;
    Node *front, *rear;
    Queue(){
	    front = NULL;
	    rear = NULL;
	    size = 0;
	}
    int getSize(){
        return size;
    }
	bool isEmpty(){
	    return (front == NULL);
	}
	Node *getFront(){
	    return front;
	}
	Node *getRear(){
	    return rear;
	}
	void enque(int x){
	    Node *temp = new Node(x);
	    size++;
	    if(front == NULL){
	        front = temp;
	        rear = temp;
	        return;
	    }
	    rear -> next = temp;
	    rear = temp;
	}
	void deque(){
	    if(front == NULL){
	        cout<<"Queue is empty"<<endl;
	        return;
	   }
	   Node *temp = front;
	   front = front -> next;
	   size--;
	   if(front == NULL) rear = NULL;
	   delete(temp);
	}
};
```
