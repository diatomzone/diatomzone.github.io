---
title: image harvest

gallery:
  kamen-rider-den-o:
    - filename: bubblemomo.gif
      description: momotaros kamen rider den-o
    - filename: bubbleura.gif
      description: urataros kamen rider den-o
    - filename: bubbleryuu.gif
      description: ryuutaros kamen rider den-o
    - filename: bubbledeneb.gif
      description: deneb kamen rider den-o
  kamen-rider:
    - filename: riderpixels1.gif
      description: showa kamen riders
    - filename: riderpixels2.gif
      description: heisei kamen riders
    - filename: kivas.gif
      description: kamen rider kiva
  smash-brawl:
    - filename: assist.png
      description: assist trophy
    - filename: cd.png
      description: music cd
    - filename: exclamation.png
      description: red exclamation point
    - filename: save.png
      description: save icon
    - filename: stage.png
      description: stage icon
  pixel-sprites:
    - filename: astro0b.gif
      description: red astronaut
    - filename: beach0a.gif
      description: palm tree sky
    - filename: brolly1a.gif
      description: rainbow umbrella
    - filename: bug001.gif
      description: red beetle
    - filename: city1a.gif
      description: night cityscape
    - filename: clothe0b.gif
      description: hat and sunglasses
    - filename: dino0a.gif
      description: green t-rex
    - filename: dog1e.gif
      description: running dog
    - filename: dragon0d.gif
      description: green dragon
    - filename: grape0a.gif
      description: purple grapes
    - filename: home05.gif
      description: red house
    - filename: mail14.gif
      description: enveloped letter
    - filename: mount3b.gif
      description: mountain view
    - filename: phone001.gif
      description: grey phone
    - filename: phone1f.gif
      description: yellow phone
    - filename: plane2b.gif
      description: blue plane
    - filename: icondep2.gif
      description: "'I got my Graphics at The Icon Depot' banner"
  uncategorized:
    - filename: floorpunch.gif
      description: figure punching the floor
    - filename: bunnybounce.gif
      description: bouncing bunny
    - filename: eatingchips.gif
      description: cat munching chips
    - filename: eyebrows.png
      description: puppy with drawn-on eyebrows

---

not created by me!

{% for section in page.gallery %} <!-- open up data -->
  <h2 id="{{ section[0] }}" style="text-align:left;">{{ section[0] }}</h2>
  <div class="centered imagegrow"> <!-- a stripped down "gallery" data setup, without the overlays etc. -->
    {% for image in section[1] %}
      <img src="{{ '/assets/images/' | append: section[0] | append: "/" | append: image.filename | relative_url }}" alt="{{ image.description }}" title="{{ image.description }}">
    {% endfor %}
  </div>
{% endfor %}
