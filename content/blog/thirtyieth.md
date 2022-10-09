---
title: "Exception Handling in C#"
date: 2022-10-08T08:27:59-04:00
draft: false
author: "Kenneth Quiggins"
---

I have been super busy with my classes in school lately, so it has been awhile since I have been able to write in my blog. Some things that I have been stuck on is how to write the logic for handling exceptions in my C# program. I have a Swimming Temperature program that has a `SwimmingWaterTemperature` class.
In the class there is a `public static bool CheckComfort(int temp)` method that takes the `int` sent from user input and checks the temperature (returns true or false). If the temp is between 70 and 85 the temperature is comfortable for swimming. If the temp is not between 32 and 212, it is invalid and the method should throw an `ArgumentException`. I can get the lab at school to pass 8.8/10.0, but for some reason I can no get the lab to accept the way I handle the exception. I will post my solution after I figure it out.

