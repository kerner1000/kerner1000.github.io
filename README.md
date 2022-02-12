{% for category in site.categories %}
  <h1>{{ category[0] }}</h1>
  <ul>
    {% for post in category[1] %}
      <li><font size="+1"><a href="{{ post.url }}">{{ post.title }}</a></font>&nbsp;&ndash;&nbsp;{{ post.date | date: '%B %d, %Y' }} <br> {% if post.excerpt != nil and post.excerpt != "" %} <i> {{ post.excerpt }}</i>{% endif %}</li>
    {% endfor %}
  </ul>
{% endfor %}
