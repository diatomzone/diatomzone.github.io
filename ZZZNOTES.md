---
title: zzznotes
---

{% raw %} <!-- prevents liquid code from being read -->

## PROJECT INFO
- site new url
  - successfully added site through files alone, didn't need to reinstall command prompt stuff in new directory
  - public repository, as private repository disables github pages
- no posts or production build, just normal and collection pages
- no spaces in filenames (standard practice + breaks navigation highlighting)
- use `relative_url` filter instead of `site.baseurl`, fewer moving parts
  - `{{ "/about.html" | relative_url }}`
  - `[description]({{ '/about.html' | relative_url }})`
  - list of hardcoded /baseurl
    - main.scss custom font import
    - main.scss background-image  

## NEWNOTES: NO BASEURL
- scss
  - retain url in single quotes (in case it needs to be used in YAML, which requires double quotes on the outside)
    - `"src: url('/assets/fonts/fullfont.ttf');"`
- html
  - can remove liquid filter
    - `<link rel="icon" type="image/x-icon" href="/assets/images/favicon-96.png">`

---

## TEST SITE LOCALLY
- cd [project path]
- http://localhost:4000/
- bundle exec jekyll serve --livereload

---

## MARKDOWN
- markdown guide https://itsfoss.com/markdown-guide/
  - with new fix: enter = line break, doublespace enter = double line break, double enter = new paragraph
  - line break: 2 spaces after line + enter
  - new paragraph <p>: enter x2
  - to escape characters that would be used to format markdown (ex: * _ () #) prepend with backslash \
  - link: [about page]({{ '/about.html' | relative_url }})
  - image = link prepended with !
- using html tags in markdown is encouraged https://daringfireball.net/projects/markdown/syntax#html
  - inline can be used anywhere
  - block-level elements (ex: div, table, p) must be at root level and surrounded by a blank line on top and bottom
- <div markdown="1"> My text with **markdown** syntax </div> use this to render text as markdown. seems the whole file has to be md (does not work in default.html), and this lets you put md in containers while following indentation rules and stuff (ex: headings at page base level)
  - this will also mess up contained nested html tags, such as headers inside of links

---

## LINKS: SITE URL / BASE URL
- url vs. baseurl https://mademistakes.com/mastering-jekyll/site-url-baseurl/
  - both are site-wide variables set in config, do not include trailing /'s
  - url: site's full url (https://diatomzone.github.io)
  - baseurl: subdirectory the site is served from (/baseurl), recommended for when you have subdirectories like github project sites
  - page url: everything after base url (/about.html)
- no way to automatically prepend baseurl to all site links...
- links: prepend {{ site.baseurl }} or use {{ "/about.html" | relative_url }} filter
- markdown links: [about page]({{ site.baseurl }}/about.html) or [about page]({{ '/about.html' | relative_url }})
- with baseurl defined in config, localhost now includes baseurl, so i can test links as they would be on github
- 404 page: put permalink: /404.html in front matter
- can't use relative_url or liquid in sass, partial fix: url($relativeurl+"/assets/images/tilesea.png")

---

## HTML / CSS NOTES
- class vs. id: an element can have many classes and can appear many times per page, while id's are exclusive and unique
- padding = inside element, margin = outside element
  - margin: auto; will horizontally center element within container
  - adjacent paddings will stack (5px + 5px = 10px), while adjacent VERTICAL margins will overlap (5px + 5px = 5px)
- value order based on number of values
  - 2: topbottom rightleft
  - 3: top rightleft bottom
  - 4: top right bottom left (clockwise)
- css selectors https://www.w3schools.com/cssref/css_selectors.php
  - a:link:not(.current) {} selects elements besides those with the "current" class
  - :last-child selects last child of parent (ex: last p in body)
  - :not(:last-child) {} selects every element besides last child
- shadows
  - text-shadow for text (text-shadow: 3px 3px 3px black;), box-shadow for elements
  - filter: drop-shadow(1px 1px 1px orange)
- outline = inside element, border = outside element (and more properites such as round corners and specific sides)
- display: the most important css property for layout
  - inline: default, height/width values do not apply
  - inline-block: inline, but height/width values do apply
  - block: starts on new line, takes up full width (can use margin:auto; to center)
  - none: element will be completely removed (maybe more popular than width:0px;)
  - inherit: inherits display property from parent
- position: choose value then move with top/right/bottom/left properties
  1. static: default, not affected by properties, normal page flow (won't overlap)
  2. relative: can be moved relative to its normal position
  3. fixed: relative to viewport, doesn't move when scrolled
  4. absolute: can be moved relative to its containing box, outside normal page flow
  5. sticky: toggles between relative and fixed depending on scroll position
- an element's "containing block" (ex: for width % value) is the first parent element with position relative/absolute, and if there are none then <body>
- font size: em is a relative unit that allows users to resize text in browser menu
  - 1em = current font size, browser default is 16px
  - w3schools rec: set default size (100%) in body and use em to change other elements
- % vs em: % resizes with window width, em resizes with page zoom
- z-index: element stacking order, higher # is in front
- @media screen and (max-width: 700px) {}: styles will apply when screen width <= 700px
  - can also load separate stylesheets in <head>:
  - `normal text lkfjglwrjg lfjsdlfjsdljfdslgjfdlgjfdlg`
  - `<link rel="stylesheet" media="screen and (min-device-width: 700px)" href="css/narrow.css"/>`
  - `<link rel="stylesheet" media="screen and (min-width: 701px) and (max-width: 900px)" href="css/medium.css"/>`
  - `<link rel="stylesheet" media="screen and (max-device-width: 901px)" href="css/wide.css"/>`
- centering
  - margin: auto; affects container (block elements)
  - text-align: center; affects children of container (text/inline/inline-block elements)
- links: put link inside desired element for proper styling, not the other way around. ex: <h1><a href="/home.html">enter</a></h1>
- anchor link: jump to anchor on same page
  - <a href="#anchor-name">jump to anchor</a> -> element with id="anchor-name"
  - to externally link to an anchor, add the #anchor-name directly to the end of the page's url (no /)
- iframe: embed webpage inside a webpage, include title="description" for screen readers
  - can open page links inside iframe, link target attribute must refer to iframe name
  - use allow="fullscreen", allowfullscreen is outdated/legacy
  - embed youtube videos: add video id to embed-type url
    - `<div class="iframecontainer"><iframe src="https://www.youtube.com/embed/6plVf2T6AOo?start=72" title="in the house like carpet" allow="fullscreen"></iframe></div>`
- non-youtube video (video and audio tags do not support title like iframes do)
  - `<video controls><source src="https://va.media.tumblr.com/tumblr_r9pc62fPSM1wrmzr9_720.mp4" type="video/mp4">(audio player not supported)</video>`
- audio
  - `<audio controls><source src="/assets/audio/sfx-selectjingle.wav" type="audio/mpeg">(audio player not supported)</audio>`
- can't change background-image opacity without affecting children, according to article

## ACCESSIBILITY
- `img template: <img src="{{ '/assets/images/explosion.gif' | relative_url }}" alt="explosion gif" title="explosion gif">`
- img alt="alt text" shows image description if image is not viewable, required for image elements
  - null alt attribute: for nonessential/decorative images, use alt="" so screen readers will skip it
- img title="hover text" shows tooltip text on hover
- hidden button at top of page to skip to content is useful for keyboard users/screen readers who want to skip the header/navbar/etc.

---

## DATA LOCATIONS
- /_layouts: stores html page templates that can be used by other files
- /_includes: stores source code (ex: navigation bar) that can be used in other files
- /_data: stores YAML, JSON, and CSV files whose data can be used in other files
- /assets: stores CSS, JS, images, etc. that can be used in other files
  - css/styles.scss: CSS hub, import all scss stylesheets you want to use (can't figure out how to use them separately)
- /_sass: stores SCSS that will be imported into CSS hub styles.scss
- /_coolpages: stores this collection's documents
- /_wikipages: stores this collection's documents
- /_site: stores static site built by jekyll serve
- _config.yml: site settings such as title, collections, global variables, and layout defaults. does not automatically refresh with jekyll serve
- Gemfile: lists site's gems
- Gemfile.lock: locks current gem versions

---

## JEKYLL GLOSSARY
- ruby: the coding language jekyll is written in
- gem: ruby code package that performs specific functions
- jekyll: gem, a static site generator
- Gemfile: lists your site's gems, every jekyll site has one
- liquid: templating language with 3 main components: objects, tags, and filters
  - object: outputs predefined variables as page content, ex: {{ page.title }} displays the page's "title" variable
  - tag: defines logic and control flow, ex: {% if page.show_sidebar %} sidebar content {% endif %}
  - filter: changes the output of an object, ex: {{ "hi" | capitalize }}
- front matter: tells jekyll to process liquid, the YAML code between two ---'s at the start of your page
- front matter variable: defined in front matter, call in liquid with "page" variable, ex: my_num: 5 -> {{ page.my_num }} -> 5
- front matter defaults: config option to automatically add values to files' front matter  
- YAML: common ruby file format, stores data
- layout: html template that wraps around markdown page content, can be used by any page
  - you can call front matter in your layout file, it will use the front matter of the page the layout is called on
- layout inheritance: a layout can be wrapped in another layout
- {{ content }}: object used in layouts, a special variable that returns the rendered content of the page the layout is called on
- {% include name.html %}: tag used in layouts, includes content from files in _includes
  - {% include_relative updates.md %} relative includes calls files in the same directory as current file (or in a subdirectory, but not in a higher directory), does not have to be in _includes. works with normal includes things such as variables.
- sass/scss: css extension used by jekyll, supports variables, nesting, operators, etc.
- sass variable: defined and called with $, ex: $pagewidth: 75%; (different from regular css variables)
- collection: group of documents, similar to a jekyll blog of posts but not organized by date
  - folder starts with underscore, ex: _collectionname
  - must be enabled and can be selected by config defaults
- document: item in a collection

---

## JEKYLL NOTES
- prefix all command prompt commands with "bundle exec" to ensure correct jekyll version
- to use variables, metadata (ex: title), and liquid, add front matter to any markdown or html file (can't be used in scss file, use scss $variables instead)
- global variables: in _config.yml, productname: namehere -> {{site.productname}}
  - remember, you must restart jekyll serve for config changes to work
- include with parameters
  - if the parameter string includes a variable, you must store the entire thing in a new variable before passing it to the include with {% capture ___ %}
  - when something is captured it becomes a variable instead of a string, so you don't need quotation marks when using it inside a liquid tag, ex: includes
- blog posts (not collections) have a built in "excerpt" feature for previews, and a _drafts folder/draft preview feature

---

## YAML NOTES
- easier to read than JSON data and allows comments (they can be used interchangeably)
- 2 types of data, both use indentation (double spaces, do not use tabs) to separate parent and child
  1. yaml map: key/value pairs (a dictionary), can be nested, ex: name: budd
    - mapping node: (recommended) each key has one value and order doesn't matter
    - mapping scalar: (maybe an array of strings?) each key can have multiple values and order matters
    - useful when you want to be able to print the key, not just use the key to return the value
  2. yaml list: a sequence of items, can include maps, ex: groceries: - eggs - milk
    - you can easily call each maps's key to return its value, ex: {{ item.description }}
    - useful when you don't need the heirarchy of a map/when you know the key names
- when iterating through a map, the entire nested map counts as the parent's child, so use [0] [1] accordingly
- escape special characters: surround entire entry with "" or ''
  - for "" surround with '', and vice versa
  - &#58; for colon
  - \u0022 for double quote
  - \u0027 for single quote

---

## SITE PLANNING
- features: click images to enlarge, embedded twines/code bits
- topic menus: school + mobile projects, twine, html/css/js showcase, code templates and cheatsheets, coding resources
  - sort projects by class/type of code? p3, p5js, etc. with short explanations of each
  - embed in iframe
- trying to figure out how to test live on mobile
- landing page before index with flashing/color warning?
- music player, keep player while changing page in iframe https://stackoverflow.com/questions/44778527/keep-playing-audio-when-changing-page
- toggle color theme? certain group of pages with colorful effects theme
- fix code inline/block styling
- reorganize scss, put variables in their own file to include in all stylesheets
- hosted images are medium sized but highly compressed jpgs (10 on firealpaca, perhaps under 20kb)

- SIDEBAR METHODS:
  - HTML: include indexside.html, which is coded in html
    - does not require new styles or layouts
    - a plain div will become as long as the page requires
  - IFRAME: iframe with indexside.html, which is a normal page markdown file and not an includes file
    - requires new styles and layouts (will get messed up by responsive css unless you override with local styles)
    - will only be the size of the iframe container (tried to make a height=100%; sidebar with a de-styled iframe, but it doesn't work because the flex stuff interferes i think)
  - conclusion: iframe sizing is not flexible so i'm going back to old html version for now

- CURRENT TASKS
  - write pages
  - organize zzznotes
  - mystuff category
  - redo landing page and its stylesheet more logically
  - folder order wikipages
  - fix code block styling (change to pre tag?)
  - STOP QUASHING VERBIAGE IN PURSUIT OF DIGESTABILITY

## SITEBUILDING RULES
- margins run from bottom to top, right to left (bottom elements use top margin, right elements use left margin), except for h1 which has a bottom margin
- for spacing reasons:
  - default pages start with h1 (included in default layout, just put title in front matter)
  - plain pages start with h3 or p
  - wikibodies start with h2 or p
  - indexside starts with h3 or p
- listing template reads files in folder, while linklist includes reads data in front matter
  - currently, linklists can only be in a single block, can't separate unless there's a way with a liquid variable
- since the newline renderer doesn't work properly, just use paragraphs (double new line) to separate text
  - coding sites use new paragraphs for everything and margin top as well
- wiki data has 3 layers (all map): data > category > entry
- linklist data has 3 layers (list): linklists > list > entry

---

## DISCOVERIES / PROBLEMS SOLVED
- can't use $sidebarwidth to set content margin-left because the em's are based on different local font sizes, just use px
- sass can nest normal selectors (nav{ ul{} li{} }), same prefix (font:{ family:; size:; }), classes with or without item (.wikibody { .flex{} }), and colons with item (div{ h2:first-child{} })
  - but not colons with no item (div{ :first-child{} })
  - sass file can't include front matter (can't use liquid variables, for background-image relative_url etc.)
- strange gap at top of page was caused by header/paragraph/etc. margins
- when starting css, make sure to include a long page, it catches so many problems
- small gap under img is because img is inline, it's treated as text and sits on baseline
  - common fixes: display block, vertical-align bottom, container line-height 0%
- localhost bugs
  - sometimes command prompt does not auto refresh, ctrl+c or enter to wake it up
  - if css changes are not showing up, ctrl + f5 to force reload, clearing cache and downloading latest version from server
  - (ctrl + shift + r may do same thing)
  - if the above doesn't work, check command prompt for errors
- css class styling showing up in inspector html but not in element css was caused by misplaced css {}'s
- @media queries must go AFTER the styles they change, put at bottom of stylesheet
- !important: will override all previous css styles, but don't use unless absolutely necessary
- footer padding needs to be in div.content, not body (caused footer to be pushed down 1 footerheight)
- can use liquid variables within a for loop using brackets: {% for page in site[page.listcategory] %}
- can combine string and variable within an {{ object }}: `<img src={{ '/assets/images/' | append: page.bioimage | relative_url }}>`
- flex-shrink and flex-grow only work when the size is in px, not % (find another way to make buffers shrink faster than content?)
- to use scss variables in calc() put it in #{}, ex: calc(#{$boxpadding} * 10)
- can't tell the rules of using liquid variables in a string
  - can insert liquid variable directly into string, ex: style="color:{{ item.color }};" (for navbar, data in navigation.yml)
  - couldn't, used this instead: `<img src="{{ '/assets/images/' | append: item.filename | relative_url }}">`
  - i guess the quotes in the first one aren't actually a string? while the second one is appending to a string
- useful css selectors: :first-of-type
- prevent stacking margin/padding/etc
  - use padding only for containers, and use margins for the contained elements
  - don't double up margins. by only using top margins, i prevent the last item from creating extra space at the bottom of the page, and know the topmarginless h1 at the top of every page will neatly absorb the margin of the element beneath it
- YAML data values can't start with ", creates an exception and breaks linklists.html (but can include ")
- how to reference a new "stylesheet": create a new css "hub" in assets and import your desired scss files from _sass. the "hub" will generate a new stylesheet in _site when you build your site, which you can reference in your template's head
- iframe will lose the extra bit of scroll if the page does not have min-height:100%; (not fullscreen)
- list item spacing is slightly different depending on if the link is in a paragraph or not (smaller when in p), due to <p> being display:block; and <a> being display:inline; so i changed "li p" to inline-block (ul and li are block) (edit: removed, see below)
- cannot add margin to <a> or change <p> to something besides display:block;, or else it breaks "skip to content" link and linklist blank entries
- you can include an html file (ex: header.html) anywhere, but you can only include a md file in another md file (ex: updates.md inside home.md) because then the entire thing will be converted to html. kramdown doesn't process html files for md
  - included md files should not have front matter, turns --- into divider
- putting an includes file in a scrollbar div is much more efficient than iframe-ing a whole new page with a simpler layout
- scrollbar box does not add top padding, simply remove margin-top from first child header etc.
- sometimes youtube embeds don't work in localhost, will work fine on normal site
- yaml can't have multiple items with the same key, or else it's overwritten (breaks old dialoguebox lines with repeated speakers), so i remade the system to make names repeatable values instead of keys, with each line being its own item
  - related, containing items don't have to have keys, so you can directly nest them like: - - these - are - items
  - 2 ways to do nested arrays:
    - key/value pairs within a {} array, separated by commas (requres "" for commas and special characters)
    - key value pairs on their own lines (does not require "" for commas, but does for other characters like colon)
  - but in the end, i used a normal [] array, first item = name, second item = text
- when 3 periods are used in a YAML "" string and printed with a liquid variable, they don't turn into ellipses
- css aspect-ratio: 1; can be combined with a defined width/height to create square images, useful for responsive/flex layout where fixed width/height would get messed up
- for loops printing yaml maps: if the for loop is nested normally on separate lines it will print the items in separate p's/lines, but if the for loop is in one line then it will print everything on the same line
- values with multiple quotes will break the containing quotes, so if you're using double quotes, surround with single quotes, and vice versa
- includes won't work if within a html tag's <>
- zzznotes and codingnotes which use raw/endraw tags will bring up warnings about "a Liquid block containing the exceprt separator "\n\n"", which is used in jekyll posts to define excerpt cutoffs, i'm just ignoring it
- markdown nested lists: unordered lists CAN work with just one indent (2 spaces) but ordered lists require 2 indents (4 spaces) as is the norm
- how to separate lists/prevent them from combining: add a line with an empty comment `<!-- -->`
- list default bullet vs. text
  - the heights of bullet markers and text markers are the same, even if the widths are different
  - yet somehow it seems the differently sized bullet throws off the height of the actual list item content
  - so i changed the default bullet to a text "*  " which is 3 monospaced spaces just like "1) "
  - content: "• ";  unicode default bullet U+2022 will work correctly, but having no styling/the real default bullet will throw off the height
- jekyll collection subfolder order (alphabetical) will dictate the order of printed collection items, great for reordering wikilisting items

## PROBLEMS
- markdown newparagraphs are working but newlines not rendering properly, added newline_to_br to content fix https://stackoverflow.com/questions/52762454/jekyll-markdown-with-line-feed-is-not-rendered-in-html
- lastchild selector is broken by {{ newline_to_br }} adding an extra <br> at end of container
  - find a different way to fix markdown rendering?
- removed newline_to_br, new paragraphs work but normal line breaks do not
- markdown links/images don't work inside html tags such as <div>
- 404 will show properly with both url and wrong url but it will crash command prompt
- gallery hovers prevent images from being right clicked/long pressed
- THE GREAT LINKLIST INDENTATION MYSTERY
  - my html is not displaying properly inside a liquid if statement, tried everything including restarting jekyll serve, it breaks and displays everything as code element/an unrendered text p if indented twice or more, it only works when the content inside the if statement is indented once/nonce
  - internet suggestion: "Add markdown="0" attribute to a top-level tag [ex: i trieed it on body in layout template] to disable Markdown parsing." (but it doesn't do anything)
  - tried the above by putting everything in a div
  - thankfully my friend discovered it works if simply contained in a div........ i guess it was misinterpreting the liquid tag/indentation and turned it into code?? the jekyll highlighter rouge or whatever was showing up in f12 too
- can't format code blocks to fit max-width: 100%; only works with with pixel amount or inline
- sidebar iframe is a set height, can't have it adjust automatically
  - aside.indexside flex-start:stretch; will make the aside full height, but the iframe will remain the same size
- tried using nested categories in _wikipages but no luck, seems it only recognizes pages, not subfolders (counts all pages as one group)
- categorynotes
  - .collection = containing collection name, .path = path to document relative to collection's directory (includes subfolders), .name = file's filename, .title = page's front matter title
  - the advantage of a collection is you can iterate through items/use liquid stuff, idk to do that with a regular folder
    - i can do path: "testfolder" (regular folder) and assign values that way, but then you lose the collection capabilities
  - could not figure how to access scope path within _wikipages (tried with _category and plain folder, with multiple variations in config) in order to assign front matter "universe" default value to each page based on folder, so my workaround is to define the categories in a _data file and sort through all _wikipage entry paths that way
- ASSET ORGANIZATION: coollinks page uses default template and manually includes directory and linklists (meant to be flexible and includes are meant to be used in other places as well), meanwhile articles page uses plain collection_listing template (it's a collection), and wikipages page is one of a kind so it uses wikipage-listing template, which contains directory and listings inside itself, and about page includes a linklists

---

## GIT NOTES
- how to remove commit by force reset https://www.howtogeek.com/devops/how-to-remove-a-commit-from-github/
  - requires downloading git https://git-scm.com/download/win
  - git branch explanation https://git-scm.com/about
  - steps, while in project directory:
    - `git reset --soft HEAD~` to remove latest commit
    - `git push origin main --force` to force push
    - then i commit normally

---

## BONUS NOTES
- if this is your first site, bundle add webrick before testing site locally
- info on filtering collection items https://jekyllrb.com/docs/step-by-step/09-collections/
- filter that allows liquid in front matter https://github.com/gemfarmer/jekyll-liquify
- sass variables https://sass-lang.com/documentation/variables
- sass nesting https://www.w3schools.com/sass/sass_nesting.asp
- sass numerics, ex: random https://www.w3schools.com/sass/sass_functions_numeric.php
- css image gallery https://www.w3schools.com/csS/css_image_gallery.asp
- referenced for footer at bottom of page https://stackoverflow.com/questions/18469262/position-footer-at-bottom-of-page-having-fixed-header
- big page of positioning? https://www.w3.org/TR/CSS2/visuren.html#position-props
- different types of yml data as used in config.yml https://jekyllrb.com/docs/datafiles/
- default css values https://www.w3schools.com/cssref/css_default_values.php4
- block and inline elements https://www.w3schools.com/htmL/html_blocks.asp
- fancy css selectors such as + and > https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors
- yaml array etc. info https://www.w3schools.io/file/yaml-arrays/

{% endraw %}
