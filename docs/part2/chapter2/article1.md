---
layout: default
title: Functions as First-Class Citizens Pass, Return, Store
parent: Core Functional Constructs in Python
grand_parent: Functional Programming in Python
nav_order: 1
---
# Functions as First-Class Citizens: Pass, Return, Store

In Python, functions are considered **first-class citizens**, which means they can be **passed as arguments**, **returned from other functions**, and **stored in variables**. This powerful feature allows developers to use functions in more flexible and expressive ways.

## Importance of Functions as First-Class Citizens

Having functions as first-class citizens is an important aspect of **functional programming**. It enables developers to write more **modular**, **reusable**, and **composable** code. By treating functions as regular values, we can create higher-order functions, which accept or return other functions. This approach promotes code that is easier to understand and maintain.

### Practical Example: Callback Functions

One practical use case of functions as first-class citizens is the concept of **callback functions**. Imagine you're building a web application that needs to process user data asynchronously. You can define a function to process the data, and then pass it as a callback function to an asynchronous task.

```python
def process_data(data):
    # Code to process data goes here

def asynchronous_task(callback):
    # Code to perform the asynchronous task goes here
    # Once the task is completed, call the callback function
    result = perform_task()
    callback(result)

# Usage
asynchronous_task(callback=process_data)
```

In this example, the `asynchronous_task` function can accept any callback function to be executed when the task is completed. This illustrates how functions as first-class citizens allow for flexible and configurable behavior.

## Pass Functions as Arguments

By passing a function as an argument to another function, we can define **generic behaviors** that can be **customized and extended** by using different functions. These higher-order functions make our code more adaptable and reusable.

### Practical Example: Sorting with Custom Comparison

Suppose you have a list of users that you want to sort based on their ages. However, you also want the flexibility to sort them based on other criteria, such as their names or IDs. By using the `key` parameter of the `sorted` function, you can pass a comparison function as an argument.

```python
def sort_users(users, comparison_function):
    return sorted(users, key=comparison_function)

# Comparison function to sort users based on age
def sort_by_age(user):
    return user['age']

# Comparison function to sort users based on name
def sort_by_name(user):
    return user['name']

# Usage
users = [
    {'name': 'Alice', 'age': 28},
    {'name': 'Bob', 'age': 25},
    {'name': 'Charlie', 'age': 30}
]

sorted_users_by_age = sort_users(users, comparison_function=sort_by_age)
sorted_users_by_name = sort_users(users, comparison_function=sort_by_name)
```

Here, the `sort_users` function accepts a comparison function as an argument. Depending on the provided comparison function, the list of users will be sorted accordingly. This demonstrates how passing functions as arguments enables dynamic and customizable behaviors.

## Return Functions

Not only can we pass functions as arguments, we can also **return functions from other functions**. This allows us to implement **function factories** or create **closures** with encapsulated state.

### Practical Example: Function Factories

A function factory is a function that generates and returns other functions. This can be useful in situations where we need to create similar functions with slight variations.

```python
def exponential_function_factory(power):
    def exponential(x):
        return x ** power
    return exponential

square = exponential_function_factory(2)
cube = exponential_function_factory(3)

# Usage
print(square(2))  # Output: 4
print(cube(2))    # Output: 8
```

In this example, `exponential_function_factory` returns a new function based on the provided power. The returned functions (`square` and `cube`) both have access to the `power` parameter, even after the `exponential_function_factory` has finished executing. This showcases the ability to return functions with encapsulated state.

## Store Functions in Variables

In Python, we can store functions in variables just like any other value. This allows us to **assign functions to variables** and **use them as necessary** throughout our code.

### Practical Example: Decorators

Decorators are a common use case where storing functions in variables is particularly useful. A decorator is a function that modifies the behavior of another function. By storing decorators in variables, we can apply them selectively to specific functions.

```python
def uppercase_decorator(func):
    def wrapper():
        result = func()
        return result.upper()
    return wrapper

def greet():
    return "hello, world!"

# Usage
decorated_greet = uppercase_decorator(greet)
print(decorated_greet())  # Output: "HELLO, WORLD!"
```

In this example, the `greet` function is passed to the `uppercase_decorator`, which returns a modified function named `wrapper`. By assigning the result of applying the decorator to the original function (`greet`) to `decorated_greet`, we can use it to invoke the modified behavior when needed.

## Conclusion

Functions being treated as first-class citizens in Python provides tremendous flexibility to developers. By passing, returning, and storing functions, we can create more flexible, reusable, and expressive code. Whether it's through callbacks, higher-order functions, or function factories, leveraging the power of functions as first-class citizens enhances the functionality and readability of our Python code.