---
layout: default
title: Dictionaries Hash Maps and Dictionary Methods
parent: Built-in Data Types and Operations
grand_parent: Python Foundations
nav_order: 4
---
# Dictionaries: Hash Maps and Dictionary Methods

In this chapter, we will explore one of the most versatile and powerful data structures in Python - **dictionaries**. Dictionaries, also known as hash maps, store data in a key-value pair format, allowing for quick and efficient retrieval of values based on their corresponding keys. They play an integral role in everyday coding by providing a flexible way to organize, manipulate, and access data.

## Understanding Dictionaries

A dictionary is an unordered collection of elements, where each element consists of a key and a value. The key acts as a unique identifier, similar to an index in a list, allowing direct access to the corresponding value. Unlike other data types such as lists or tuples, dictionaries use hashing algorithms to organize and store their data, which results in faster retrieval times.

Let's understand this with an example:

```python
student = {
    'name': 'John Doe',
    'age': 20,
    'university': 'XYZ University',
    'major': 'Computer Science'
}
```

In the above code snippet, we have created a dictionary called `student` that stores information about a student. The keys are `'name'`, `'age'`, `'university'`, and `'major'`, while the corresponding values are `'John Doe'`, `20`, `'XYZ University'`, and `'Computer Science'` respectively.

Dictionaries can store values of different data types, such as strings, integers, floats, lists, or even other dictionaries. This flexibility allows you to model complex real-world scenarios and store related data together.

## Accessing Dictionary Values

To access a value in a dictionary, you can use the corresponding key enclosed in square brackets or the `get()` method. The former option is more commonly used.

```python
student_name = student['name']
student_age = student.get('age')
```

In the above example, we are retrieving the value of the `'name'` key using both methods. The variable `student_name` will store the value `'John Doe'`, while `student_age` will store the value `20`.

## Modifying and Adding Elements

Dictionaries are mutable, which means you can modify or add elements to them. To modify the value of a key, simply assign a new value to it.

```python
student['age'] = 21
```

In the above code snippet, we are updating the age of the student from `20` to `21`. Similarly, you can add new key-value pairs to a dictionary by assigning a value to a new key.

```python
student['email'] = 'john.doe@example.com'
```

In the above code snippet, we are adding an `'email'` key with the value `'john.doe@example.com'` to the `student` dictionary.

## Removing Elements

To remove elements from a dictionary, you can use the `del` keyword or the `pop()` method. The `del` keyword allows you to remove a specific key-value pair from the dictionary.

```python
del student['major']
```

In the above example, we are removing the `'major'` key-value pair from the `student` dictionary.

The `pop()` method removes the key-value pair and also returns the value associated with the specified key.

```python
email = student.pop('email')
```

In the above code snippet, we are removing the `'email'` key-value pair from the `student` dictionary and storing the removed value in the `email` variable.

## Checking for Key Existence

To check if a key exists in a dictionary, you can use the `in` keyword or the `get()` method. The `in` keyword returns a boolean value indicating whether the key exists or not.

```python
if 'major' in student:
    print("Student has a major.")
```

In the above example, we are checking if the `'major'` key exists in the `student` dictionary. If it does, the message "Student has a major." will be printed.

The `get()` method returns the value associated with the specified key if it exists, and a default value otherwise.

```python
university = student.get('university', 'Unknown')
```

In the above code snippet, we are retrieving the value associated with the `'university'` key. If the key exists, the value will be stored in the `university` variable. Otherwise, the default value `'Unknown'` will be used.

## Summary

Dictionaries are powerful data structures in Python that allow efficient storage, retrieval, and manipulation of data using key-value pairs. Their flexibility and versatility make them an integral part of everyday coding. By understanding the intricacies of dictionaries and familiarity with the available dictionary methods, you'll be well-equipped to leverage their potential in your projects.