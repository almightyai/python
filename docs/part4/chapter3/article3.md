---
layout: default
title: Types of Inheritance Single, Multiple, Multilevel, and Hierarchical
parent: Inheritance and Polymorphism
grand_parent: Object-Oriented Python
nav_order: 3
---
# Types of Inheritance: Single, Multiple, Multilevel, and Hierarchical

In object-oriented programming, inheritance is a powerful concept that allows the creation of new classes by extending existing classes. Through inheritance, a derived class (or subclass) inherits the properties and behaviors of a base class (or superclass) while also having the ability to define its own unique features.

There are several types of inheritance in Python, each with its own characteristics and benefits. In this chapter, we will explore four commonly used types of inheritance: single, multiple, multilevel, and hierarchical. Understanding these types is crucial for building effective and maintainable code.

## Single Inheritance

Single inheritance refers to the scenario where a class inherits from a single base class. This type of inheritance allows the derived class to acquire the attributes and methods of the base class, promoting code reuse and modularity.

To better understand single inheritance, let's consider a practical example. Imagine we are building a game that involves different types of vehicles. We can create a base class called `Vehicle`, which defines common attributes and behaviors such as speed and direction. Then, we can create a subclass called `Car` that inherits from `Vehicle` and adds specific features like the number of seats and the presence of airbags.

```python
class Vehicle:
    def __init__(self, speed, direction):
        self.speed = speed
        self.direction = direction
    
    def accelerate(self):
        # code to accelerate the vehicle
        pass
    
    def brake(self):
        # code to brake the vehicle
        pass

class Car(Vehicle):
    def __init__(self, speed, direction, num_seats, airbags):
        super().__init__(speed, direction)
        self.num_seats = num_seats
        self.airbags = airbags
    
    def honk(self):
        # code to honk the car horn
        pass
```

In the example above, the `Car` class inherits from the `Vehicle` class using the `Vehicle` class as the base class. This allows `Car` objects to have all the attributes and methods defined in the `Vehicle` class, which helps reduce code duplication and improve maintainability.

## Multiple Inheritance

Multiple inheritance enables a derived class to inherit from more than one base class. This type of inheritance provides the flexibility to combine the features of multiple classes into a single derived class.

To illustrate multiple inheritance, let's consider a scenario where we are developing a system to manage different types of employees. We can define a base class called `Employee` and subclasses for specific types of employees such as `Developer` and `Manager`. Additionally, we can create a separate class called `Project` that represents a project within the company. By using multiple inheritance, we can define a class called `ProjectManager` that inherits from both `Manager` and `Project`, allowing the project manager to access both managerial functions and project-specific details.

```python
class Employee:
    def __init__(self, name, salary):
        self.name = name
        self.salary = salary
    
    def calculate_pay(self):
        # code to calculate employee's pay
        pass

class Manager(Employee):
    def __init__(self, name, salary, department):
        super().__init__(name, salary)
        self.department = department
    
    def hire_employee(self):
        # code to hire a new employee
        pass

class Project:
    def __init__(self, name, start_date, end_date):
        self.name = name
        self.start_date = start_date
        self.end_date = end_date
    
    def calculate_progress(self):
        # code to calculate project progress
        pass

class ProjectManager(Manager, Project):
    def __init__(self, name, salary, department, project_name, project_start, project_end):
        Manager.__init__(self, name, salary, department)
        Project.__init__(self, project_name, project_start, project_end)
```

In the above example, the `ProjectManager` class inherits from both the `Manager` class and the `Project` class. This allows the project manager to access methods and attributes from both base classes, combining managerial functionality with project-specific behavior.

## Multilevel Inheritance

Multilevel inheritance involves a chain of inheritance, where a derived class inherits from another derived class. This type of inheritance provides the capability to create a hierarchical structure of classes, with each derived class inheriting characteristics from higher-level classes.

To demonstrate multilevel inheritance, let's take an example from the banking domain. We can define a base class called `BankAccount` that represents a generic bank account. On top of that, we can create a derived class called `SavingsAccount` that inherits from `BankAccount` and adds additional features like interest calculation. Furthermore, we can have another derived class called `FixedDepositAccount` that inherits from `SavingsAccount` and adds extra functionality for managing fixed deposit accounts.

```python
class BankAccount:
    def __init__(self, account_number, balance):
        self.account_number = account_number
        self.balance = balance
    
    def deposit(self, amount):
        # code to deposit money
        pass
    
    def withdraw(self, amount):
        # code to withdraw money
        pass

class SavingsAccount(BankAccount):
    def __init__(self, account_number, balance, interest_rate):
        super().__init__(account_number, balance)
        self.interest_rate = interest_rate
    
    def calculate_interest(self):
        # code to calculate interest
        pass

class FixedDepositAccount(SavingsAccount):
    def __init__(self, account_number, balance, interest_rate, duration):
        super().__init__(account_number, balance, interest_rate)
        self.duration = duration
    
    def calculate_maturity_amount(self):
        # code to calculate maturity amount
        pass
```

In the above example, the `SavingsAccount` class inherits from the `BankAccount` class, and the `FixedDepositAccount` class inherits from the `SavingsAccount` class. This creates a hierarchy where both `SavingsAccount` and `FixedDepositAccount` have access to attributes and methods defined in `BankAccount`, allowing for a structured and layered approach to banking-related functionality.

## Hierarchical Inheritance

Hierarchical inheritance involves a base class that serves as the parent for multiple derived classes. In this type of inheritance, each derived class inherits from the same base class, offering the ability to create specialized classes based on common attributes and behaviors.

Let's consider an example where we are developing an application that involves different types of animals. We can define a base class called `Animal` that represents common attributes and behaviors such as species and sound. Then, we can create derived classes such as `Dog`, `Cat`, and `Cow`, each representing a specific animal type and having its own unique features.

```python
class Animal:
    def __init__(self, species, sound):
        self.species = species
        self.sound = sound
    
    def make_sound(self):
        # code to make the animal sound
        pass

class Dog(Animal):
    def __init__(self, species, sound, breed):
        super().__init__(species, sound)
        self.breed = breed
    
    def fetch(self):
        # code to simulate a dog fetching
        pass

class Cat(Animal):
    def __init__(self, species, sound, color):
        super().__init__(species, sound)
        self.color = color
    
    def purr(self):
        # code to simulate a cat purring
        pass

class Cow(Animal):
    def __init__(self, species, sound, milk_production):
        super().__init__(species, sound)
        self.milk_production = milk_production
    
    def eat_grass(self):
        # code to simulate a cow eating grass
        pass
```

In the above example, the `Dog`, `Cat`, and `Cow` classes inherit from the `Animal` class. This enables them to share common attributes and behaviors defined in the `Animal` class while also allowing them to define their own specific features. The hierarchical inheritance provides a structured approach to modeling different animal types in the application.

## Conclusion

Understanding the different types of inheritance in Python is essential for creating well-structured and maintainable code. Single inheritance allows for code reuse and modularity, multiple inheritance combines features from multiple base classes, multilevel inheritance creates a hierarchical structure of derived classes, and hierarchical inheritance enables the creation of specialized classes based on a common base class.

By leveraging the power of inheritance, developers can build complex systems with ease while maintaining code clarity and flexibility. Whether it is creating a game with different types of vehicles, managing employees in an organization, handling various banking accounts, or modeling different animal types, inheritance plays a vital role in everyday coding and fosters the growth of robust and efficient applications.