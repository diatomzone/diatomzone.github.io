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
  - padding = inside container, margin = outside container
  - adjacent paddings will stack (5px + 5px = 10px), while adjacent VERTICAL margins will overlap (5px + 5px = 5px)
- % vs. em
  - % sizing resizes with window width, em sizing resizes with page zoom
- outline vs. border
  - outline = inside element, border = outside element (also has more customization like rounded corners and styling specific sides)

### mechanics

- value order when using multiple values (ex: margins)
  - 2: topbottom rightleft
  - 3: top rightleft bottom
  - 4: top right bottom left (clockwise)
- centering
  - `text-align: center;` centers children of container (text/inline/inline-block elements)
  - `margin: auto;` centers the container itself (block elements)
- turning elements into links
  - put link inside desired element for proper styling, not the other way around. ex: `<h1><a href="/home.html">enter</a></h1>`
- z-index: element stacking order, higher # is in front

### some css selectors [(list of selectors)](https://www.w3schools.com/cssref/css_selectors.php)

- `div.centered` selects divs with the "centered" class
- `:not(.centered)` selects every element without the "centered" class
- `:last-child` selects the last element in a parent element (ex: the last p in body)
- `div:nth-child(3)` selects the third div in a parent element
- `span.spoilered:hover` selects spans with the "spoilered" class when hovered over

### size units

- px
  - hardcoded value
  - resizes with page zoom
- %
  - relative to containing block
  - font resizes with page zoom, element resizes with window width
- vw
  - relative to viewport width
  - resizes with window width
- em
  - relative to font size (allows users to resize text in browser menu)
  - resizes with page zoom
    - 1em = current font size, browser default is 16px
    - w3schools rec: set default size (100%) in body and use em to change other elements

### display: the layout mvp

- inline: default, height/width values do not apply
- inline-block: inline, but height/width values do apply
- block: starts on new line, takes up full width (can use margin:auto; to center)
- none: element is completely removed (may be more popular than hiding with width:0px;)
- inherit: inherits display property from parent

### position

1. static: default, not affected by top/right/bottom/left properties, normal page flow (won't overlap things)
2. relative: can be moved relative to its normal position
3. fixed: relative to viewport, doesn't move when scrolled
4. absolute: can be moved relative to its containing box, outside normal page flow (can overlap things)
5. sticky: toggles between relative and fixed depending on scroll position

- some positions are affected by top/right/bottom/left properties
- an element's "containing block" (ex: for setting width %) is the closest parent element with position relative/absolute. if there are none then it will use <body>

### responsive styles

- `@media screen and (max-width: 700px) {}`: the contained styles will apply when screen width <= 700px
- can also load separate stylesheets in <head>:
  - `<link rel="stylesheet" media="screen and (min-device-width: 700px)" href="css/narrow.css"/>`
  - `<link rel="stylesheet" media="screen and (min-width: 701px) and (max-width: 900px)" href="css/medium.css"/>`
  - `<link rel="stylesheet" media="screen and (max-device-width: 901px)" href="css/wide.css"/>`

### fun effects

- shadows
  - text-shadow for text (text-shadow: 3px 3px 3px black;), box-shadow for elements
  - filter: drop-shadow(3px 3px 3px orange);
  - box shadow uses the element's entire (rectangular) box, while drop shadow uses the shape (alpha channel) of the image/text

---

## html: the building blocks of the website

### anchor link: jump to anchor on same page
- `<a href="#anchor-name">jump to anchor</a>` jumps to element with `id="anchor-name"`
- to externally link to an anchor, add the #anchor-name directly to the end of the page's url (no /)

### iframe: embed webpage inside a webpage

- include `title="description"` for screen readers
- can open page links inside iframe, link target attribute must refer to iframe name
- use `allow="fullscreen"`, allowfullscreen is outdated/legacy
- embed youtube videos: add video id to embed-type url
  - `<div class="iframecontainer"><iframe src="https://www.youtube.com/embed/6plVf2T6AOo?start=72" title="in the house like carpet" allow="fullscreen"></iframe></div>`

### non-youtube video

- video and audio tags do not support "title" descriptions like iframes do
  - `<video controls><source src="https://va.media.tumblr.com/tumblr_r9pc62fPSM1wrmzr9_720.mp4" type="video/mp4">(audio player not supported)</video>`

### audio
- `<audio controls><source src="/assets/audio/sfx-selectjingle.wav" type="audio/mpeg">(audio player not supported)</audio>`

{% endraw %}
