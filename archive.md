---
title: Archiv
author: kleinen
layout: default
---

# Archiv

# Lectures WS 2014/15

- [Info1]({{site.baseurl}}ws2014/info1/)
- [Info3]({{site.baseurl}}ws2014/info3/)
- [WT1 Web Technology]({{site.baseurl}}ws2014/webapplications/)
- [Praxisprojekt]({{site.baseurl}}ss2014/project)


<h1>Lectures SS 2014</h1>
<ul>
<li><a href="{{site.baseurl}}ss2014/info2">Informatik 2</a></li>
<li><a href="{{site.baseurl}}ss2014/info3">Informatik 3</a></li>
<li><a href="{{site.baseurl}}ss2014/project">Praxisprojekt</a></li>
</ul>


<h1>Lectures WS 2013/2014</h1>
<ul>
<li><a href="{{site.baseurl}}ws2013/info1">Informatik 1</a></li>
<li><a href="{{site.baseurl}}ws2013/info3">Informatik 3</a></li>
<li><a href="{{site.baseurl}}ws2013/project">Praxisprojekt</a></li>
</ul>

<h1>Older Lectures</h1>

  * [SS 2013]({{site.baseurl}}ss2013/)
  * [WS 2012]({{site.baseurl}}ws2012/)

<div id="home">
  <h1>All Anouncements</h1>
  <ul class="posts">
    {% for post in site.posts %}
      <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
</div>
