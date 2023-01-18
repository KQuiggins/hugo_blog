---
title: "Naming Routes"
date: 2023-01-17T16:35:18-05:00
draft: false
author: "Kenneth Quiggins"
---

Today I learned about naming routes when using Vue Router. This ability makes it easier to navigate to a route. For example if we have 3 routes like this:

```
const routes = [
  {

    path: "/",
    component: Home,
  },
  {

    path: "/about",
    component: About,
  },
  {

    path: "/manage",
    component: Manage,
  },
];
```
Then your header would look like this:
```
<li>
    <router-link class="px-2 text-white" to="/about">About</router-link>
</li>

<li>
    <router-link class="px-2 text-white" to="/manage">Manage</router-link>
</li>

<li>
    <router-link class="px-2 text-white" to="/home">Home</router-link>
</li>

```
Instead you can name your routes like this:
```
{
    name: "home",
    path: "/",
    component: Home,
  },
```
Then your header would look like this:
```
<li>
    <router-link class="px-2 text-white" :to="{ 'home' }">Home</router-link>
</li>

```
You would do the same for the other routes. This makes your code cleaner and easier to read. By using the name property it allows you the freedom to change the path whenever you want, and keeps you from having to write out a long path name in several places. Hope everyone can see the benefits of naming routes.
Happy Coding!!!
