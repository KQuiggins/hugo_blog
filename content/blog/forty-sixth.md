---
title: "Depth First Search"
date: 2023-03-07T13:17:00-05:00
draft: false
author: "Kenneth Quiggins"
---

I recently completed a code challenge going over Depth First Search (DFS) algorithm.
I learned a lot from this challenge and the research I done trying to figure out how to solve the problem. Most of the research I done was after trying to solve the algorithm because of the desire to solve the challenge on my own, which I was able to do to my suprise. Here are some things I learned.

Depth First Search (DFS) is a graph traversal algorithm that traverses a graph or a tree by exploring as far as possible along each branch or path before backtracking.

The DFS algorithm starts at a given source node and explores each of its neighbors in depth before moving on to the next node. It keeps track of the visited nodes to ensure that each node is visited only once.

The algorithm follows the following steps:

   1. Start with the source node.
   2. Mark the current node as visited.
   3. Recursively visit all unvisited neighbors of the current node in a depth-first manner.
   4. Backtrack if there are no more unvisited neighbors.

Here is the code and the explanation.
# Explanation of the code

The code is a implementation of a function `nodeDepths` that calculates the sum of the depths of all the nodes in a binary tree. The binary tree is represented using a custom `BinaryTree` class.

```python
def nodeDepths(root):
    sum = 0
    return nodeDepthHelper(root, sum)
```

The nodeDepths function takes in the root of the binary tree and calls the nodeDepthHelper function to calculate the sum of the depths of all the nodes in the binary tree.

```python
def nodeDepthHelper(root, sum, depth=0):
    if root is None:
        return sum
    else:
        sum += depth
        sum = nodeDepthHelper(root.left, sum, depth + 1)
        sum = nodeDepthHelper(root.right, sum, depth + 1)

    return sum
```

The nodeDepthHelper function takes in a node, a sum, and the depth of the node as parameters.

It checks if the node is None. If it is, it returns the sum. If it's not, it adds the depth to the sum, and then recursively calls itself for the left and right children of the node, incrementing the depth by 1 each time.

Finally, the nodeDepthHelper function returns the sum

```python
# This is the class of the input binary tree.
class BinaryTree:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None
```

Hope this helps, Happy Coding!!!
