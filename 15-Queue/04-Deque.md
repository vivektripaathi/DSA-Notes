# Deque
Generalized version of [Queue](/15-Queue/01-Introduction.md) that allows insert and delete at both the ends.

## Array Implementation of Deque
```cpp
struct Deque{
    int size, cap;
    int *arr;
    Deque(int x){
        cap = x;
        arr = new int[cap];
        size = 0;
    }
    bool isEmpty(){
        return size == 0;
    }
    bool isFull(){
        return (cap == size);
    }
    int getRear(){
        if(isEmpty()){
            cout<<"Stack is empty"<<endl;
            return -1;
        }
        return size-1;
    }
    void insertRear(int x){
        if(isFull()){
            cout<<"Stack is Full"<<endl;
            return;
        }
        arr[size] = x;
        size++;
    }
    void deleteRear(){
        if(isEmpty()){
            cout<<"Stack is empty"<<endl;
            return;
        }
        size--;
    }
    void insertBegin(int x){
        if(isFull()){
            cout<<"Stack is Full"<<endl;
            return;
        }
        for(int i = size-1; i >= 0; i--){
            arr[i+1] = arr[i];
        }
        arr[0] = x;
        size++;
    }
    void deleteBegin(){
        if(isEmpty()){
            cout<<"Stack is empty"<<endl;
            return;
        }
        for(int i = 0; i < size-1; i--){
            arr[i] = arr[i+1];
        }
        size--;
    }
};
```