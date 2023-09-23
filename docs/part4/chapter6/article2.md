---
layout: default
title: Factory Pattern Creating Objects without Specifying Exact Class
parent: Design Patterns in Python
grand_parent: Object-Oriented Python
nav_order: 2
---
# Factory Pattern: Creating Objects without Specifying Exact Class

## Introduction

In object-oriented programming, the Factory Pattern is a creational design pattern that allows us to create objects without specifying the exact class of the object that will be created. This pattern provides a way to encapsulate the object creation logic and abstract it from the client code. It promotes loose coupling between objects, making the code more flexible, maintainable, and extensible.

## Importance of Factory Pattern

The Factory Pattern is important in everyday coding for several reasons:

1. **Flexibility**: By decoupling the client code from the specifics of object creation, the Factory Pattern allows for greater flexibility. We can easily modify or extend the set of classes being created without impacting the existing code.

2. **Abstraction**: The Factory Pattern abstracts the process of object creation, providing a simplified interface for clients. Clients can create objects without being concerned about the implementation details or the specific class of the object being created.

3. **Code Reusability**: By centralizing object creation logic within the factory, we can reuse the same code across different parts of an application. This promotes code reusability and reduces duplication.

4. **Easy Testing**: With the Factory Pattern, testing becomes easier. By mocking or substituting the factory, we can control the creation of objects during testing, which enhances testability and enables isolated testing of client code.

## Intricacies of Factory Pattern

To understand the Factory Pattern, let's consider a practical example. Imagine you are building a system to manage different shapes in a 2D drawing application. You have various types of shapes such as circles, rectangles, and triangles.

Instead of directly creating shapes using their respective constructors, you can employ the Factory Pattern to create objects without specifying the exact class:

```python
class Shape:
    def draw(self):
        pass

class Circle(Shape):
    def draw(self):
        print("Drawing a circle")

class Rectangle(Shape):
    def draw(self):
        print("Drawing a rectangle")

class Triangle(Shape):
    def draw(self):
        print("Drawing a triangle")

class ShapeFactory:
    def create_shape(self, shape_type):
        if shape_type == "circle":
            return Circle()
        elif shape_type == "rectangle":
            return Rectangle()
        elif shape_type == "triangle":
            return Triangle()

# Usage:
factory = ShapeFactory()
circle = factory.create_shape("circle")
circle.draw()  # Output: "Drawing a circle"
```

In this example, the `ShapeFactory` encapsulates the creation of different shapes. It takes a `shape_type` parameter and returns an instance of the corresponding shape. The client code can create shapes without worrying about the implementation details of each shape constructor.

By using the Factory Pattern, we achieve loose coupling between the client code and the specific shape classes. If we want to add a new shape type, we can simply extend the factory by adding a new condition in the `create_shape` method, without modifying the client code.

## Relevance in Everyday Coding

The Factory Pattern is widely used in everyday coding, particularly in scenarios where the creation of objects involves complex or conditional logic. Some common real-world applications of the Factory Pattern include:

1. **Database Abstraction**: When working with different database providers, the Factory Pattern can be used to create database connection objects without specifying the exact provider (e.g., MySQL, PostgreSQL, SQLite).

2. **Dependency Injection**: In dependency injection frameworks, the Factory Pattern is often utilized to create and inject dependencies into objects dynamically while decoupling the client code from the specific implementations.

3. **Plugin Systems**: When developing applications that support plugins or extensions, the Factory Pattern is frequently employed to instantiate and manage plugin objects.

Overall, the Factory Pattern plays a crucial role in creating flexible, maintainable, and extensible code. It enables developers to abstract the object creation process, promotes code reusability, and provides a simple interface for client code to create objects without tight coupling to their specific classes.