---
layout: home
---

{% for cat in site.categories %}
  {% assign category = cat[0] %}
  <h3>{{ category }}</h3>

  <ul>
    {% for post in site.categories[category] %}
      <li>
        {{ post.date | date: site.theme_config.date_format }}

        <a href="{{ post.url | relative_url }}">
          {{ post.title }}
        </a>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
