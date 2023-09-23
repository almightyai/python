---
layout: default
title: Creating a Queue with deque
parent: Custom Data Structures Building From Scratch
grand_parent: Deep Dive into Data Structures
nav_order: 2
---
# Creating a Queue with deque

In Python, the `deque` class from the `collections` module provides a versatile and efficient implementation of a double-ended queue. A queue is a linear data structure that follows the First-In-First-Out (FIFO) principle. In other words, the first element added to the queue will be the first one to be removed.

## Importance of Queues

Queues are fundamental in computer science and are widely used in everyday coding. They are particularly useful in scenarios where we need to process elements in the order they were added. Some common use cases for queues include:

1. **Task scheduling**: Queues allow us to manage a collection of tasks and process them in an orderly manner, ensuring fairness and adherence to priority levels.

2. **Breadth-First Search (BFS) algorithm**: In graph theory, BFS uses queues to traverse and explore all the neighboring nodes of a given node, level by level.

3. **Message queuing systems**: In distributed systems, message queues enable asynchronous communication between different parts of an application or between different applications, providing reliability and scalability.

## The `deque` Class

While Python provides the `list` class to handle collections of items, the `deque` class is specifically designed to optimize operations performed at both ends of the queue. It offers various methods that allow efficient insertion and deletion of elements, making it an ideal choice for implementing a queue.

To use the `deque` class, we need to import it from the `collections` module:

```python
from collections import deque
```

## Creating a Queue with `deque`

We can create an empty queue using the `deque` class by simply calling the constructor:

```python
queue = deque()
```

We can also initialize a queue with some initial elements:

```python
queue = deque(['apple', 'banana', 'cherry'])
```

Now, let's dive into some practical examples to understand how to use the `deque` class to build a queue from scratch.

## Example 1: Task Scheduler

Suppose we are building a task scheduling system where we need to process a queue of tasks in the order they were added. We can use the `deque` class to implement the task queue:

```python
from collections import deque

# Create an empty task queue
task_queue = deque()

# Add tasks to the queue
task_queue.append('Task 1')
task_queue.append('Task 2')
task_queue.append('Task 3')

# Process tasks in FIFO order
while len(task_queue) > 0:
    task = task_queue.popleft()
    print(f"Processing task: {task}")
```

Output:
```
Processing task: Task 1
Processing task: Task 2
Processing task: Task 3
```

In this example, we use the `append()` method to add tasks to the end of the queue and the `popleft()` method to retrieve tasks from the front of the queue in a FIFO manner.

## Example 2: BFS Algorithm

Let's consider a scenario where we need to implement the BFS algorithm for traversing a tree-like structure represented by an adjacency list. We can utilize the `deque` class to store the nodes to be visited:

```python
from collections import deque

# Create an empty queue for BFS traversal
queue = deque()

# Add the starting node to the queue
queue.append('A')

# Perform BFS traversal
while len(queue) > 0:
    node = queue.popleft()
    print(f"Visiting node: {node}")
    
    # Enqueue all adjacent nodes of the current node
    # ...
```

Output:
```
Visiting node: A
```

In this example, we enqueue the starting node to the queue using the `append()` method. Then, we retrieve nodes from the front of the queue using the `popleft()` method and process them. We can continue adding adjacent nodes to the queue to traverse the graph level by level.

## Conclusion

The `deque` class from the `collections` module provides an efficient implementation of a double-ended queue in Python. By utilizing the `deque` class, we can easily create and manipulate queues. Whether you are building a task scheduling system or implementing graph algorithms like BFS, understanding and using queues is essential for efficient and organized coding.

Remember to import the `deque` class from the `collections` module before using it, and leverage the various methods it offers, such as `append()` and `popleft()`, to add and remove elements from the queue respectively. With its practical applications and efficient performance, the `deque` class is a valuable tool in your Python programming toolkit.