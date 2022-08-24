---
title: "timer functions"
date: 2022-08-23T20:59:24-04:00
draft: false
author: "Kenneth Quiggins"
---

Today I used python timer module to run `process_time()` on my dictionary api request. I solved the same problem two different ways. One way using an list and the other using a set. I found the set way to be faster. After thinking about why I can see that a set should be faster because it uses hash tables and time shouldn't matter if the set is bigger or smaller. With a list the bigger the list is the longerit will take if you have to search through it.

