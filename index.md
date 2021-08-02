[Blog](</posts/2021-08-01-meddie.md>) 📝  

[Links](</links.html>) 🔗

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>
