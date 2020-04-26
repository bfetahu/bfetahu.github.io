---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% assign postsByYear = site.publications reversed | group_by_exp:"post", "post.date | date: '%Y'"  %}
{% for yearMonth in postsByYear %}
  <h2>{{ yearMonth.name }}</h2>
   <ul>
      {% for post in yearMonth.items %}
  <li> {% include archive-single.html %}</li>
      {% endfor %}
  </ul>
{% endfor %}

