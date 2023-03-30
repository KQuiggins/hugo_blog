---
title: "Minimum Waiting Time"
date: 2023-03-30T11:12:05-04:00
draft: false
author: "Kenneth Quiggins"
---

# Minimum Waiting Time

You are given a non-empty array of positive intergers representing the amounts of time that specific queries take to execute. Only one query can execute at a time.

A queries waiting time is defined as the amount of time that it must wait before its execution starts. If a query is executed second then its waiting time is the duration of the first query; if a query is executed third then its waiting time is the sum of the durations of the first two queries.

Write a function that returns the minimum amount of total waiting time for all the queries.
hint: (all queries have to wait the duration of the queries that come before it.)

## Understanding the problem

Suppose we have a list of query durations as follows:

```python
queries = [2, 5, 1, 3]

```

We can process these queries in any order we choose. Let's say we process them in the order [1, 2, 3, 5]. Then the total waiting time would be:

```python

(0) + (2) + (2+1) + (2+1+3) = 9

```

However, if we instead process the queries in the order [5, 2, 3, 1], the total waiting time would be:

```python

(0) + (5) + (5+3) + (5+3+2) = 18


```

Clearly, the order in which we process the queries affects the total waiting time. Therefore, we need to come up with a strategy for minimizing the waiting time.

## Solution

One approach to solving this problem is to sort the queries by their duration in ascending order. This way, we process the shortest queries first, which minimizes the waiting time. Here's the Python code to implement this approach:

```python

def minimumWaitingTime(queries):
    queries.sort()
    totalWaitingTime = 0
    for idx, duration in enumerate(queries):
        queriesLeft = len(queries) - (idx + 1)
        totalWaitingTime += duration * queriesLeft
    return totalWaitingTime

```

In this code, we first sort the queries list in place using the sort() method. We then iterate over the sorted list using a for loop. For each query, we calculate the number of queries left to process (queriesLeft) and multiply the query duration by this number to get the waiting time for that query. We then add this waiting time to the totalWaitingTime variable. Finally, we return the totalWaitingTime.

## Testing

```python

>>> minimumWaitingTime([2, 5, 1, 3])
10

```

## Complexity

Time: O(nlog(n)) | Space: O(1)

## Happy Coding!



