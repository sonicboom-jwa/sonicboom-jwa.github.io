---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

exclude: true	
layout: default
title: Sonic Boom raid strats
---

Apex raids:
<ul>
  {% comment %}
    Get all "photo_set" pages and display a list with links to them.
  {% endcomment %}
  {% assign photo_pages = site.pages | where: "layout", "photo_set" %}
  {% assign photo_apex = photo_pages | where: "rarity", "apex" %}
  {% assign photo_nonapex = photo_pages | where: "rarity", "nonapex" %}
  {% for photo_page in photo_apex %}
    <li>
      <a href="{{ photo_page.url | prepend: site.baseurl }}">{{ photo_page.title }}</a>
    </li>
  {% endfor %}
  </ul>

Other rarities:
  <ul>
{% for photo_page in photo_nonapex %}
    <li>
      <a href="{{ photo_page.url | prepend: site.baseurl }}">{{ photo_page.title }}</a>
    </li>
  {% endfor %}
</ul>
