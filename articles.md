---
title: Articles

menuitem: true
menuorder: 6
---



# Mijn laatste artikelen


<ul>
{% for article in site.data.articles %}
  <li>
    {{article.site}}: <a href="{{ article.url }}" target="_blank">
      {{ article.title }}
    </a>
  </li>
{% endfor %}
</ul>