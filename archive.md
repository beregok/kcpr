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
      {% for post in site.posts  %}
        {% capture this_year %}{{ post.date | date: "%Y" }}{% endcapture %}
        {% capture this_month %}
				{% comment %}  {{ post.date | date: "%B" }} {% endcomment %}
				{% assign m = post.date | date: "%-m" %}
				{% case m %}
				  {% when '1' %}Січень
				  {% when '2' %}Лютий
				  {% when '3' %}Березень
				  {% when '4' %}Квітень
				  {% when '5' %}Травень
				  {% when '6' %}Червень
				  {% when '7' %}Липень
				  {% when '8' %}Серпень
				  {% when '9' %}Вересень
				  {% when '10' %}Жовтень
				  {% when '11' %}Листопад
				  {% when '12' %}Грудень
				{% endcase %}
				{% endcapture %}
        {% capture next_year %}{{ post.previous.date | date: "%Y" }}{% endcapture %}
        {% capture next_month %}
				{% comment %} {{ post.previous.date | date: "%B" }} {% endcomment %}
				{% assign m = post.previous.date | date: "%-m" %}
				{% case m %}
				  {% when '1' %}Січень
				  {% when '2' %}Лютий
				  {% when '3' %}Березень
				  {% when '4' %}Квітень
				  {% when '5' %}Травень
				  {% when '6' %}Червень
				  {% when '7' %}Липень
				  {% when '8' %}Серпень
				  {% when '9' %}Вересень
				  {% when '10' %}Жовтень
				  {% when '11' %}Листопад
				  {% when '12' %}Грудень
				{% endcase %}
				{% endcapture %}
        {% if forloop.first %}
          <h2 id="year_{{this_year}}">{{this_year}}</h2>
          <h3 id="month_{{this_year}}_{{this_month}}">{{this_month}}</h3>
          <ul class="posts">
        {% endif %}
         <li><time>{{ post.date | date:"%d" }} - </time> <a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
        {% if forloop.last %}
          </ul>
        {% else %}
          {% if this_year != next_year %}
            </ul>
            <h2 id="year_{{next_year}}">{{next_year}}</h2>
            <h3 id="month_{{next_year}}_{{next_month}}">{{next_month}}</h3>
            <ul>
          {% else %}
            {% if this_month != next_month %}
              </ul>
              <h3 id="month_{{next_year}}_{{next_month}}">{{next_month}}</h3>
              <ul>
            {% endif %}
          {% endif %}
        {% endif %}
      {% endfor %}
</section>
