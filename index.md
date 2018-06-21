---
layout: home
title: Home
searchable: true
categories:
    - Uncategorized
tags:
    - home
date: 2018-06-13 14:09:00
description: Home page
---
AmpVIEW's Online User Guide is an expansive set of resources that helps you find the information you need for your electrochemical measurements.

<div id="search-container">
    <input type="search" id="search-input" placeholder="Search">
    <ul id="results-container" style="display: none;"></ul>
</div>




<h1>Contents</h1>
<ul class="category-list">
    {% assign categories = "Uncategorized,Overview,Requirements,Installation,Proceeding,Licenses and Terms of Use" | split: ',' %}
    {% for category in categories %}
    {% assign category_pages = site.pages | where:"categories",category %}
    <li>
        <a href="/{{ site.baseurl }}/category/{{ category | replace: " ","-" | downcase }}">{{ category}} ({{ category_pages | size }})</a>
    </li>
    {% endfor %}
</ul>

<script src="{{ "/assets/js/simple-jekyll-search.min.js" | relative_url }}" type="text/javascript"></script>
<script>
window.onload=function(){
    SimpleJekyllSearch({
        searchInput: document.getElementById('search-input'),
        resultsContainer: document.getElementById('results-container'),
        json: '{{ "/search.json" | relative_url }}'
        ,
        searchResultTemplate: '<li class="search-result"><a href="{url}">{title}</a><div class="description">{description}</div></li>'
    })
}
</script>