{% for category in site.categories %}
  <h3>{{ category[0] }}</h3>
  <ul>
    {% for post in category[1] %}
      <li><a href="{{ post.url }}">{{ post.title }}</a>{% if post.excerpt != null and post.excerpt != "" %} - <i>{{ post.excerpt }}</i>{% endif %}</li>
    {% endfor %}
  </ul>
{% endfor %}
