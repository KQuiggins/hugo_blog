---
title: "Vue Music Player"
date: 2022-12-29T12:17:37-05:00
draft: false
author: "Kenneth Quiggins"
---

Today I learned how to initialize firebase first in my Vue.js music player app to ensure a user is logged in before they have access to their data. First we need to destructure the firebase import statement to be able to grab the auth object which has an event attached to it that we can listen for:

```
import { auth } from "./includes/firebase";

```
Using the auth object we attach it to the auhStateChanged method which takes one argument that is a callback function that will fire when the state of the user changes. First we need to declare app outside of the callback function so we can use it inside of the callback function. Then we check to see if app is undefined, if it is we create the app and mount it to the DOM. If it is not undefined we do nothing. This ensures that the app is only created once and not every time the state of the user changes. This is just the first step of what I am trying to accomplish, next I will figure out how to persist the data and write a blog post about it.
```
let app;

auth.onAuthStateChanged(() => {
  if (!app) {
    app = createApp(App);

    app.use(createPinia());
    app.use(router);
    app.use(VeeValidatePlugin);

    app.mount("#app");
  }
});

```
Happy Coding!!!

