---
title: "Protecting passwords in a repository"
date: 2022-09-24T11:47:57-04:00
draft: false
author: "Kenneth Quiggins"
---

Today I finished watching a tutorial on php and learned how to setup a database and server with xampp. I had to figure out on my own how to change ports on the database because port 3306 was already in use.
I was able to go into the config file and make my changes and successfully connect to the database. I was also able to take the advice of my mentor and create a .env file and add it to the .gitignore file then create variables for my database username & password. After that I used `<?php include 'config/.env' ?>` at the top of my database file and plugged my variables in the connection string. 

