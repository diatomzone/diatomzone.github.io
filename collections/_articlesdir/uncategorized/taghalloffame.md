---
title: art tags hall of fame
imgheight: 2em

---

some of the humerus-est non-specific{{site.data.foot.t1}} tags people have left on my art HEHEHFJG

text in hovertext!

<div class="photogallery dimmed">
    {%- for image in site.static_files -%}
      {%- if image.path contains 'assets/images/tags' -%}
        <p>
          <img src="{{ image.path }}" alt="{{ image.basename }}" title="{{ image.basename }}">
        </p>
      {%- endif -%}
    {%- endfor -%}
</div>

---

- {{site.data.foot.b1}} not including equally-treasured specific or wholesome tags cus i'd get embarrassed dislaying nice things HRGH thank you very much everyone!! :'^)
