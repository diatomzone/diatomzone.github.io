---
title: about
background: rainbow

memelist:
  - filename: wayne.png
    description: "wayne from hylics 2 lying facedown on the ground"
  - filename: chomp.jpg
    description: "drawing of someone furiously biting an unbothered person's head"
    dark: true
  - filename: worthit.jpg
    description: "cursed emoji meme reading 'I don't want to see... BUT I DO. and sometimes... It's worth it'"
    dark: true
  - filename: thumbsup.jpg
    description: "crudely-drawn yet smug thumbs-up"
    dark: true
  - filename: coding.jpg
    description: "the 'fuck them kids' meme edited to just say 'fuck them', labeled 'ceo of coding @ me'"

linklists:
  site credits:
    - name: w3schools
      url: https://www.w3schools.com/
      description: the only light illuminating this cruel earth (everyone's favorite interactive wiki for all things coding!)
    - name: sadgrl's flexbox layout tutorial
      url: https://learn.sadgrl.online/building-a-layout-from-start-to-finish/
      description: (i think the page is temporarily down?)
    - name: jekyll tutorial
      url: https://jekyllrb.com/docs/step-by-step/01-setup/
      description: jekyll is the static site builder that powers github pages! here's the main jekyll tutorial i used -- it made no sense on my first try, though.
    - name: jekyll tutorial -- github pages
      url: https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll
      description: github pages lets you host straight from your repository! here's a tutorial i used on my second try -- unfortunately scrapped the site because it came with a premade "theme".
    - name: neocities
      url: https://neocities.org/
      description: this site's host -- check out the neocities "websites" and "activity" tabs to peruse a wealth of charming personal sites!
    - name: my friend
      url: https://www.youtube.com/watch?v=oZTbnoSFgMU
      description: helped me fix one of my includes which was broken for no reason
    - name: lark and deus
      url: https://www.youtube.com/watch?v=JM5oZ7qNEMk
      description: page testing, quality control, and copyediting B^)
    - name: my pal
      url: https://www.youtube.com/watch?v=xLvHJmzmXb0
      description: page testing, design consultation, and web adventuring companion!
    - name: '"skip to content" button'
      url: https://css-tricks.com/how-to-create-a-skip-to-content-link/
      description: for keyboards/screen readers
    - name: iframe aspect ratio
      url: https://www.w3schools.com/howto/howto_css_responsive_iframes.asp
      description:
    - name: shrinkable page margins
      url: https://stackoverflow.com/questions/67858284/how-to-have-one-item-shrink-fully-before-another-starts-to-shrink
      description: buffers disappear before page content is affected (flex-shrink and flex-grow)
    - name: css gradient maker
      url: https://cssgradient.io/
      description:
    - name: bullet styling
      url: https://web.dev/css-marker-pseudo-element/
      description: nested list items were givin' me trouble
    - name: "jekyll: loop through images in folder"
      url: https://stackoverflow.com/questions/17677094/jekyll-for-loop-over-all-images-in-a-folder
      description:
    - name: texture town
      url: https://textures.neocities.org/
      description: (see coollinks) background images
    - name: noclip
      url: https://noclip.website/
      description: (see coollinks) background images

---

## coding moodboard

<div class="centered">
  {%- for meme in page.memelist -%}
    <img src="/assets/images/memes/{{ meme.filename }}" alt="{{ meme.description }}" title="{{ meme.description }}" style="max-height: 12em;" {% if meme.dark == true %}class="dimmed"{% endif %}>
  {%- endfor -%}
</div><!-- meme.dark breaks if stripped of whitespace, for some reason -->

## this site

my brain is so small and coding is so hard.

and yet,

the endless torment is outweighed by the joy of creation and self-expression.

when i see something i've made from scratch, and what others have made from the love in their hearts, the world is beautiful.

this is what gives me the strength to try.

(countless clueless directionless webpages and two catastrophic jekyll failures have paved the way)

thank you for visiting my very first site that actually works! {{ site.data.emojis.pie }}

---

{% include linklists.html listname="site credits" %}
