# Linked Lists

## Basics of a Linked List and How to Manipulate it

A linked list is a data structure that consists of a sequence of elements, called nodes, that are connected to each other. 

Each node contains two parts: the data and a pointer to the next node in the list. 

The first node is called the head, and the last node is called the tail.

#### Node Class
The Node class is used to create nodes that will be added to the linked list. The constructor initializes the data and next pointer.

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

```

#### LinkedList Class

The LinkedList class is used to create a linked list. The constructor initializes the head to None.

#### Adding Nodes

The add_node method adds a new node to the end of the list. 
If the head is None, it sets the head to the new node. Otherwise, it traverses the list until it finds the last node and adds the new node as the next node.

```python
class LinkedList:
    def __init__(self):
        self.head = None

    def add_node(self, data):
        new_node = Node(data)
        if self.head is None:
            self.head = new_node
        else:
            curr_node = self.head
            while curr_node.next is not None:
                curr_node = curr_node.next
            curr_node.next = new_node

```

#### Removing Nodes

The remove_node method removes a node from the list by traversing the list and finding the node with the specified data. 

If the node is the head, it sets the head to the next node. Otherwise, it updates the next pointer of the previous node to skip over the removed node.

```python
class LinkedList:
    def __init__(self):
        self.head = None

    def remove_node(self, data):
        curr_node = self.head
        if curr_node.data == data:
            self.head = curr_node.next
            return curr_node
        while curr_node.next is not None:
            if curr_node.next.data == data:
                removed_node = curr_node.next
                curr_node.next = curr_node.next.next
                return removed_node
            curr_node = curr_node.next
        return None


```

#### Traversing List

The traverse_list method traverses the list and prints the data of each node.

```python
class LinkedList:
    def __init__(self):
        self.head = None

    def traverse_list(self):
        curr_node = self.head
        while curr_node is not None:
            print(curr_node.data)
            curr_node = curr_node.next

```


## Things I want to know more about

- Definitely want to dive deeper into the Big O Analysis algorithm efficiency document 

> References
>
>[Linked Lists](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/singly_linked_list.html)
>
>[Whats a linked list, anyway?](https://medium.com/basecs/whats-a-linked-list-anyway-part-1-d8b7e6508b9d)
>
>[Big O: Analysis of Algorithm Efficiency](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/big_oh.html)