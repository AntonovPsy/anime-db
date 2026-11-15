---
layout: default
title: Список аниме
---
# Список аниме

{% assign items = site.pages | where: "anime", true | sort: "title" %}
Всего записей: {{ items | size }}

| Обложка | Название | Альтернативное | Рейтинг |
| --- | --- | --- | --- |
{% for p in items -%}
| {% if p.cover %}<img src="{{ p.cover | relative_url }}" alt="" width="70">{% else %}—{% endif %} | [{{ p.title | escape }}]({{ p.url | relative_url }}) | {{ p.alt_title | default: "—" | escape }} | {{ p.rating | default: "—" }} |
{% endfor %}
