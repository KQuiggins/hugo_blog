---
title: "Javascript sort function"
date: 2022-08-27T16:37:14-04:00
draft: false
author: "Kenneth Quiggins"
---

Today I learned about the javascript `sort()` function. It really acts weird when sorting an array with numbers that have more than one digit. It only sorts the first digit. For instance `100` would come befor `23`. The way around this behavior is to pass a function to the `sort()` function.
So it would look like this: `val = numbers.sort(function(a, b) { return a - b; });` and it would sort the numbers from lowest to highest. 

