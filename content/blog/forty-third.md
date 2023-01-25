---
title: "Django Login Redirect"
date: 2023-01-25T15:16:26-05:00
draft: false
author: "Kenneth Quiggins"
---

Django has built authentication that makes it easy to design and implement logging in and out for your websites. The regular document flow for logging in, after you have designed your login page, would automatically redirect you to 

`/accounts/profile/`

after hitting the submit button. Generally speaking we would want something more to our liking, something like a product page you would see after logging in to a e-commerce site. Django makes accomplishing this fairly straight forward. Head to your `settings.py` file and we will add this code to the bottom.

```
LOGIN_REDIRECT_URL ='myapp:products'
```
Your path would be different from mine but the structure goes like this 

`LOGIN_REDIRECT_URL ='app_name:path'` if you have an app_name specified in your code or you can just use this `LOGIN_REDIRECT_URL ='path_to_url'` really depends on how your code is setup. Either way Django does a good job of making our lives as developers easier and help keep our code clean, which is a win in my book.

Happy Coding!!!!

