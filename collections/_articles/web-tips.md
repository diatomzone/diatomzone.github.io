---
title: knowledge i wish i knew when i started websiteing
---

coding is sohard

---

### my #1 annoyingest fix: img gap!!!

this haunted me for years {{site.data.emojis.enid}}

by default, images have a small gap beneath them because images display as "inline" elements!

this means an image is treated as text and sits on the "baseline" rather than where it should be...

common fixes:

-

---

## best practices

### general

- no spaces in filenames! a general coding "best practice". spaces broke my navbar's highlighting class...
- when testing your site, force reload the page with ctrl + shift + r (or ctrl + f5). this clears the cache and updates things (like stylesheets maybe) that may not update with a regular reload.

### html tags

[semantic elements](https://www.w3schools.com/html/html5_semantic_elements.asp)! use tags that have meaning / are easy to identify, such as <nav> and <footer> instead of plain <div>'s.

div, nav, header etc. are all exactly the same (a plain container), but i find named elements easier to keep track of. i don't need id's for everything either!

---

## github pages / jekyll

### how to test site locally

1. command prompt: `cd [local project path]`
2. web browser: http://localhost:4000/
3. command prompt: `bundle exec jekyll serve --livereload`

### how to adjust links for a project site (subdirectory)

a github pages "project site" (https://username.github.io/myproject) is a subdirectory of your "user site" (https://username.github.io), which can throw off links for project sites.

a link to `/index.html` in your project site will send you all the way back to the root, rather than the index of your project site.

it would probably be really annoying and bad if i hardcoded the baseurl in every single link, so here's what i did:

1. define your baseurl in `_config.yml`: `baseurl: /myproject`
  - (i also have my site url defined here)
2. use the "relative_url" liquid filter on any link to add your baseurl
  - html: `<a href="{{ '/index.html' | relative_url }}"></a>`
  - html image: `<img src="{{ '/assets/images/dog.png' | relative_url }}" alt="dog">`
  - markdown: `[home]({{ '/index.html' | relative_url }})`
