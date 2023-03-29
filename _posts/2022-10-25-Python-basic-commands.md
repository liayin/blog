---
layout: post
title: Python Basic Commands
date: 2022-10-25 9:00:01 --0000
permalink: /posts/python-basic-commands/
---

Table of Contents
* TOC
{:toc}

## String Operations
Split String by Character
```python
my_string = "Python"
tokens = list(my_string)
print("String tokens are: ", tokens)
```
String tokens are: [‘P’, ‘y’, ‘t’, ‘h’, ‘o’, ‘n’]

## List Operations
Sorting elements in a list
```python
prime_numbers = [11, 3, 7, 5, 2]

# sorting the list in ascending order
prime_numbers.sort()

print(prime_numbers)

# Output: [2, 3, 5, 7, 11]
```

Reversing elements in a list
```python
# create a list of prime numbers
prime_numbers = [2, 3, 5, 7]

# reverse the order of list elements
prime_numbers.reverse()

print('Reversed List:', prime_numbers)

# Output: Reversed List: [7, 5, 3, 2]
```

Need index in an array
```python
for i, element in enumerate(array):
    print("working with index", i)
    do_something(element)
```

## Dictionary operations

How to declare a dictionary ([Reference](https://www.w3schools.com/python/python_dictionaries.asp))
```python
thisdict = {
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}
```
