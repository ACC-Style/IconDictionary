---
title:  "Member Hub "
date:   2021-01-13 10:14:44 -0500
categories: icons
---
<H2>Member Hub Icons</H2>
<p>
Member Hub is a property that is directly controled by ACC so icons here are not always a standard or used in other areas of the college. </p>
<div id="mylist" class="ul_none">
{% for icons in site.data.IconDictionaryData %}
{% assign categoryArray = icons.category | split:"," %}
{% assign classes = icons.class | split:"," %}
{% if categoryArray contains "memberhub" %}
    {% include icon.html %}
  {% endif %}
{% endfor %}
</div>

