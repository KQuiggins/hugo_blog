---
title: "Git Submodules"
date: 2022-08-04T16:15:40-04:00
draft: false
author: "Kenneth Quiggins"
---

Today I was able to fix both of my problems I was having. The first one with creating a docker image with my flask app I was able to use a different python image from docker hub that was not labeled with "-alpine", after that the build went successfully. My second issue was not being able to serve my hugo blogs web pages locally, I was able to fix this by going into the themes folder and running "git submodule init" & "git submodule update" which this actually solves two problems for me now I can get to the themes files so I should be able to add some CSS and style some of my pages the way I want to. 

