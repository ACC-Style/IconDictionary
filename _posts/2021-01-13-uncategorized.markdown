---
title:  "Uncategorized"
date:   2021-01-13 10:14:44 -0500
categories: icons
---
<H2>Incomplete Icons</H2>
<p>
This is a living document so during audits and colleciton process incomplete icons will be found here before they are standarized and categorized into the rest of the icons. </p>
<div class="ul_none">
{% for icons in site.data.IconDictionaryData %}
{% assign categoryArray = icons.category | split:"," %}
{% assign classes = icons.class | split:"," %}
{% if icons.category.size == nil %}
   {% include icon.html %}
{% endif %}
{% endfor %}
</div>

