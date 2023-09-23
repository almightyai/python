---
layout: default
title: ChainMap Linking Multiple Dictionaries
parent: Advanced Data Structures from the collections Module
grand_parent: Deep Dive into Data Structures
nav_order: 4
---
# ChainMap: Linking Multiple Dictionaries

In this chapter, we will explore the `ChainMap` data structure from the `collections` module in Python. `ChainMap` allows us to link multiple dictionaries together to create a single, unified view of all the dictionaries. This can be extremely useful when working with multiple dictionaries and simplifies the process of accessing and updating values.

## Introduction to ChainMap

A `ChainMap` is a class that provides the ability to link multiple dictionaries, acting as a single combined dictionary. It maintains a list of dictionaries and searches for keys in the order they are specified.

Let's start by importing the `ChainMap` class from the `collections` module:

```python
from collections import ChainMap
```

## Creating a ChainMap

To create a `ChainMap`, we simply pass the dictionaries we want to link as arguments to the `ChainMap` constructor.

```python
dict1 = {'apple': 1, 'banana': 2}
dict2 = {'orange': 3, 'pear': 4}
dict3 = {'grape': 5, 'kiwi': 6}

chain_map = ChainMap(dict1, dict2, dict3)
```

In the above example, we have created three dictionaries (`dict1`, `dict2`, `dict3`) and linked them together using `ChainMap`. Now, we can access and modify values in these dictionaries through the `chain_map` object.

## Accessing Values in ChainMap

When we access a key in a `ChainMap`, it searches for the key in each linked dictionary in the order they were passed during the creation. The first dictionary that contains the key will be used to retrieve the value.

```python
print(chain_map['apple'])  # Output: 1
print(chain_map['orange'])  # Output: 3
print(chain_map['grape'])  # Output: 5
```

As shown in the example above, we can access the values from any of the linked dictionaries as if they were all combined into a single dictionary.

## Updating Values in ChainMap

The `ChainMap` object maintains a reference to the original dictionaries it links. Therefore, any changes made to the dictionaries will be reflected in the `ChainMap`.

```python
dict1['apple'] = 10
dict2['orange'] = 30
dict3['grape'] = 50

print(chain_map['apple'])  # Output: 10
print(chain_map['orange'])  # Output: 30
print(chain_map['grape'])  # Output: 50
```

In the above example, we have updated the values in the original dictionaries (`dict1`, `dict2`, `dict3`). As a result, the values retrieved from the `ChainMap` reflect the updated values.

## Adding and Removing Dictionaries

We can add and remove dictionaries from a `ChainMap` dynamically using the `new_child()` and `maps` attributes, respectively.

```python
dict4 = {'mango': 7, 'pineapple': 8}

chain_map = chain_map.new_child(dict4)

print(chain_map['mango'])  # Output: 7

chain_map.pop()
print(chain_map['mango'])  # Raises KeyError
```

In the above example, we first add `dict4` to the `ChainMap` using `new_child()`, and then we remove the last dictionary using `pop()`. After removing `dict4`, trying to access its keys in the `ChainMap` will raise a `KeyError`.

## Practical Applications of ChainMap

Now that we have a good understanding of `ChainMap`, let's explore some practical examples where it can be useful.

1. **Default Configurations**: `ChainMap` can be used to store default configurations for an application, with the ability to override those defaults with user-specific configurations.

2. **Contextual Variables**: When working with a series of nested functions or contexts, `ChainMap` can help pass variables and configurations through the stack without explicitly passing them as arguments.

3. **Configuration Layers**: In a complex system with multiple configuration layers (e.g., global, group, user), `ChainMap` can simplify the process of accessing and updating configuration values.

4. **Fallback Values**: `ChainMap` can be used to specify a hierarchy of dictionaries from which fallback values can be retrieved when a key is not found in the previous dictionaries.

## Conclusion

`ChainMap` is a powerful tool for linking multiple dictionaries together, providing a single unified view of all linked dictionaries. It simplifies the process of accessing and updating values, making it a valuable asset for everyday coding tasks. By leveraging `ChainMap`, developers can streamline their code, improve readability, and create more maintainable applications.