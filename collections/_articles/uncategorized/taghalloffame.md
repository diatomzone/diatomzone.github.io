---
title: art tags hall of fame
imgheight: 2em

---

some of the humerus-est non-specific<sup>1</sup> tags people have left on my art HEHEHFJG

text in hovertext!

<div class="centered dimmed">
    {% for image in site.static_files %}
      {% if image.path contains 'assets/images/tags' %}
        <img src="{{ image.path }}" alt="{{ image.basename }}" title="{{ image.basename }}" style="max-width:70%;"><br><br>
      {% endif %}
    {% endfor %}
</div>

---

- <sup>1</sup> not including equally-treasured specific or wholesome tags cus i'd get embarrassed dislaying nice things HRGH thank you very much everyone!! :'^)
