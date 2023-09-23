---
layout: default
title: Overriding Methods and the `super()` Function
parent: Inheritance and Polymorphism
grand_parent: Object-Oriented Python
nav_order: 2
---
# Overriding Methods and the `super()` Function

In object-oriented programming, **inheritance** allows a class to inherit properties and methods from another class. In Python, overriding methods is a powerful feature that enables you to redefine methods inherited from a parent class in the child class. This allows you to customize the behavior of the method specifically for the child class without modifying the parent class.

## Understanding Method Overriding

Method overriding allows a child class to provide a different implementation of a method that is already defined in its parent class. When a method is overridden, the parent class's implementation is replaced with the child class's implementation. This means that when the method is called on an instance of the child class, the overridden implementation will be executed instead.

This concept is best explained with an example. Let's consider a scenario where we have a `Rectangle` class as the parent class and a `Square` class as the child class. Both classes have a method called `area()` that calculates the area of the shape. However, the formula to calculate the area of a rectangle is different from the formula to calculate the area of a square.

```python
class Rectangle:
    def __init__(self, length, width):
        self.length = length
        self.width = width

    def area(self):
        return self.length * self.width

class Square(Rectangle):
    def __init__(self, side):
        super().__init__(side, side)

    def area(self):
        return self.length ** 2
```

In the above example, the `Square` class inherits from the `Rectangle` class and overrides the `area()` method. When `area()` is called on an instance of the `Square` class, the overridden implementation in the `Square` class will be executed, returning the square of the length.

This concept of method overriding is crucial in object-oriented programming as it allows us to create specialized behavior in child classes while still benefiting from code reuse through inheritance.

## The Role of the `super()` Function

In Python, the `super()` function plays a vital role in method overriding. It allows us to call a method in the parent class from the child class, thus enabling us to extend or customize the behavior of the inherited method.

To demonstrate this, let's extend our previous example by introducing another child class called `Cuboid`. The `Cuboid` class will inherit from the `Rectangle` class and override the `area()` method to calculate the surface area of the cuboid.

```python
class Cuboid(Rectangle):
    def __init__(self, length, width, height):
        super().__init__(length, width)
        self.height = height

    def area(self):
        return 2 * (self.length * self.width + self.length * self.height + self.width * self.height)
```

In the above example, the `Cuboid` class inherits from the `Rectangle` class and overrides the `area()` method to provide its own implementation. However, it still needs to call the `__init__()` method from the `Rectangle` class to initialize the length and width variables. This is achieved using the `super()` function.

The `super().__init__(length, width)` line in the `Cuboid` class calls the `__init__()` method of the `Rectangle` class, passing the required arguments. This ensures that the necessary initialization steps from the parent class are executed before continuing with the child class's initialization.

Using the `super()` function in this way allows for better code organization and maintainability, as it reduces redundant code and ensures that all necessary steps defined in the parent class are executed.

## Practical Applications

Overriding methods and using the `super()` function are not simply concepts for theoretical understanding; they have practical relevance and can be applied in various real-world scenarios.

- In a web development project, you may have a base class for handling authentication and authorization. The child classes, representing specific user roles like `Admin`, `Editor`, and `User`, can override methods such as `can_create`, `can_edit`, and `can_delete` to define role-specific permissions.

- In a game development project, you can have a parent class for game entities like `Character` or `Monster`. Subclasses like `PlayerCharacter`, `EnemyCharacter`, or `BossCharacter` can override methods such as `attack` or `move` to define unique behavior for each entity type.

- In a scientific computing application, you could have a base class for numerical computation techniques. Child classes representing different techniques, like `GradientDescent`, `NewtonRaphson`, or `GeneticAlgorithm`, can override methods such as `step` or `update` to implement specific algorithmic steps.

These are just a few examples of how method overriding and the `super()` function can be used to customize behavior and create specialized implementations in different domains.

## Conclusion

Overriding methods and utilizing the `super()` function are essential tools in Python to facilitate customization and specialization in object-oriented programming. By using method overriding, you can redefine behavior inherited from a parent class within a child class. The `super()` function allows you to call methods defined in the parent class, enabling you to extend or customize the inherited behavior.

Understanding how to override methods and correctly use the `super()` function will enhance your skills as a Python developer and empower you to write efficient and maintainable code.