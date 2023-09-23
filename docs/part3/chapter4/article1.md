---
layout: default
title: namedtuple Creating Simple Classes Efficiently
parent: Advanced Data Structures from the collections Module
grand_parent: Deep Dive into Data Structures
nav_order: 1
---
# namedtuple: Creating Simple Classes Efficiently

In Python, one of the most commonly used data structures is a class. Classes allow us to define our own data types and encapsulate data and functions into a single unit. However, creating classes in Python can sometimes be a tedious and verbose task. This is where the `namedtuple` class from the `collections` module comes to the rescue.

## Introduction to namedtuple

The `namedtuple` function in Python allows you to create simple classes efficiently. It is a subclass of the built-in `tuple` type, and it creates a new class that is an immutable, tuple-like object with named fields. It provides an easy way to define lightweight classes without the need to write a full-blown class definition.

## Benefits of Using namedtuple

Using `namedtuple` has several advantages over manually writing a class:

1. **Readability:** By using `namedtuple`, we can give meaningful names to the fields. This improves the readability of the code, making it more maintainable and easier to understand for other developers.

2. **Simplicity:** `namedtuple` provides a simple and concise syntax to define a class with named fields. It reduces the amount of code we need to write and maintain.

3. **Efficiency:** Since `namedtuple` is implemented in C, it is highly optimized for performance. It is faster and more memory-efficient compared to creating a custom class.

## Creating a namedtuple

To create a `namedtuple`, we first need to import it from the `collections` module. Let's take an example of creating a `Point` class using `namedtuple`:

```python
from collections import namedtuple

Point = namedtuple('Point', ['x', 'y'])
```

In the above example, we have created a `Point` class using `namedtuple`. The class has two fields, `x` and `y`, which represent the coordinates of a point in a two-dimensional space.

We can now create instances of the `Point` class just like we would with any other class:

```python
p1 = Point(1, 2)
p2 = Point(3, 4)

print(p1.x, p1.y)  # Output: 1 2
print(p2.x, p2.y)  # Output: 3 4
```

## Accessing Fields in a namedtuple

The fields in a `namedtuple` can be accessed using dot notation, just like we would with a regular class:

```python
print(p1.x)  # Output: 1
print(p2.y)  # Output: 4
```

## Namedtuple as a Lightweight Alternative to Classes

`namedtuple` provides a lightweight alternative to creating full-fledged classes in certain scenarios. Suppose we need to represent a student's information, including their name, age, and grade. We can use a namedtuple instead of creating a custom class:

```python
Student = namedtuple('Student', ['name', 'age', 'grade'])

s1 = Student('Alice', 20, 'A')
s2 = Student('Bob', 19, 'B')

print(s1.name, s1.age, s1.grade)  # Output: Alice 20 A
print(s2.name, s2.age, s2.grade)  # Output: Bob 19 B
```

By using `namedtuple` in this case, we avoid writing a full class definition while still having a cleaner and more readable code.

## Conclusion

`namedtuple` is a powerful tool in Python that allows developers to create simple classes efficiently. It improves the readability, simplicity, and performance of our code by providing a concise syntax for defining lightweight classes. By using practical examples and real-world scenarios, we have explored the importance, intricacies, and relevance of `namedtuple` in everyday coding. Consider utilizing `namedtuple` in your projects to enhance your Python coding experience.