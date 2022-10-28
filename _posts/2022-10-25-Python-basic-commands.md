---
layout: post
title: Python Basic Commands
date: 2022-10-25 9:00:01 --0000
permalink: /posts/python-basic-commands/
---

Table of Contents
* TOC
{:toc}

## List Operations
Sorting elements in a list
```python
prime_numbers = [11, 3, 7, 5, 2]

# sorting the list in ascending order
prime_numbers.sort()

print(prime_numbers)

# Output: [2, 3, 5, 7, 11]
```

Need index in an array
```python
for i, element in enumerate(array):
    print("working with index", i)
    do_something(element)
```