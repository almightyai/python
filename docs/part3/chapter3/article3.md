---
layout: default
title: FrozenSets Immutable Counterparts of Sets
parent: Sets Unique and Unordered Collections
grand_parent: Deep Dive into Data Structures
nav_order: 3
---
# FrozenSets: Immutable Counterparts of Sets

In Python, sets are commonly used to store unique and unordered collections of elements. However, there might be situations where you need a set that cannot be modified once created. This is where FrozenSets come in.

## Introduction to FrozenSets

A FrozenSet is an immutable version of a set. Once created, you cannot add, remove, or modify any elements in a FrozenSet. It provides a read-only interface to a set's elements, allowing you to perform operations like union, intersection, difference, and testing for membership. 

## Creating a FrozenSet

To create a FrozenSet, you can pass any iterable object, such as a list or tuple, to the `frozenset()` function. Here's an example:

```python
fruits_list = ['apple', 'banana', 'orange']
fruits_set = set(fruits_list)
fruits_frozen_set = frozenset(fruits_list)
```

In this example, `fruits_set` is a regular set, while `fruits_frozen_set` is a FrozenSet. 

## Immutability and Hashability

One of the key characteristics of FrozenSets is their immutability. This means that once created, you cannot modify the FrozenSet or its elements. This immutability makes FrozenSets hashable, which means they can be used as keys in dictionaries or elements in other sets.

```python
person = {'name': 'John', 'age': 25}
frozen_person_set = frozenset(person)
```

In this example, `frozen_person_set` is created from a dictionary. Since FrozenSets are hashable, it can be used as a key in a dictionary:

```python
data = {frozen_person_set: 'some value'}
```

## Set Operations on FrozenSets

FrozenSets support various set operations, which makes them versatile and useful in practice. Let's explore some examples:

### Intersection

You can find the intersection between two FrozenSets using the `intersection()` or `&` operator:

```python
countries_set = frozenset(['USA', 'Canada', 'Mexico'])
visited_set = frozenset(['USA', 'Mexico'])

common_countries = countries_set.intersection(visited_set)
```

In this example, `common_countries` will contain the FrozenSet `{'USA', 'Mexico'}`.

### Union

To find the union of two FrozenSets, use the `union()` or `|` operator:

```python
fruits_set = frozenset(['apple', 'banana', 'orange'])
more_fruits_set = frozenset(['grapes', 'watermelon'])

all_fruits = fruits_set.union(more_fruits_set)
```

Here, `all_fruits` will be the FrozenSet `{'apple', 'banana', 'orange', 'grapes', 'watermelon'}`.

### Difference

The difference between two FrozenSets can be obtained using the `difference()` or `-` operator:

```python
numbers_set = frozenset([1, 2, 3, 4, 5])
odd_numbers_set = frozenset([1, 3, 5])

even_numbers = numbers_set.difference(odd_numbers_set)
```

In this case, `even_numbers` will be the FrozenSet `{2, 4}`.

## Conclusion

FrozenSets provide a powerful and immutable way to store unique and unordered collections of elements in Python. They are particularly useful when you want to ensure that a set remains unchanged once created. By leveraging FrozenSets, you can write more robust and efficient code while adhering to Python's philosophy of simplicity and readability.