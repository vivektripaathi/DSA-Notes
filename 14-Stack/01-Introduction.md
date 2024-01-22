# Stack 
Stack is an Abstract Data Structure that follows a particular order in which the operations are performed.
The order in which the operations are performed in stack is described as **Last In First Out**  referred to by acronym **LIFO** or **First In Last Out** referred to by acronym **FILO**.

## Operations of stack
- **`isempty()`**:  Returns `true` if the stack is empty else `false`.
- **`push()`**: Inserts an item to the top of the stack.
- **`pop()`**: Removes an item from the top the stack.
- **`peek()`**: Returns the top item.
- **`size()`**: Returns the size of stack.

### Corner Conditions on operations
- **Underflow**: When `peek()` or `pop()` is called on an empty stack.
- **Overflow**: When `push()` is called on a full stack.

## Implementation of Stack
1. [Array Implementation  of Stack](13-Stack/02-Array-Implementation.md)
2. [Linked List Implementation of Stack](13-Stack/03-Linked-List-Implementation.md)
   - Cpp provides built in [Stack STL](02-Standard-Template-Library/05-Stack) also.