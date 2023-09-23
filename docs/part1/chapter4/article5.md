---
layout: default
title: Sets Unordered Collections with No Duplicates
parent: Built-in Data Types and Operations
grand_parent: Python Foundations
nav_order: 5
---
# Sets: Unordered Collections with No Duplicates

Sets are a fundamental data type in Python that offer a unique way to store and organize data. Unlike lists or tuples, sets are **unordered** collections that do not allow duplicates. This makes sets a powerful tool when working with unique elements or when efficiently eliminating duplicates from a dataset. In this article, we will explore the importance, intricacies, and relevance of sets in everyday coding.

## Importance of Sets

Sets provide a valuable solution to a common problem in programming – dealing with unique values. Whether you need to find unique elements in a list, eliminate duplicates from a dataset, or perform set operations such as union, intersection, or difference, sets offer a natural and efficient approach.

One practical example of using sets is when working with a large dataset of emails. Suppose you need to extract all unique domain names from a list of email addresses. By converting the list to a set, you can instantly obtain only the unique domains, without having to write complex logic to eliminate duplicates manually.

## Creating Sets

To create a set in Python, you can use curly braces `{}` or the built-in `set()` function. Let's consider an example:

```python
fruit_set = {'apple', 'banana', 'orange'}
```

In this example, we created a set called `fruit_set` containing three fruit names. Notice that sets use curly braces, similar to dictionaries, but without key-value pairs.

Another way to create a set is by passing an iterable (like a list or a tuple) to the `set()` function:

```python
prime_numbers = set([2, 3, 5, 7])
```

Here, we created a set called `prime_numbers`, which contains the first four prime numbers.

## Adding and Removing Elements

Sets offer simple and intuitive methods to add and remove elements.

To add an item to a set, you can use the `add()` method:

```python
fruits = {'apple', 'banana'}
fruits.add('orange')
```

In this example, we added the 'orange' item to the `fruits` set using the `add()` method. Now, the `fruits` set contains three items: 'apple', 'banana', and 'orange'.

To remove an item from a set, you can use the `remove()` method:

```python
fruits.remove('banana')
```

Here, we removed the 'banana' item from the `fruits` set. Now, the `fruits` set only contains 'apple' and 'orange'.

## Set Operations

Sets are not only useful for managing unique elements, but they also provide powerful set operations.

### Union

The union operation combines the elements of two sets into a new set. In Python, you can use the `union()` method or the `|` operator to perform the union operation:

```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}
union_set = set1.union(set2)
```

After executing this code, `union_set` will contain {1, 2, 3, 4, 5}, which includes all the elements from both `set1` and `set2`.

### Intersection

The intersection operation returns the common elements between two sets. In Python, you can use the `intersection()` method or the `&` operator to perform the intersection operation:

```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}
intersection_set = set1.intersection(set2)
```

After executing this code, `intersection_set` will contain {3}, which is the only element present in both `set1` and `set2`.

### Difference

The difference operation returns the elements that are in one set but not in the other. In Python, you can use the `difference()` method or the `-` operator to perform the difference operation:

```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}
difference_set = set1.difference(set2)
```

After executing this code, `difference_set` will contain {1, 2}, which are the elements present in `set1` but not in `set2`.

## Summary

In this article, we explored the importance, intricacies, and relevance of sets in everyday coding. Sets provide an unordered collection with no duplicates, making them useful for managing unique elements and performing set operations. With sets, you can easily find unique values, eliminate duplicates, and perform union, intersection, and difference operations. By using relatable examples, we have demonstrated how sets can be utilized in real-world scenarios and their significance in Python programming. So, make sure to leverage the power of sets in your coding journey!