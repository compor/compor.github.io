---
layout: page
title: "Categories"
permalink: "/categories/"

---

<ul class="category-cloud">
{% for category in site.categories %}
  <li style="font-size: {{ category | last | size | times: 100 | divided_by: site.categories.size | plus: 70  }}%">
    <a href="#{{ category | first | slugize }}">
      {{ category | first }}
    </a>
  </li>
{% endfor %}
</ul>

<div id="archives">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <h3 id="#{{ category_name | slugize }}">{{ category_name }}</h3>
    <a name="{{ category_name | slugize }}"></a>
    {% for post in site.categories[category_name] %}
    <article class="archive-item">
      <h4><a href="{{ root_url }}{{ post.url }}">{{post.title}}</a></h4>
    </article>
    {% endfor %}
  </div>
{% endfor %}
</div>

