---
title: Blog

menuitem: false
menuorder: 1
---

<div id="blogindex">
 {% for post in site.categories.blog %}


    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      <p>{% if post.content contains "<!--start-->" %}{% assign extract = post.content | split: "<!--start-->" | last | split: "<!--end-->" | first | strip_html %}
                 {{ extract }}
          {% elsif post.content contains "<!--more-->" %}
                  {{ post.excerpt | strip_html }}
          {% else %}
                   {{ post.content | strip_html | truncatewords: 50 }}
           {% endif %}


                  <p>

  {% endfor %}


