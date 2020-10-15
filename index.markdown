---
layout: default
---

<header>
  <h1>{{ site.title }}</h1>

  {% if site.theme_config.show_description == true %}
    <p>{{ site.description }}</p>
  {% endif %}
</header>

{% for cat in site.categories %}
  {% assign category = cat[0] %}
  <h3>{{ category }}</h3>

  <ul>
    {% for post in site.categories[category] limit:5 %}
      <li>
        {{ post.date | date: site.theme_config.date_format }}

        <a href="{{ post.url | relative_url }}">
          {{ post.title }}
        </a>
      </li>
    {% endfor %}

    {% if site.categories[category].size > 5 %}
      <li>
        <a href="{% link _category/fulltime.markdown %}">more</a>
      </li>
    {% endif %}
  </ul>
{% endfor %}

<center>
  <small>
    <a href="feed.xml">feed.xml</a>
  </small>
</center>
