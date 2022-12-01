---
title: "Javascript DOM Manipulation"
date: 2022-12-01T15:27:28-05:00
draft: false
author: "Kenneth Quiggins"
---

I have been working with JavaScript and learning how to manipulate the DOM. 
I wanted to write about something I have learned recently that I thought was useful.
If you have an index.html file with a div element with an id of scrollable like this:
```
<div id="scrollable">
        <p>This is some content that is long</p>
        <p>This is some content that is long</p>
        <p>This is some content that is long</p>
        <p>This is some content that is long</p>
        <p>This is some content that is long</p>
        <p>This is some content that is long</p>
        <p>This is some content that is long</p>
        <p>This is some content that is long</p>
    </div>

```
In your styles.css file you can make it have a scroll bar so you can scroll through items by having your overflow set to hidden like this:

```
#scrollable{
    position: relative;
    width: 600px;
  height: 100px;
  overflow-x: hidden;
  overflow-y: auto;
  text-align: center;
  padding: 20px;
  border: 3px solid black;
  background-color: aliceblue;
}

```
If you need to have the scrollbar automatically scroll to a certain item you can create a constant and get your element by id then use the scrollTo method on the constant. Here is one implementation of this method in my main.js file:
```
const scrollable = document.getElementById('scrollable');

scrollable.scrollTo({
    top: scrollable.querySelectorAll('p')[2].offsetTop,
    behavior: 'smooth'
});

```
Thank you for reading. Happy Coding!!
