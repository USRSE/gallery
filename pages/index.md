---
subtitle: US-RSE Gallery
layout: gallery-home
permalink: /
gallery: true
full_width: true
---

{% comment %}We want data folders sorted by name (e.g., year){% endcomment %}
{% capture galleries %}{% endcapture %}{% for data in site.data %}{% if data[0] == "gallery" %}{% for gallery in data[1] %}{% assign gallery_name = gallery[0] %}{% capture galleries %}{{ galleries }},{{ gallery_name }}{% endcapture %}{% endfor %}{% endif %}{% endfor %}
{% assign galleries = galleries | split: "," | sort | reverse %}
<div class="container">
{% comment %}This section loops through data files, and then uses the first data file in the datayaml as the gallery cover.{% endcomment %}
{% for gallery_name in galleries %}{% assign gallery_dir = '/assets/gallery/' + gallery_name %}{% assign data = site.data.gallery[gallery_name] %}{% for photo in data.photos %}{% if forloop.first %}<div class="gallery-container w-3 h-2">
  <div class="gallery-item">
    <a href="{{ site.baseurl }}/{{ gallery_name }}"><div class="image">
      <img src="{{ site.baseurl }}/assets/gallery/{{ gallery_name }}/{{ photo[0] }}" alt="{{ gallery_name }}">
    </div>
    <div class="text">{{ gallery_name | capitalize }}</div></a>
  </div>
</div>{% endif %}{% endfor %}{% endfor %}
</div>

