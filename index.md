---
layout: default
---

...in the meantime, take a look at my software development site [jermware.net](https://jermware.net)
<span style="font-size: 0;"><a rel="me" href="https://mstdn.social/@gavinjerman">Mastodon</a> </span>

{% assign postsByYear = site.posts | group_by_exp:"post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
  <h1>{{ year.name }}</h1>
  {% assign postsByMonth = year.items | group_by_exp:"post", "post.date | date: '%B'" %}

{% for month in postsByMonth %}
<h2>{{ month.name }}</h2>
<ul>
  {% for post in month.items %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <br>{{ post.excerpt }}<br><br>
    </li>
  {% endfor %}
</ul>

{% endfor %}
{% endfor %}
