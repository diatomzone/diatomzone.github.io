---
title: web tips i wish i knew when i started making this site
---

## best practices?

computer stuff is definitely not my expertise. barely knowing what i'm doing in the first place, i found it extra frustrating not knowing the "best" ways to do extremely simple things, like trying to reinvent the wheel when i'm driving a car.

---

## my #1 annoyingest fix: img gap!!!

by default, images have a small gap beneath them because images display as "inline" elements!

this means an image is treated as text and sits on the "baseline" rather than where it should be...

common fixes:

## general

- no spaces in filenames! a general coding "best practice". spaces broke my navbar's highlighting class...
- when testing your site, force reload the page with ctrl + shift + r (or ctrl + f5). this clears the cache and updates things (like stylesheets maybe) that may not update with a regular reload.

## html tags

[semantic elements](https://www.w3schools.com/html/html5_semantic_elements.asp)! use tags that have meaning / are easy to identify, such as <nav> and <footer> instead of plain <div>'s.

div, nav, header etc. are all exactly the same (a plain container), but i find named elements easier to keep track of. i don't need id's for everything either!
