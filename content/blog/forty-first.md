---
title: "Vue Signing out"
date: 2023-01-08T17:57:57-05:00
draft: false
author: "Kenneth Quiggins"
---

Continuing with my Vue music player app, I have been working on authentication. This app has firebase firestore on the backend and I am using pinia for maintaining state. I want to write about how I was able to implement logging out in the app.
The first thing I did was use a browser built-in function to refresh the page after a successful login or registration of an account. This makes sure the modal closes and everything is loaded correctly.
`LoginForm.Vue`
```
async login(values) {
      this.login_in_submission = true;
      this.login_show_alert = true;
      this.login_alert_variant = "bg-blue-500";
      this.login_alert_msg = "Please wait! We are logging you in.";

      try {
        await this.authenticate(values);
      } catch (error) {
        this.login_submission = false;
        this.login_alert_variant = "bg-red-500";
        this.login_alert_msg = "Invalid login details.";
        return;
      }
      this.login_alert_variant = "bg-green-500";
      this.login_alert_msg = "You have been logged in successfully.";
      console.log(values);
      window.location.reload();  // <--- This is the line that refreshes the page
    },

```
Then we need to go `Header.Vue` file and add the logout button to the header. We also want to add `v-if="!userSore.userLoggedIn"` to the Nav link so that `Login/register` is visible only when the user is not logged in.
```
<li v-if="!userStore.userLoggedIn">
    <a class="px-2 text-white" href="#" @click prevent="toggleAuthModal">Login / Register</a>
</li>
```
After that we want to add a `v-else` and our `Logout` button to our Navbar that will be visible when the user is logged in.

```
<template v-else>
    <li>
        <a class="px-2 text-white" href="#">Manage</a>
    </li>
    <li>
        <a
        class="px-2 text-white"
        href="#"
        @click.prevent="userStore.signOut"
        >Logout</a
        >
    </li>
</template>
```
The userStore is a pinia store we have in our app for maintaining state and signOut is a firebase function for signing users out of the app. We also need to add a `signOut` function to our `userStore` in `stores/user.js` file. We will add this function to our actions.
```
async signOut() {
      await auth.signOut();

      this.userLoggedIn = false;
    },

```
Hope this helps Happy Coding!!!!

