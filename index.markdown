---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

<div id="mylist" class="ul_none">
{% for icons in site.data.IconDictionaryData %}
{% assign categoryArray = icons.category | split:"," %}
{% assign classes = icons.class | split:"," %}
    {% include icon.html %}
{% endfor %}
</div>
