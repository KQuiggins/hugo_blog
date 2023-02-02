---
title: "Login required decorator"
date: 2023-02-02T14:30:21-05:00
draft: false
author: "Kenneth Quiggins"
---

Today I have been working on my Django website on preventing unauthenticated users from accessing other authenticated users profile page.

The first step in acheiving this is to go to your `settings.py` file and at the bottom add the login url. 
```
LOGIN_URL = 'users:login'
```

Next step would be to go to `views.py` and import the `login_required` decorator from Django's auth library which is very powerful and has a ton of useful resources.
```
from django.contrib.auth.decorators import login_required
``` 
Once you have your import statement in place you can add the login_required decorator on the view/route you would like to protect. In my case the it was the profile view.
```
@login_required
def profile(request):
    return render(request, 'users/profile.html')

```
Once all that is in place if a user is not logged in and tries to access a page that has the `login_required` decorator they will be redirected to the login url you specified in the `settings.py` file. Hope this helps.

HAPPY CODING!!!
