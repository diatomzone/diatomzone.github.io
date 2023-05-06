---
title: "check it out: my website's specil features!"
---

i am extremely particular about my webpage preferences.

([credits](/about.html#site credits) for some of these, and [elaborations](webtips.html#main) on some others!)

## zestiest features

- when resizing the browser, page content will not shrink until margins disappear
- no extra space at the top or bottom of containers -- elements run flush with padding<sup>1</sup>

## functional features

- responsive layout: elements resize and reorder for narrow browsers/mobile
- additional navigation at bottom of page
- larger font size and dark background because my eye balls
- hidden "skip to content" button for keyboard users/screen readers (at top of page, press TAB then ENTER)

## bonus features

- "discord emojis" stored as variables, called with {%raw%}`{{site.data.emojis.emojiname}}`{%endraw%}
  - emoji height matches line height so they don't throw off spacing
- image alt text in hovertext
- `.dimmed` class for dimming white images
- spoiler text capabilities (hover to reveal) <span class="spoilered">a three minute egg...</span>
- iframes (ex: youtube embeds) maintain 16:9 aspect ratio
- lightweight: external videos, no large image files, etc.
- custom cursor and handwritten font
- no javascript (yet)
- various elements printed using LIQUID functions and YAML data (ex: wiki infobox content, lists of links/descriptions)

## specific spacings

- custom unordered/ordered list markers (aka bullets) so list items are the same height<sup>2 3</sup>

<div class="flex flexcentered">
<div class="directory" style="display:flex; flex-shrink:0;"> <!-- if the contained divs are indented, they somehow turn into code blocks -->
<div markdown="1" style="padding:0 0.5em;">
  - ITEM
  - ITEM
  - ITEM
  - ITEM
</div>
<div markdown="1" style="padding:0 0.5em;">
  1. ITEM
  1. ITEM
  1. ITEM
  1. ITEM  
</div>
</div>
<p style="padding:0 1em;">custom vs. default</p>
<div class="directory" style="display:flex; flex-shrink:0;"> <!-- if the contained divs are indented, they somehow turn into code blocks -->
<div style="padding:0 0.5em;">
  <ul class="listdefault">
    <li>ITEM</li>
    <li>ITEM</li>
    <li>ITEM</li>
    <li>ITEM</li>
  </ul>
</div>
<div style="padding:0 0.5em;">
  <ol class="listdefault">
    <li>ITEM</li>
    <li>ITEM</li>
    <li>ITEM</li>
    <li>ITEM</li>
  </ol>
</div>
</div>
</div>

- custom superscript<sup>(wow!)</sup> styling (none, custom, default)

<div class="flex flexcentered">
<div class="directory" style="display:flex; flex-shrink:0;"> <!-- if the contained divs are indented, they somehow turn into code blocks -->
<div markdown="1" style="padding:0 0.5em;">
  - NO
  - NO
  - NO
  - NO
</div>
<div markdown="1" style="padding:0 0.5em;">
  - CS<sup>#</sup>
  - CS<sup>#</sup>
  - CS<sup>#</sup>
  - CS<sup>#</sup>
</div>
<div markdown="1" style="padding:0 0.5em;">
  - DF<sup style="vertical-align:super; position:static;">#</sup>
  - DF<sup style="vertical-align:super; position:static;">#</sup>
  - DF<sup style="vertical-align:super; position:static;">#</sup>
  - DF<sup style="vertical-align:super; position:static;">#</sup>
</div>
</div>
</div>

---

- <sup>1</sup> SPACING IS MY #1 GRIPE EVER DEATH AND DESTRUCTION {{site.data.emojis.explosion}}
- <sup>2</sup> WHY ARE THEY DIFFERENT {{site.data.emojis.ungalo}}
- <sup>3</sup> EDIT: apparently default works perfectly fine on chrome and mobile firefox FIREFOX HOW COULD YOU DO THIS TO MEEEEEEE
