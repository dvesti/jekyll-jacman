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
    <a class="extend prev" rel="prev" href="{{ paginator.previous_page_path }}"><span></span>Prev</a>

    <span class="page-number current">1</span>

    <a class="page-number" href="/">1</a>

    <span class="page-number current">{{ i }}</span>

    <a class="page-number" href="/page{{ i }}">{{ i }}</a>

    <a class="extend next" rel="next" href="{{ paginator.next_page_path }}">Next<span></span></a>
```

На это:

```ruby
    <a class="extend prev" rel="prev" href="{{ site.baseurl }}{{ paginator.previous_page_path }}"><span></span>Пред.</a>
  
     <span class="page-number current">1</span>

    <a class="page-number" href="{{ site.baseurl }}">1</a>
  
    <span class="page-number current">{{ i }}</span>
  
    <a class="page-number" href="{{ site.baseurl }}/page{{ i }}">{{ i }}</a>
  
    <a class="extend next" rel="next" href="{{ site.baseurl }}{{ paginator.next_page_path }}">След.<span></span></a> 
```

