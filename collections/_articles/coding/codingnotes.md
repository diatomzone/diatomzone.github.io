---
title: shiny coding notes
---

{% raw %} <!-- prevents liquid code from being read -->

parts of my notes that are general and readable enough to be of use 😌

## stylin' with css

### compare and contrast

- class vs. id
  - an element can have multiple classes and classes can appear many times per page, while id's are exclusive and can only appear once per page
- padding vs. margin
  - padding = inside element, margin = outside element
  - adjacent paddings will stack (5px + 5px = 10px), while adjacent VERTICAL margins will overlap (5px + 5px = 5px)

### mechanics

- order when there are multiple values
  - 2: topbottom rightleft
  - 3: top rightleft bottom
  - 4: top right bottom left (clockwise)

- css selectors [(more info)](https://www.w3schools.com/cssref/css_selectors.php)
  - `a:link:not(.current)` selects elements besides those with the "current" class
  - `:last-child` selects last child of parent (ex: last p in body)
  - `:not(:last-child)` selects every element besides last child

- centering
  - margin: auto; affects container (block elements)
  - text-align: center; affects children of container (text/inline/inline-block elements)

- turning elements into links
  - put link inside desired element for proper styling, not the other way around. ex: `<h1><a href="/home.html">enter</a></h1>`


### display: the most important css property for layout

- inline: default, height/width values do not apply
- inline-block: inline, but height/width values do apply
- block: starts on new line, takes up full width (can use margin:auto; to center)
- none: element will be completely removed (maybe more popular than width:0px;)
- inherit: inherits display property from parent


### position

choose value then move with top/right/bottom/left properties

1. static: default, not affected by properties, normal page flow (won't overlap)
2. relative: can be moved relative to its normal position
3. fixed: relative to viewport, doesn't move when scrolled
4. absolute: can be moved relative to its containing box, outside normal page flow
5. sticky: toggles between relative and fixed depending on scroll position


- an element's "containing block" (ex: for width % value) is the first parent element with position relative/absolute, and if there are none then <body>

### font size units

- font size: em is a relative unit that allows users to resize text in browser menu
  - 1em = current font size, browser default is 16px
  - w3schools rec: set default size (100%) in body and use em to change other elements

- % vs em: % resizes with window width, em resizes with page zoom
- z-index: element stacking order, higher # is in front

### responsive styles

- `@media screen and (max-width: 700px) {}`: the contained styles will apply when screen width <= 700px
- can also load separate stylesheets in <head>:
  - `<link rel="stylesheet" media="screen and (min-device-width: 700px)" href="css/narrow.css"/>`
  - `<link rel="stylesheet" media="screen and (min-width: 701px) and (max-width: 900px)" href="css/medium.css"/>`
  - `<link rel="stylesheet" media="screen and (max-device-width: 901px)" href="css/wide.css"/>`

### fun effects

- shadows
  - text-shadow for text (text-shadow: 3px 3px 3px black;), box-shadow for elements
  - filter: drop-shadow(1px 1px 1px orange)
- outline = inside element, border = outside element (and more properites such as round corners and specific sides)

---

## html: the building blocks of the website

### anchor link: jump to anchor on same page
- `<a href="#anchor-name">jump to anchor</a>` jumps to element with `id="anchor-name"`
- to externally link to an anchor, add the #anchor-name directly to the end of the page's url (no /)

### iframe: embed webpage inside a webpage

- include title="description" for screen readers
- can open page links inside iframe, link target attribute must refer to iframe name
- use allow="fullscreen", allowfullscreen is outdated/legacy
- embed youtube videos: add video id to embed-type url
  - `<div class="iframecontainer"><iframe src="https://www.youtube.com/embed/6plVf2T6AOo?start=72" title="in the house like carpet" allow="fullscreen"></iframe></div>`

### non-youtube video

- video and audio tags do not support "title" descriptions like iframes do
  - `<video controls><source src="https://va.media.tumblr.com/tumblr_r9pc62fPSM1wrmzr9_720.mp4" type="video/mp4">(audio player not supported)</video>`

### audio
- `<audio controls><source src="/assets/audio/sfx-selectjingle.wav" type="audio/mpeg">(audio player not supported)</audio>`

{% endraw %}
