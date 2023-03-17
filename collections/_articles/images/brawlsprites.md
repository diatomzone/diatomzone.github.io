---
title: smash brawl food sprites
---

transparent food sprites from super smash bros. brawl!

free to use from [the spriters resource](https://www.spriters-resource.com/wii/ssbb/sheet/29509/), i just chopped 'em up. (hovertext names from [smash wiki](https://www.ssbwiki.com/Food))

<div class="centered">
    {% for image in site.static_files %}
      {% if image.path contains 'assets/images/brawl/food' %}
        {% if image.name != 'food.png' %}
          <img src="{{ image.path }}" alt="{{ image.basename }}" title="{{ image.basename }}">
        {% endif %}
      {% endif %}
    {% endfor %}
</div>
