___
an ADT is a logical description of a data structure that specifies the data it stores and the operations that can be performed on the data **without** specifying the implementatiion details. 
- define a contract or interface
Example: Stack ADT in C using an array.
```c
#include <stdio.h>
#include <stdbool.h>

#define MAX_SIZE 100

typedef struct {
    int items[MAX_SIZE];
    int top;
} Stack;

void initStack(Stack *stack) {
    stack->top = -1;
}

bool isEmpty(Stack *stack) {
    return stack->top == -1;
}

bool isFull(Stack *stack) {
    return stack->top == MAX_SIZE - 1;
}

void push(Stack *stack, int item) {
    if (isFull(stack)) {
        printf("Error: Stack is full\n");
        return;
    }
    stack->items[++stack->top] = item;
}

int pop(Stack *stack) {
    if (isEmpty(stack)) {
        printf("Error: Stack is empty\n");
        return -1;
    }
    return stack->items[stack->top--];
}

int peek(Stack *stack) {
    if (isEmpty(stack)) {
        printf("Error: Stack is empty\n");
        return -1;
    }
    return stack->items[stack->top];
}

int main() {
    Stack myStack;
    initStack(&myStack);

    push(&myStack, 10);
    push(&myStack, 20);
    push(&myStack, 30);

    printf("Top element: %d\n", peek(&myStack));

    printf("Popped element: %d\n", pop(&myStack));
    printf("Popped element: %d\n", pop(&myStack));
    printf("Popped element: %d\n", pop(&myStack));

    return 0;
}
```
In this example, the Stack ADT is implemented using an array. The ADT provides operations like `push`, `pop`, `peek`, `isEmpty`, and `isFull`. The implementation details (using an array) are hidden from the users of the ADT, who only interact with the provided operations.