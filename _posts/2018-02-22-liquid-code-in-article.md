---
layout: post  
title: "Как отображать код Liquid code в статье"  
date: 2018-02-22 23:21:20 +0200
categories: News
tags: 
- Blog
- Bugs
---
Писал статью.  (*test-проверка: 2020-05-01*)  
Указал код. Всё красиво с подцветкой, но...  
Не отобразился и вообще чепуха произошла.  
По-гуглил. Нашёл [это решение](https://www.juev.org/2012/07/05/jekyll-liquid-code-in-article/)  
В [предыдущей статье](https://dvesti.github.io/jekyll-jacman/news/2018/02/22/pagination-jacman/) получилось всё-таки сделать как надо  

Секрет в тэгах {`%raw%`} и {`%endraw%`}.  
Код с **хтмл** и *руби* и ***всего***, что есть в файле надо обрамить ими - и всё! :smile:
**P.S.** [Полезная ссылка](https://jekyllrb.com/docs/templates/#code-snippet-highlighting) по теме
