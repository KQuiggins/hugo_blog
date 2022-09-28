---
title: "filter function"
date: 2022-09-27T20:33:58-04:00
draft: false
author: "Kenneth Quiggins"
---

Today I learned about the filter function in JavaScript. This really is a super useful tool to use. Say I have an array of companies.

```
const companies = [
    { name: "Company One", category: "Finance", start: 1981, end: 2003 },
    { name: "Company Two", category: "Retail", start: 1992, end: 2008 },
    { name: "Company Three", category: "Auto", start: 1999, end: 2007 },
    { name: "Company Four", category: "Retail", start: 1989, end: 2010 },
    { name: "Company Five", category: "Technology", start: 2009, end: 2014 },
    { name: "Company Six", category: "Finance", start: 1987, end: 2010 },
    { name: "Company Seven", category: "Auto", start: 1986, end: 1996 },
    { name: "Company Eight", category: "Technology", start: 2011, end: 2016 },
    { name: "Company Nine", category: "Retail", start: 1981, end: 1989 }
];
```
I would like to get all the companies which category is Auto. I could simply write this code using an arrow function and the filter method.

`const autoCompanies = companies.filter(company => company.category === 'Auto');`

Or say I want all the companies that have been in business at least 8 years. I could write this piece of code.

`const lastedEightYears = companies.filter(company => (company.end - company.start) >= 8);`

There are a couple other ways to wite this function but this way is the cleanest and in my opinion the best way to implement this function.

