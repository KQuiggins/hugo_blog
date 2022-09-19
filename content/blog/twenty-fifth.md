---
title: "JavaScript map() function"
date: 2022-09-19T19:05:18-04:00
draft: false
author: "Kenneth Quiggins"
---

Today I learned about the JavaScript map() function. The map function is an important concept to learn if you want to master JavaScript. The map function works by mapping all elements in an array to a callback function an returns the results in an array. Here is an example of the map function:
```
    const numbers = [1, 2, 3, 4, 5];
    const doubled = numbers.map(x => x * 2);
    console.log(doubled);
    // returns [2, 4, 6, 8, 10]

```

