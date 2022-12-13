---
title: "Django Forms"
date: 2022-12-13T15:53:06-05:00
draft: false
author: "Kenneth Quiggins"
---

I have been working on a Django e-commerce site for awhile now, so I thought I would share something from that project.

Django makes creating forms really easy and comes with a forms class you can inherit from and create the fields you need really easy.

First you need to import the form you want and import forms. So you will have something similiar to this. Here I am importing a UserCreationForm for signing up a new User.
This will be in a forms.py file
```
from django.contrib.auth.forms import UserCreationForm
from django.contrib.auth.models import User
from django import forms
```
Then you will create a class such as NewUserForm as I do here, and inherit from the form class you want to create
```
class NewUserForm(UserCreationForm):
```
After that you will add the input fields you want to add to your form.
```
class NewUserForm(UserCreationForm):
    email = forms.EmailField(required=True)
    username = forms.CharField(required=True)
    password1 = forms.CharField(required=True)
    password2 = forms.CharField(required=True)
```

You can also add an optional meta class to your NewUserForm class as a way to specify some standard options as how you class should behave.

```
class NewUserForm(UserCreationForm):
    email = forms.EmailField(required=True)
    username = forms.CharField(required=True)
    password1 = forms.CharField(required=True)
    password2 = forms.CharField(required=True)

    class Meta:
        model = User
        fields = ("username", "email", "password1", "password2")
```

Your basic form structure is set up now. The next steps would be to setup a view for your form so you can get it to render on your page properly but I will leave that for another post.
Happy Coding!!!

