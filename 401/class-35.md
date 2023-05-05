# Graphs

## WHY

Graphs are powerful because they can model relationships between entities in a way that is not possible with other data structures. For example, consider a social network where each user is a vertex and the relationships between users are edges. A graph can be used to find the shortest path between two users or to identify clusters of users who have a common interest.

## WHAT

A graph is a collection of vertices (also known as nodes) and edges that connect these vertices. Vertices are represented by circles or dots, and edges are represented by lines that connect two vertices. Each edge represents a relationship between two vertices. A graph can be directed, where edges have a specific direction, or undirected, where edges do not have a direction.

Terminology for Graphs:

- Vertex: A vertex, also called a “node”, is a data object that can have zero or more adjacent vertices.

- Edge: An edge is a connection between two nodes.

- Neighbor: The neighbors of a node are its adjacent nodes, i.e., are connected via an edge.

- Degree: The degree of a vertex is the number of edges connected to that vertex.


## HOW

In Python, graphs can be represented using various data structures such as dictionaries, lists, sets, or classes. 

An example of an undirected graph using a dictionary is:

```python
    graph = {'A': ['B', 'C'],
             'B': ['C', 'D'],
             'C': ['D'],
             'D': ['C'],
             'E': ['F'],
             'F': ['C']}
```

In this example, each node is represented as a key in the dictionary, and its neighbors are represented as values in a list.

## Things I want to know more about

> References
>
>[Graphs](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/graphs.html)
>
>[Python Patterns - Implementing Graphs](https://www.python.org/doc/essays/graphs/)