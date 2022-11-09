---
title: "JavaScript Prototype"
date: 2022-11-08T19:17:12-05:00
draft: false
author: "Kenneth Quiggins"
---

Today I learned about the prototype property in JavaScript.
The prototype property allows you to add functionality or a certain property to an object that will then be added to all other objects of the same type.

If I create a class:
```
class userCreator{
    constructor(name, score){
        this.name = name;
        this.score = score;
    }
    
}
```
I can then add a method to the class like this:
```
userCreator.prototype.increment = function(){
    this.score++;
}
```
Now if I create a new user:
```
const user1 = new userCreator("Kenneth", 5);
```
I can then call the increment method on the user1 object:
```
user1.increment();
```
This will increment the score by 1. This is a very powerful feature of JavaScript. I hope you can see how this could be used to create a lot of functionality. The increment method is now part of the userCreator class's prototype. This means that all objects created from the userCreator class will have access to the increment method. Happy Coding!!!





