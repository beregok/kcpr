---
layout: page
current: about
title: Архів
navigation: true
logo: 'assets/images/ghost.png'
class: page-template
subclass: 'post page'
---

<section>
  <h3>Статті написані цього року</h3>
  {%for post in site.posts %}
    {% unless post.next %}
      <ul>
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        </ul>
        <h3>{{ post.date | date: '%Y' }}</h3>
        <ul>
      {% endif %}
    {% endunless %}
      <li><time>{{ post.date | date:"%d %b" }} - </time><a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
  </ul>
</section>


