---
layout: default
---

[Nigel Bailey](https://u13941160.ct.sendgrid.net/ls/click?upn=qGA9KeqTrDVLccgmtPRJXGHwO9wtloCt-2Ff7uuC1R4m-2BseUofT713d4FjsRHjAg5HRhHPegT5giZzQlM-2Fq-2BDaaqS2X3MlNleVOU5-2BsTbxl0SN8y94w2W3d4X8Pmh0pFIsuMTQ_UZ8Gt84SyECa2crBDmJWYetZxuCXqfOgiIwV0d3UeGLO6zmQ6rGa8iXpIJLE9uiotWtoDW-2FGI94AvOUj5fGilR-2Bj0aMH1OuXHNI97fsgf2QeWPLCQHlmnqZ6jY-2Fm1pi7-2Fh9CEakew2NaKWFWHEd-2FPhzhTF3dP7F-2BNG2WvvtwkdFFDu3FKJqDLVFBUtJ8gMTlyFNxc5lo4CC9EIXa-2BcJek2zynz4QPY966MItH-2FQlvI0-3D)

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
