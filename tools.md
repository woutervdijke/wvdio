---
title: Tooltips

menuitem: true
menuorder: 5
---

# Mijn favoriete tools

Datajournalistiek is voor een heel groot deel handig doen met een computer. Goede tooltjes helpen daarbij. Dit zijn een aantal van mijn favorieten, per categorie:
<div>
{% for post in site.categories.tooltips %}
    {% if post.url %}
         <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
    {% endif %}
 {% endfor %}
</div>