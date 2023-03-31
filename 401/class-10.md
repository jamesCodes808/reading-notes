# Stacks and Queues

## Why?
- Stacks and queues are fundamental data structures used in programming.

- They help manage data by providing a way to add, remove, and manipulate elements.

- Stacks and queues are used in a variety of applications, such as parsing expressions, implementing algorithms, and managing computer memory.

## What?
- A stack is a Last-In-First-Out (LIFO) data structure. This means that the last element added to the stack is the first one to be removed.

- A queue is a First-In-First-Out (FIFO) data structure. This means that the first element added to the queue is the first one to be removed.

- Stacks and queues can be implemented using arrays or linked lists.

## How?

- To implement a stack using an array:

```python
class Stack:
    def __init__(self):
        self.items = []

    def push(self, item):
        self.items.append(item)

    def pop(self):
        if not self.is_empty():
            return self.items.pop()

    def is_empty(self):
        return len(self.items) == 0

```

- To implement a queue using a linked list: 

```python
class Node:
    def __init__(self, value=None):
        self.value = value
        self.next = None

class Queue:
    def __init__(self):
        self.head = None
        self.tail = None

    def enqueue(self, item):
        new_node = Node(item)
        if self.tail:
            self.tail.next = new_node
        else:
            self.head = new_node
        self.tail = new_node

    def dequeue(self):
        if not self.is_empty():
            dequeued = self.head
            self.head = self.head.next
            if not self.head:
                self.tail = None
            return dequeued.value

    def is_empty(self):
        return self.head is None

```

## What I want to know more about

- Queues and Stacks look very interesting and I definitely want to learn more and get hands on experience with them.


> References
>
>[Stacks and Queues](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/stacks_and_queues.html)