---
title: most influential discord emojis
background: zenigata
emojiheight: 4em

emojilist:
  - filename: enid.png
    description: "enid -- enid from ok ko doing the pensive gorilla munch face"
  - filename: zenigata.png
    description: "zenigata -- zenigata from lupin iii doing a goofy shout"
  - filename: loveimages.png
    description: "loveimages -- the contently smiling dog from the i love images meme"
  - filename: reigen.png
    description: "reigen -- reigen from mob psycho 100 cackling unphotogenically"
  - filename: shannon.png
    description: "shannon -- shannon from ok ko doing the tails gets trolled face"
  - filename: ungalo.png
    description: "ungalo -- ungalo from jojo sweating and screaming in despair"
  - filename: evil.png
    description: "evil -- the face from the driving home/penis comic"

---

here is a collection/safekeeping of the top emojis i wish i could use on every platform
{{ site.data.emojis.zenigata }} {{ site.data.emojis.zenigata }}

names in hovertext!

<div class="centered imagegrow">
  <span class="emoji">
    {% for emoji in page.emojilist %}
      <img src="/assets/images/emojis/{{ emoji.filename }}" style="height:{{ page.emojiheight }};" alt="{{ emoji.description }}" title="{{ emoji.description }}">
    {% endfor %}
  </span>
</div>

<span class="spoilered">honorable mention: komaeda hand sprite</span>
