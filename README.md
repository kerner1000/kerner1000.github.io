{% for category in site.categories %}
  <h3>{{ category[0] }}</h3>
  <ul>
    {% for post in category[1] %}
      <li><a href="{{ post.url }}">{{ post.title }}</a> - <i>{{ post.excerpt }}</i></li>
    {% endfor %}
  </ul>
{% endfor %}
