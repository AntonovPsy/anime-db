---
layout: default
title: Список аниме
---
# Список аниме

{% assign items = site.pages | where: "anime", true | sort: "title" %}
Всего записей: {{ items | size }}

<table>
  <thead>
    <tr><th>Обложка</th><th>Название</th><th>Альтернативное</th><th>Рейтинг</th></tr>
  </thead>
  <tbody>
  {% for p in items %}
    <tr>
      <td>{% if p.cover %}<img src="{{ p.cover | relative_url }}" alt="" width="70">{% else %}—{% endif %}</td>
      <td><a href="{{ p.url | relative_url }}">{{ p.title | escape }}</a></td>
      <td>{{ p.alt_title | default: "—" | escape }}</td>
      <td>{{ p.rating | default: "—" }}</td>
    </tr>
  {% endfor %}
  </tbody>
</table>
