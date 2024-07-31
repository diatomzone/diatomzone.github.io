---
title: seasonal gifs and images

gallery:
  halloween:
    - filename: gifs/halloween1.gif
      description:
    - filename: gifs/halloween2.gif
      description:

---

collected as time proceeds 😌

(needs hovertext) (i didn't make these)

<div class="centered imagegrow"> <!-- a stripped down "gallery" data setup, without the overlays etc. -->
  {% for section in page.gallery %} <!-- open up data -->
    <h2 id="{{ section[0] }}" style="text-align:left;">{{ section[0] }}</h2><br>
    {% for image in section[1] %}
      <img src="{{ '/assets/images/' | append: image.filename | relative_url }}" alt="{{ image.description }}" title="{{ image.description }}">
    {% endfor %}
  {% endfor %}
</div>
