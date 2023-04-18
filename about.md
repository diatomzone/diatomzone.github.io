---
title: about

linklists:
  site credits:
    - name: w3schools
      url: https://www.w3schools.com/
      description: everyone's favorite wiki for all things coding! (the only light illuminating this cruel earth)
    - name: w3schools -- responsive iframe
      url: https://www.w3schools.com/howto/howto_css_responsive_iframes.asp
      description:
    - name: sadgrl's flexbox layout tutorial
      url: https://learn.sadgrl.online/building-a-layout-from-start-to-finish/
      description: (i think page is temporarily down?)
    - name: css tricks
      url: https://css-tricks.com/how-to-create-a-skip-to-content-link/
      description: keyboard/screen reader accessible "skip to content" link
    - name: jekyll tutorial
      url: https://jekyllrb.com/docs/step-by-step/01-setup/
      description: made no sense during my first jekyll attempt, i couldn't even figure out how to test my site locally RIP. but after reading through the github tutorial, the combined knowledge from both sources made my second run way smoother!
    - name: github pages jekyll tutorial
      url: https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll
      description: used during my second jekyll attempt. unfortunately scrapped the site because it came with a premade "theme".
    - name: my friend
      url: https://www.youtube.com/watch?v=oZTbnoSFgMU
      description: helped me fix my one of my includes which was broken for no reason
    - name: shrink page margins
      url: https://stackoverflow.com/questions/67858284/how-to-have-one-item-shrink-fully-before-another-starts-to-shrink
      description: buffers disappear before page content is affected
    - name: css gradient
      url: https://cssgradient.io/
      description: an elegant css gradient maker
    - name: styling unordered/ordered list items
      url: https://web.dev/css-marker-pseudo-element/
      description: nested lists were givin' me trouble
    - name: "jekyll: loop through images in folder"
      url: https://stackoverflow.com/questions/17677094/jekyll-for-loop-over-all-images-in-a-folder
      description:

---

## coding moodboard

<div class="centered">
  <img src="{{ '/assets/images/memes/wayne.png' | relative_url }}" alt="wayne from hylics 2 lying facedown on the ground" title="wayne from hylics 2 lying facedown on the ground">
  <img src="{{ '/assets/images/memes/chomp.jpg' | relative_url }}" alt="drawing of someone furiously biting an unbothered person's head" title="drawing of someone furiously biting an unbothered person's head" class="dimmed">
  <img src="{{ '/assets/images/memes/worthit.jpg' | relative_url }}" alt="cursed emoji meme reading 'I don't want to see... BUT I DO. and sometimes... It's worth it'" title="cursed emoji meme reading 'I don't want to see... BUT I DO. and sometimes... It's worth it'">
  <img src="{{ '/assets/images/memes/thumbsup.jpg' | relative_url }}" alt="a crudely-drawn yet smug thumbs-up" title="a crudely-drawn yet smug thumbs-up" class="dimmed">
  <img src="{{ '/assets/images/memes/coding.jpg' | relative_url }}" alt="the 'fuck them kids' meme edited to just say 'fuck them', labeled 'ceo of coding @ me'" title="the 'fuck them kids' meme edited to just say 'fuck them', labeled 'ceo of coding @ me'">
</div>

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
