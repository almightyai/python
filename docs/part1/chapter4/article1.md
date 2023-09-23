---
layout: default
title: Python Numbers int, float, complex
parent: Built-in Data Types and Operations
grand_parent: Python Foundations
nav_order: 1
---
# Python Numbers: int, float, complex

Python, being a versatile programming language, provides built-in support for various data types, including numbers. Python numbers are essential for performing mathematical operations and are widely used in everyday coding. In this article, we will explore the three types of numbers in Python: `int`, `float`, and `complex`. We will discuss their importance, intricacies, and relevance in real-world coding scenarios.

## Integers (`int`)

Integers, also known as whole numbers, are one of the fundamental data types in Python. They are used to represent positive or negative numbers without any decimal places. Integers play a crucial role in many programming tasks such as counting, indexing, and mathematical calculations.

Let's consider a real-world example to understand the importance of integers in Python. Imagine you are writing a program that calculates the total cost of items in a shopping cart. Each item has a price, and you want to sum up the prices to get the total. In this case, the prices of the items would be represented as integers. Here's an example:

```python
item1_price = 10
item2_price = 15
item3_price = 5

total_cost = item1_price + item2_price + item3_price
print("Total cost:", total_cost)
```

Output:
```
Total cost: 30
```

In the above example, we used integers (`10`, `15`, `5`) to represent the prices of items. By performing addition using the `+` operator, we obtained the total cost (`30`).

## Floating-Point Numbers (`float`)

Floating-point numbers, commonly known as floats, are used to represent numbers with decimal places in Python. Floats provide a way to work with fractional values and perform precise calculations involving real numbers.

Consider a scenario where you need to calculate the average of a series of numbers. In this case, the numbers can't always be represented as whole integers; they might have decimal parts. To calculate the average, you would need to use floating-point numbers. Let's see an example:

```python
num1 = 4.5
num2 = 3.2
num3 = 6.7

average = (num1 + num2 + num3) / 3
print("Average:", average)
```

Output:
```
Average: 4.8
```

In the above example, we used floats (`4.5`, `3.2`, `6.7`) to represent the numbers. By dividing the sum of the numbers by the count (`3`), we obtained the average (`4.8`).

## Complex Numbers (`complex`)

Complex numbers are used to represent quantities that involve both a real part and an imaginary part. In Python, complex numbers are written in the form `a + bj`, where `a` represents the real part and `b` represents the imaginary part.

Complex numbers find applications in a variety of domains, such as signal processing, physics, and engineering. Let's consider a simplified example of modeling an electrical circuit with complex impedances. Each component in the circuit can have a resistance (`R`) and a reactance (`X`). We can represent the impedance of a component using a complex number. Here's an example:

```python
R1 = 10
X1 = 4j
Z1 = R1 + X1

print("Impedance of component 1:", Z1)

R2 = 5
X2 = -2j
Z2 = R2 + X2

print("Impedance of component 2:", Z2)

total_impedance = Z1 + Z2
print("Total impedance:", total_impedance)
```

Output:
```
Impedance of component 1: (10+4j)
Impedance of component 2: (5-2j)
Total impedance: (15+2j)
```

In the above example, we used complex numbers to represent the impedances of two components (`Z1` and `Z2`). By performing addition using the `+` operator, we obtained the total impedance (`(15+2j)`).

---

In conclusion, Python provides three types of numbers: `int`, `float`, and `complex`. Integers are used for whole numbers, floats for numbers with decimal places, and complex numbers for quantities with real and imaginary parts. Understanding and utilizing these number types is essential for various real-world coding scenarios, such as calculations, data analysis, and simulations. By using practical examples, we have explored the importance, intricacies, and relevance of Python numbers in everyday coding. Now that we have a solid foundation, we can proceed further in our journey to mastering Python.