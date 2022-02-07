{% for category in site.categories %}
  <h3>{{ category[0] }}</h3>
  <ul>
    {% for post in category[1] %}
      <li><a href="{{ post.url }}">{{ post.title }}</a> {{ post.date | date: '%B %d, %Y' }}
{% if post.excerpt != nil and post.excerpt != "" %} - <i>{{ post.excerpt }}</i>{% endif %}</li>
    {% endfor %}
  </ul>
{% endfor %}
