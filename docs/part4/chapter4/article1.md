---
layout: default
title: Encapsulating Data Private and Protected Attributes
parent: Encapsulation and Abstraction
grand_parent: Object-Oriented Python
nav_order: 1
---
# Encapsulating Data: Private and Protected Attributes

In object-oriented programming, encapsulation refers to the practice of hiding internal data and implementation details of a class from external access. This allows for better control over the class's behavior and reduces the likelihood of unintentional misuse or modification of data. Python provides two mechanisms to achieve encapsulation: private and protected attributes.

## Private Attributes

Private attributes are denoted by prefixing a double underscore (`__`) to the attribute name. This naming convention signals that the attribute should not be accessed or modified outside the class definition. However, it's important to note that Python does not enforce true encapsulation, as accessing private attributes is still possible.

Nevertheless, using private attributes serves as a strong indicator to other developers that they should not rely on or modify these attributes. It promotes encapsulation by discouraging direct access and encouraging the use of getter and setter methods for attribute interaction.

```python
class BankAccount:
    def __init__(self, account_number, balance):
        self.__account_number = account_number
        self.__balance = balance
    
    def deposit(self, amount):
        self.__balance += amount
    
    def withdraw(self, amount):
        if self.__balance >= amount:
            self.__balance -= amount
        else:
            print("Insufficient funds")
    
    def get_balance(self):
        return self.__balance

account = BankAccount("123456789", 1000)
account.deposit(500)
account.withdraw(200)
print(account.get_balance())  # Output: 1300
print(account.__balance)      # Error: AttributeError: 'BankAccount' object has no attribute '__balance'
```

In the example above, the `BankAccount` class has private attributes `__account_number` and `__balance`. These attributes cannot be directly accessed outside the class. The `deposit` and `withdraw` methods provide a controlled way to modify the balance, while the `get_balance` method allows external code to retrieve the balance.

## Protected Attributes

Protected attributes are denoted by prefixing a single underscore (`_`) to the attribute name. While not truly restricted from external access, the single underscore serves as a convention that indicates the attribute should be treated as internal and not accessed directly from outside the class.

Protected attributes are typically used to indicate that a particular attribute or method is part of the class's implementation details but might be useful or necessary for subclasses. They help in maintaining a clear distinction between public interface and internal implementation.

```python
class Shape:
    def __init__(self, color):
        self._color = color
    
    def _draw(self):
        print(f"Drawing shape with color {self._color}")

class Circle(Shape):
    def __init__(self, color, radius):
        super().__init__(color)
        self._radius = radius
    
    def draw(self):
        self._draw()
        print(f"Drawing circle with radius {self._radius}")

shape = Circle("red", 5)
shape.draw()
print(shape._color)   # Output: red
```

In the example above, the `Shape` class has a protected attribute `_color` and a protected method `_draw`. The `_draw` method is intended for internal use only, while the `draw` method is a public method that can be called from external code. The `Circle` subclass inherits the protected attribute and method from the `Shape` class, showcasing their usefulness in subclassing scenarios.

### Conclusion

Encapsulating data using private and protected attributes is an essential practice in object-oriented programming. Although Python's enforcement of encapsulation is not as strict as in some other languages, adhering to the conventions of private and protected attributes provides clarity and maintainability to codebases.

By encapsulating data, developers can ensure that the internal workings of a class are shielded and provide controlled access through well-defined methods. This promotes modularity, prevents direct manipulation of internal state, and allows for easier maintenance and modification of code in the future.