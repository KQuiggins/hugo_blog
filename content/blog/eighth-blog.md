---
title: "Docker Database Migrations"
date: 2022-08-05T08:27:51-04:00
draft: false
author: "Kenneth Quiggins"
---

After finishing my docker-compose file to connect MySQL database to the flask app I ran into another problem with creating the database tables, I thought this would be a straight forward thing to do and apparently it is not from all the research I have done on the issue so far. I will continue to document everything I try, what works and what does not, hopefully it will help someone with similar issues. I have worked on a Django project with a setup similar to this with a database that needed migrations to be made to the database so I am thinking that will be a good place to go back and look how it is setup.

[]: # Language: markdown
[]: # Path: content/blog/ninth-blog.md
[]: # Compare this snippet from content/blog/fourth-blog.md:
[]: # ---
[]: # title: "Linked List"
[]: # date: 2022-07-29T20:40:55-04:00
[]: # draft: false
