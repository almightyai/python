---
layout: default
title: Designing a Simple Stack Using Lists
parent: Custom Data Structures Building From Scratch
grand_parent: Deep Dive into Data Structures
nav_order: 1
---
# Designing a Simple Stack Using Lists

In this chapter, we will explore the concept of designing custom data structures in Python. Specifically, we will delve into building a simple stack using lists. A stack is a fundamental data structure that follows the LIFO (Last In, First Out) principle. It allows for the efficient insertion and removal of elements in a certain order, making it highly relevant in everyday coding tasks.

## Importance of Stacks in Programming

Stacks play a crucial role in various real-world scenarios and applications. Imagine a scenario where you are implementing an Undo/Redo feature in a text editor. You need a data structure that can maintain a history of the user's actions and allow for easy reversal of those actions. A stack, with its LIFO principle, is an ideal choice for this purpose.

Similarly, consider a situation where you are parsing arithmetic expressions to evaluate them. You come across parentheses, and you need to ensure that they are balanced correctly. A stack can be used to keep track of opening and closing brackets, making it easier to validate the expression.

Another example is the backtracking algorithm used in solving problems like the "N-Queens" puzzle. Here, a stack can be employed to store the current state and make the algorithm more efficient.

By understanding how to design a simple stack using lists in Python, you will have a valuable tool in your programming toolkit to tackle various scenarios effectively.

## Basic Structure of a Stack

Before diving into the implementation, let's take a moment to understand the basic structure of a stack. A stack consists of two primary operations:

1. **Push**: This operation adds an element to the top of the stack.
2. **Pop**: This operation removes the topmost element from the stack.

Additionally, a stack typically includes a few supporting operations:

- **Peek**: This operation returns the topmost element of the stack without removing it.
- **IsEmpty**: This operation checks whether the stack is empty or contains elements.

## Designing a Simple Stack Using Lists

Now, let's discuss how to design a simple stack using lists in Python. Python lists are dynamically resizable arrays that allow for efficient element insertion and retrieval.

Here is the basic implementation of a stack using a Python list:

```python
class Stack:
    def __init__(self):
        self.stack = []

    def push(self, element):
        self.stack.append(element)

    def pop(self):
        if not self.is_empty():
            return self.stack.pop()
        else:
            raise IndexError("Cannot pop from an empty stack.")

    def peek(self):
        if not self.is_empty():
            return self.stack[-1]
        else:
            raise IndexError("Cannot peek an empty stack.")

    def is_empty(self):
        return len(self.stack) == 0
```

Let's break down the implementation:

- The `__init__` method initializes an empty list to serve as the underlying data structure for our stack.
- The `push` method adds the given element to the top of the stack using the `append` function of Python lists.
- The `pop` method removes and returns the topmost element of the stack using the `pop` function of Python lists. It also checks for an empty stack and raises an `IndexError` in such cases.
- The `peek` method returns the topmost element of the stack without removing it. It also performs a check for an empty stack and raises an `IndexError` in such cases.
- The `is_empty` method checks whether the stack is empty by comparing the length of the stack to zero.

## Practical Examples

To better understand the usage and relevance of the stack data structure, let's consider a few practical examples.

### Example 1: Balancing Parentheses

Suppose you are tasked with writing a program to validate whether a given string of parentheses is balanced (i.e., each opening bracket has a corresponding closing bracket). We can utilize our stack implementation as follows:

```python
def is_balanced_parentheses(string):
    stack = Stack()
    opening_brackets = ['(', '[', '{']
    closing_brackets = [')', ']', '}']

    for char in string:
        if char in opening_brackets:
            stack.push(char)
        elif char in closing_brackets:
            if stack.is_empty():
                return False
            opening_bracket = stack.pop()

            if opening_brackets.index(opening_bracket) != closing_brackets.index(char):
                return False

    return stack.is_empty()
```

In this example, we iterate through each character of the input string. If we encounter an opening bracket, we push it onto the stack. If we encounter a closing bracket, we check whether the stack is empty. If it is empty, it means there is no corresponding opening bracket, so the parentheses are unbalanced. If the stack is not empty, we pop the opening bracket and compare its index with the index of the closing bracket. If they don't match, the parentheses are unbalanced.

### Example 2: Stack-Based Algorithms

Stacks find extensive use in solving various algorithms, one of which is the backtracking algorithm. Let's consider an example where we want to find a path from the start point to the destination point on a grid, following certain rules. We can solve this problem using a stack to perform backtracking:

```python
def find_path(start, destination, grid):
    stack = Stack()
    stack.push(start)

    while not stack.is_empty():
        current_position = stack.peek()
        if current_position == destination:
            return True

        next_position = find_next_position(current_position, grid)
        
        if next_position:
            stack.push(next_position)
        else:
            stack.pop()

    return False
```

In this example, we initialize a stack with the start position and iterate until the stack becomes empty. At each iteration, we check whether the current position is the destination. If it is, we've found a path. Otherwise, we find the next valid position based on certain rules, such as move constraints or obstacle avoidance. If a next position is found, we push it onto the stack. If not, we backtrack by popping the current position from the stack.

By thoroughly understanding the design and implementation of a simple stack using lists, you will be equipped to solve a wide range of real-world programming problems efficiently and effectively.