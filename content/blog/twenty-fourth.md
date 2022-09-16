---
title: "JavaScript Objects & Prototypes"
date: 2022-09-16T13:45:26-04:00
draft: false
author: "Kenneth Quiggins"
---

Today I learned about JavaScript Objects & Prototypes. For intance if I create an object constructor like this: 

``` 
function Student(firstName, lastName, id, scores){
    *** constructor body goes here ***
}

```
I can create a method and add it to the objects prototype, so any object of that type would be able to use that method like so:
```
Student.prototype.getAverage = function(){
    *** Function body goes here ***
}
```
I really like learning JavaScript, although I know I have just scratched the surface with what the language is capable of. I will keep learning something new everyday and write about what I have learned. Hopefully it will all stick. 