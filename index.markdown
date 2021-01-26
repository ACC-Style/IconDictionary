---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---
<div><label for="iconSearch" class="">Search For An Icon</label>
<div class="flex relative">
    <input class="flex_auto font_2 p_3 p-x_4 lh_2 br_black-3 br_radius" type="text" id="iconSearch" onkeyup="myFunction()" placeholder="Search for icons.." title="Type in an icon">
    <div class="absolute font_2 p_3 p-x_4 lh_2  opacity_4 t_0 r_0 b_0 "><i class="fas fa-search"></i></div>
    </div>
</div>
<div id="mylist" class="ul_none">
{% for icons in site.data.IconDictionaryData %}
{% assign categoryArray = icons.category | split:"," %}
{% assign classes = icons.class | split:"," %}
    {% include icon.html %}
{% endfor %}
</div>
<script>
function myFunction() {
    var input, filter, list, li, a, i, txtValue, synonymValue, synonym;
    input = document.getElementById("iconSearch");
    filter = input.value.toUpperCase();
    list = document.getElementById("mylist");
    li = list.getElementsByClassName("IconListItem");
    for (i = 0; i < li.length; i++) {
        a = li[i].getElementsByTagName("a")[0];
        txtValue = a.textContent || a.innerText;
        synonym = li[i].getElementsByClassName('IconSynonyms')[0];
        synonymValue = (synonym)? (synonym.textContent || synonym.innerText): '';
       
        if (txtValue.toUpperCase().indexOf(filter) > -1 || synonymValue.toUpperCase().indexOf(filter)>-1 ) {
            li[i].style.display = "";
             console.log(synonymValue);
        } else {
            li[i].style.display = "none";
        }
    }
}
</script>