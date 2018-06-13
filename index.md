---
layout: home
title: Home
searchable: true
categories:
    - Uncategorized
tags:
    - home
date: 2018-06-13 14:09:00
---
AmpVIEW's Online User Guide is an expansive set of resources that helps you find the information you need for your electrochemical measurements.

<input type="search" placeholder="&#xF002;" id="input-search">

<h1>Contents</h1>
<ul class="category-list">
    {% assign categories = "" | split: ',' %}
    {% for category in categories %}
    {% assign category_pages = site.pages | where:"categories",category %}
    <li>
        <a href="/{{ site.baseurl }}/category/{{ category | replace: " ","-" | downcase }}">{{ category}} ({{ category_pages | size }})</a>
    </li>
    {% endfor %}
</ul>