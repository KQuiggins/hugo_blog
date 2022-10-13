---
title: "Python Fundamentals and Map()"
date: 2022-10-13T19:22:17-04:00
draft: false
author: "Kenneth Quiggins"
---

I have been going back over some of the fundamentals of python data types and also trying to learn more advanced algorithms. Today I focused on the `map()` function. Map takes in 2 arguments like this `map(function, iterables)`. So I could write a function like this:
```
def multiplyByTwo(item):
    
    return item*2

```
And then print the answer out like this:
```
print(list(map(multiplyByTwo, [2, 4, 6])))

```
which returns:

```
[4, 8, 12]

```
This is a very basic example. I hope you can see how powerful this function could be. Ever for this example, because otherwise my function would look something close to this:

```
def multiplyByTwo(li):
    new_list = []
    for item in li:
        new_list.append(item*2)
    return new_list

```
Happy Coding!

