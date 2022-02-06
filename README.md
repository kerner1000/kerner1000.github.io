<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a> {{ post.categories }} {{ post.tags }}
    </li>
  {% endfor %}
</ul>
