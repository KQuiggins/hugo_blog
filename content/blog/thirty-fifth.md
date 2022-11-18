---
title: "Vue.js"
date: 2022-11-17T20:52:57-05:00
draft: false
author: "Kenneth Quiggins"
---

Today I finished a program in my JavaScript class using Vue.js.
This program takes data from a database that contains information about speeding tickets that was recorded from a state trooper in the state of New York. This program makes a Ajax request returns the data then displays the data on 2 different pages one page has all the tickets and the other page only has the tickets that are 25 mph or over.

The program is very simple but it was a good introduction to Vue.js. I am looking forward to learning more about Vue.js in the future.

This is my Ajax request:
```
methods: {
       async getTickets() {
            const response = await fetch('tickets1.json');
            this.tickets = await response.json();
            this.filtered = this.tickets.filter((ticket) => ticket.actual_speed - ticket.posted_speed >= 25);
            console.log(this.filtered); 
            
        },
        
    },

```

This is my table using v-for to loop through the data:
```
<table class="table table-bordered table-striped">
                <tr>
                    <th>Ticket ID</th>
                    <th>Time</th>
                    <th>Posted Speed</th>
                    <th>MPH Over</th>
                    <th>Age</th>
                    <th>Sex</th>
                </tr>
                <tr v-for="ticket in tickets">
                    <td>{{ticket.tid}}</td>
                    <td>{{ticket.stop_time}}</td>
                    <td>{{ticket.posted_speed}}</td>
                    <td>{{ticket.actual_speed - ticket.posted_speed}}</td>
                    <td>{{ticket.age}}</td>
                    <td>{{ticket.violator_sex}}</td>
                </tr>
            </table>

```