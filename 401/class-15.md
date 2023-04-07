# Trees 

## What are Trees?

In computer science, a tree is a non-linear data structure consisting of nodes connected by one or more parent-child relationships. Each node in a tree can have zero or more child nodes, except for the root node, which has no parent node. Trees are used to represent hierarchical structures, such as file systems, organization charts, and family trees.

## Why are Trees used?

Trees are used to represent data that has a hierarchical structure. They provide a way to organize and access data efficiently, as well as to perform operations such as search, insertion, and deletion quickly. Trees are also used in many algorithms and data structures, such as binary search trees, heaps, and tries.

## How do Trees work?

A tree consists of nodes connected by edges, which represent the parent-child relationships between nodes. The topmost node in a tree is called the root node, and all other nodes are descendants of the root. Each node can have zero or more child nodes, and each child node can have its own child nodes, forming a recursive structure.

## Common Terminology


- Node - A Tree node is a component which may contain its own values, and references to other nodes

- Root - The root is the node at the beginning of the tree

- K - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.

- Left - A reference to one child node, in a binary tree

- Right - A reference to the other child node, in a binary tree

- Edge - The edge in a tree is the link between a parent and child node

- Leaf - A leaf is a node that does not have any children

- Height - The height of a tree is the number of edges from the root to the furthest leaf

## How to build a Tree

- Binary Tree (collection of nodes that have 3 properties: value, left_child, right_child)

```python
class BinaryTree:
    def __init__(self, value):
        self.value = value
        self.left_child = None
        self.right_child = None
```

- K-ary Tree (When Nodes are allowed to have more than 2 children nodes)

```python
class TreeNode:
    def __init__(self, val):
        self.val = val
        self.children = []

# create root node
root = TreeNode(1)
```


## Things I want to know more about

- How to implement the basic functionality of a tree

- Better understanding of trees

>References
>
>[Trees](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/Trees.html)
>
>[An Introduction to Tree in Data Structure](https://www.simplilearn.com/tutorials/data-structure-tutorial/trees-in-data-structure)
>
>[What is a Tree in Computer Science?](https://www.codesdope.com/blog/article/trees-in-computer-science/)
>
>[Python - Binary Tree](https://www.tutorialspoint.com/python_data_structure/python_binary_tree.htm)