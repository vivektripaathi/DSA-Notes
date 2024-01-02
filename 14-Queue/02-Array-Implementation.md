# Array Implementation of Queue `C++`

## Naive Method
```cpp
struct Queue{
	int size, cap;
	int *arr;
	Queue(int c){
	    cap = c;
	    size = 0;
	    arr = new int[cap];
	}
	bool isEmpty(){
	    return (size == 0);
	}
	bool isFull(){
	    return (size == cap);
	}
	void enque(int x){
	    if(isFull()){
	        cout<<"Queue is full"<<endl;
	        return;
	    }
	    arr[size] = x;
	    size++;
	}
	void deque(){
	    if(isEmpty()){
	        cout<<"Queue is empty"<<endl;
	        return;
	    }
	    for(int i = 0; i < size -1; i++){
	        arr[i] = arr[i+1];
	    }
	    size--;
	}
	
};
```

## Efficient Method(Circular Array)
```cpp
struct Queue{
	int size, cap, front;
	int *arr;
	Queue(int c){
	    cap = c;
	    front = 0;
	    size = 0;
	    arr = new int[cap];
		}
	bool isEmpty(){
	    return (size == 0);
	}
	bool isFull(){
	    return (size == cap);
	}
	bool getFront() {
		if(isEmpty()) return -1;
		return front;
	}
	bool getRear(){
		if(isEmpty()) return -1;
		else return (front + size - 1) % cap;
	}
	void enque(int x){
	    if(isFull()){
	        cout<<"Queue is full"<<endl;
	        return;
	    }
	    int rear = getRear();
	    arr[rear] = x;
	    size++;
	}
	void deque(){
	    if(isEmpty()){
	        cout<<"Queue is empty"<<endl;
	        return;
	    }
	    for(int i = 0; i < size -1; i++){
	        arr[i] = arr[i+1];
	    }
	    size--;
	}
};
```

## Using `class`
```cpp
class Queue 
{ 
    public:
    int front, rear, size; 
    unsigned capacity; 
    int* array; 
}; 

// function to create a queue of a given capacity. 
// It initializes the size of the queue as 0 
Queue* createQueue(unsigned capacity) 
{ 
    Queue* queue = new Queue();
    queue->capacity = capacity; 
    queue->front = queue->size = 0; 
    queue->rear = capacity - 1; // This is important, see the enqueue 
    queue->array = new int[(queue->capacity * sizeof(int))]; 
    return queue; 
} 

// Queue is full when size 
// becomes equal to the capacity 
int isFull(Queue* queue) 
{ return (queue->size == queue->capacity); } 

// Queue is empty when size is 0 
int isEmpty(Queue* queue) 
{ return (queue->size == 0); } 

// Function to add an item to the queue. 
// It changes rear and size 
void enqueue(Queue* queue, int item) 
{ 
    if (isFull(queue)) 
        return; 
    queue->rear = (queue->rear + 1) % queue->capacity; 
    queue->array[queue->rear] = item; 
    queue->size = queue->size + 1; 
    cout << item << " enqueued to queue\n"; 
} 

// Function to remove an item from the queue. 
// It changes front and size 
int dequeue(Queue* queue) 
{ 
    if (isEmpty(queue)) 
        return INT_MIN; 
    int item = queue->array[queue->front]; 
    queue->front = (queue->front + 1) % queue->capacity; 
    queue->size = queue->size - 1; 
    return item; 
} 

// Function to get front of queue 
int front(Queue* queue) 
{ 
    if (isEmpty(queue)) 
        return INT_MIN; 
    return queue->array[queue->front]; 
} 

// Function to get rear of queue 
int rear(Queue* queue) 
{ 
    if (isEmpty(queue)) 
        return INT_MIN; 
    return queue->array[queue->rear]; 
} 
```