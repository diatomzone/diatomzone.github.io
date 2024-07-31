---
title: basic knowledge i wish i knew when i started siteing
---

<div class="directory"> <!-- manual instance of a directory -->
  <h4>skip to:</h4>
  <ul>
      <li><a href="#tip-top-tips">tip top tips</a></li> <!-- entry label, link to anchor -->
      <li><a href="#best-practices">best practices</a></li>
      <li><a href="#spacing-and-layouts">spacing and layouts</a></li>
      <li><a href="#github-pages--jekyll">github pages / jekyll</a></li>
      <li><a href="#ways-of-the-web">ways of the web</a></li>
  </ul>
</div>

## tip top tips

### how to get rid of the gap underneath images!!!

images display as "inline" (inline-block) by default, meaning they sit up on the text "baseline" rather than the bottom of the. wherever they're supposed to be (this haunted me for actual years {{ site.data.emojis.enid }})

my fix: `img { vertical-align: bottom; }`

---

## best practices

### general

- no spaces in filenames
  - a general coding "best practice"! spaces broke my navbar's highlighting class...
- force reload when testing your site
  - force reload the webpage with ctrl + shift + r (or ctrl + f5). this clears the cache and updates things (like stylesheets?) that may not update with a regular reload

### html tags

#### semantic elements [(more info)](https://www.w3schools.com/html/html5_semantic_elements.asp)

use tags that have meaning/are easy to identify, such as `<nav>` and `<footer>`, instead of plain `<div>`'s.

div, nav, footer etc. are all exactly the same (a plain container), but named elements are easier to keep track of. i don't need id's for everything either!

#### nice tag choices

- use new paragraph `<p>` instead of line break `<br>`
  - markdown does this when you double-enter
- use <strong>strong</strong> `<strong>` and <em>emphasis</em> `<em>` instead of <b>bold</b> `<b>` and <i>italic</i> `<i>`
  - they are semantic, work with screen readers, are less likely to confuse mobile styling (ex: bolding already bolded text), and can be styled in your stylesheet

---

## spacing and layouts

### my margin method

to keep vertical spacing simple, consistent, and avoid pointless margin overlap, i style with top margins and set bottom margins to 0.

this means the last element in a container will run flush with the bottom (it won't create an extra gap)!

since i start each page with `<h1>` (and start other containers with a known alternative), i give that first element a top margin of 0 so it will run flush with the top. (i can also give it a bottom margin if needed)

### layouts

flexboxes are great for building a responsive layout! basically, they let you put elements side by side (ex: a sidebar and main body), and you can easily reorganize/reorder elements for narrow screens.

---

## github pages / jekyll

(both are free! 😎)

### how to adjust links for a project site (subdirectory)

a github pages "project site" (https://username.github.io/myproject) is a subdirectory of your "user site" (https://username.github.io), which can throw off links for project sites.

a link to `/index.html` in your project site will send you all the way back to the root, rather than to the index of your project site.

it would likely be really annoying and bad if i hardcoded the baseurl in every single link, so here's what i did:

{% raw %}
1. define your baseurl in `_config.yml`: `baseurl: /myproject`
  - (i also have my site url defined here)
2. use the "relative_url" liquid filter on any link to automatically add your baseurl
  - html: `<a href="{{ '/index.html' | relative_url }}"></a>`
  - html image: `<img src="{{ '/assets/images/dog.png' | relative_url }}" alt="dog">`
  - markdown: `[home]({{ '/index.html' | relative_url }})`
{% endraw %}

now if your baseurl changes, you can easily update it in config!

### jekyll (static site builder) is helpful

jekyll introduces a hundred more moving parts and takes me forever to figure out, but it makes things so much easier in the long run! some featured favorite features:

- write your page layouts/source codes once, then apply 'em anywhere you like
- use LIQUID to harness the essentials of code: variables, for loops, and if statements
- YAML data is very easy to read and edit -- combine it with liquid to efficiently print things onto your page, ex: wiki infobox content!
- write your page content in markdown! jekyll converts it to html
- BONUS: [the jekyll tutorial](https://jekyllrb.com/docs/step-by-step/07-assets/) introduced me to SASS, a CSS extension, which has ultra swag variable and nesting(!!) capabilities

### how to test site locally

once you've [installed everything](https://jekyllrb.com/docs/installation/) and [set up jekyll](https://jekyllrb.com/docs/step-by-step/01-setup/) in your local project directory...

1. command prompt: `cd [local project path]`
2. command prompt: `bundle exec jekyll serve --livereload`
3. web browser: http://localhost:4000/

---

## ways of the web

### no hotlinking

hotlinking: embedding images/media on your site by directly linking them from someone else’s site. considered poor “netiquette” because it uses up the other person's data.

instead, download the image/media and host it on your own site, or use an external host (ex: youtube)!

(i hotlink from my own blog/drafts though cus it's tumblr {{site.data.emojis.zenigata}})
