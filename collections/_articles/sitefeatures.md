---
title: "my website: specil features!"
---

i am extremely particular about my webpage preferences.

## zestiest features

- when resizing the browser, page content will not shrink until margins disappear
- no extra space at top or bottom of containers -- elements run flush with padding (SPACING IS THE #1 GRIPE EVER)
- customized unordered and ordered list markers (bullets) so list items have the same height (WHY ARE THEY DIFFERENT {{site.data.emojis.ungalo}})

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

## functional features

- responsive layout: elements resize and reorder on narrow browsers/mobile
- additional navigation at bottom of page
- hidden "skip to content" button for keyboard users/screen readers (press TAB then ENTER)
- larger font size and dark background because my eyeballs

## bonus features

- image alt text hovertext
- iframes (ex: youtube embeds) maintain 16:9 aspect ratio
- "discord emojis" stored as global variables, called with {%raw%}`{{site.emojis.emojiname}}`{%endraw%}
  - emoji height matches line height so emojis don't throw off spacing
- no javascript (yet)
- lightweight: external videos, no large image files, etc.
- custom cursor and handwritten font
