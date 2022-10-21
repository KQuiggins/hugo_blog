---
title: "JavaScript Program 4"
date: 2022-10-21T15:48:11-04:00
draft: false
author: "Kenneth Quiggins"
---

Today I was able to finish the fourth JavaScript program of the semester.
In this program we had to use DOM manipulation to create a table element to display data on the page. This program used Bootstrap 5 to help with styling the table. I used the `window.onload()` function to ensure everything was loading on the page before any JavaScript was able to run. I have an array of items.
```
var items = [   		
        {item: 'boogie board', cost: 15.99, quantity: 3},   		
        {item: 'shark-tooth necklace', cost: 10.99, quantity: 1},   		
        {item: 'inflatable alligator', cost: 12.99, quantity: 2},   		
        {item: 'flip flops', cost: 16.99, quantity: 1},   		
        {item: 'beach towel', cost: 10.99, quantity: 2},    		
        {item: 'goggles', cost: 8.99, quantity: 2}   	
     ];

```
When the webpage loads you are presented with text that says Items Purchased and a button. Once the button is pressed this triggers the `onclick` function:

```
document.getElementById('showData').onclick = function(){
        var tbl = document.createElement('table')
        tbl.setAttribute('class', 'table');
        var row = tbl.insertRow(-1)
        row.insertCell().innerHTML = "Item"
        row.insertCell().innerHTML = "Cost"
        row.insertCell().innerHTML = "Quantity"
        row.insertCell().innerHTML = "Subtotal"

        for(i=0; i < items.length; i++){
            total = (items[i].cost * items[i].quantity).toFixed(2);
            row = tbl.insertRow(-1)
            row.insertCell().innerHTML = items[i].item;
            row.insertCell().innerHTML = items[i].cost;
            row.insertCell().innerHTML = items[i].quantity;
            row.insertCell().innerHTML = total;
        }

        var display = document.getElementById('tableData');
        display.appendChild(tbl);
     };

```
this function creates the `<table></table>` element, inserts the table head using `insertCell().innerHTML`, loops through the array multiplying the cost and quantity the inserts the data in the correct rows of the table. 
HAPPY CODING!!!


