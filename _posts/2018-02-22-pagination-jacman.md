---
layout: post  
title: "Фикс для пагинации в теме для Jekyll - jekyll-jacman"  
date: 2018-02-22 21:21:20 +0200
categories: News
tags: 
- Blog
- Bugs
---
Итак, тема для **Jekyll - *Jekyll-Jacman***
Не работала пагинация.  
После того как изменил количество сообщений на страницу - вместо 20 поставил 5 - появилась пагинация, но не с правильными путями  
Изменения делал в файле`jekyll-jacman\_includes\index.html`   

Меняем это:

```ruby
{% raw %} 
    <nav id="page-nav" class="clearfix{% if site.index.expand != true  %} unexpand{% endif %}">
  <nav id="page-nav" class="clearfix">
    {% if paginator.previous_page %}
    <a class="extend prev" rel="prev" href="{{ paginator.previous_page_path }}"><span></span>Prev</a>
    {% endif %}
    {% if paginator.page == 1 %}
    <span class="page-number current">1</span>
    {% else %}
    <a class="page-number" href="/">1</a>
    {% endif %}
    {% for i in (2..paginator.total_pages) %}
    {%if i == paginator.page %}
    <span class="page-number current">{{ i }}</span>
    {% else %}
    <a class="page-number" href="/page{{ i }}">{{ i }}</a>
    {% endif %}
    {% endfor %}
     {% if paginator.next_page %}
    <a class="extend next" rel="next" href="{{ paginator.next_page_path }}">Next<span></span></a>
    {% endif %}
  </nav>
  </nav>
{% endraw %}
```

На это:

```ruby
{% raw %} 
<nav id="page-nav" class="clearfix{% if site.index.expand != true  %} unexpand{% endif %}">
  <nav id="page-nav" class="clearfix">
    {% if paginator.previous_page %}
    <a class="extend prev" rel="prev" href="{{ site.baseurl }}{{ paginator.previous_page_path }}"><span></span>Пред.</a>
    {% endif %}
    {% if paginator.page == 1 %}
    <span class="page-number current">1</span>
    {% else %}
    <a class="page-number" href="{{ site.baseurl }}">1</a>
    {% endif %}
    {% for i in (2..paginator.total_pages) %}
    {%if i == paginator.page %}
    <span class="page-number current">{{ i }}</span>
    {% else %}
    <a class="page-number" href="{{ site.baseurl }}/page{{ i }}">{{ i }}</a>
    {% endif %}
    {% endfor %}
     {% if paginator.next_page %}
    <a class="extend next" rel="next" href="{{ site.baseurl }}{{ paginator.next_page_path }}">След.<span></span></a>
    {% endif %}
  </nav>
  </nav>
{% endraw %}
```
