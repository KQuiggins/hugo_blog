---
title: "JavaScript Built-In Functions"
date: 2022-10-18T14:18:09-04:00
draft: false
author: "Kenneth Quiggins"
---

I have been going through a course called Mastering the Coding Interview: Data Structures & Algorithms. I have learned a lot so far through this course. 
One thing I resently learned is, if I have two arrays and want to find out if I have a value from array1 that is the same in array2 I could loop through both arrays like this:
```
const array1 = ['a', 'b', 'c', 'x'];
const array2 = ['z', 'y', 'x'];

function containsCommonItem(arr1, arr2){
    for(let i=0; i < arr1.length; i++){
        for(let j=0; j < arr2.length; j++){
            if(arr1[i] === arr2[j]){
                return true;
            }
        }
    }
    return false;
}

```
But that is not very efficient so I called use a dictionary like this:
```
function containsCommonItem2(arr1, arr2){
    // loop through first array and create object where properties === items in the array.
    let map = {}
    for (let i=0; i < arr1.length; i++){
        if(!map[arr1[i]]){
            const item = arr1[i];
            map[item] = true;
        }
    }
    //console.log(map)
    // loop through second array and check if item in second array exist on created object.
    for (j=0; j <arr2.length; j++){
        if (map[arr2[j]]){
            return true;
        }
    }
    return false
}

```
which is a little more efficient that nested loops. But could just use Javascripts built-in functions and be way more efficient with cleaner code:

```
function containsCommonItem3(arr1, arr2){
    return arr1.some(item => arr2.includes(item))
}

console.log(containsCommonItem3(array1, array2))
```

The built-in functions some() and includes() give me the same output of true or false if "some" of the items "include" the item I am looking for. Today was a great day for learning!

Happy Coding!!

