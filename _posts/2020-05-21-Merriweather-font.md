---
layout: post  
title: "Шрифт Merriweather"  
date: 2020-05-21 10:01:20 +0200
categories: News
tags: 
- Blog
excerpt_separator: <!--more-->
---

Давно приглядывался к шрифту *Merriweather*.  
А вчера прочитал, что он -- один из самых популярный в Интернете.  
По крайней мере, на новостных сайтах и блогах. И это -- справедливо: читается хорошо, выглядит приятно, как латиница, так и кириллица.  
<!--more-->
Как правильно установить шрифт на свой сайт указано на [странице самого шрифта](https://fonts.google.com/specimen/Merriweather?_escaped_fragment_&query=Merriweather)

--01. Выбрать из предложенных вариантов нужный и нажать на `+Select this style`.

--02. В появившейся правой колонке нажимаем на `Embed`.

--03. Вставляем в *html* страницу между `<head>...</head>` следующий код (в нашей теме `Jekyll-Jacman` это в файле `/_includes/_partial/head.html`):  
   ```html
<link href="https://fonts.googleapis.com/css2?family=Merriweather&display=swap" rel="stylesheet">
   ```

--04. В файле *css* (у нас это -- `/assets/css/style.css`) добавляем название шрифта. Должно выглядеть так:
```css
font-family: 'Merriweather', serif;
```

--05. Сохраняем, ребилдим, проверяем на localhost`e, отправляем на сервер и...  

--06. Наслаждаемся.
