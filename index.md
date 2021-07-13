---
layout: default
---

### Downloads

<ol>
{% for item in site.data.data %}
{% assign ebk = "/books/" | append: item.name | append: ".epub" %}
{% assign pbk = "/books/" | append: item.name | append: ".pdf" %}
{% if item.type == "ebook" %}
<li>{{item.name}} (<a href="{{ebk}}">EPUB</a>, <a href="{{pbk}}">PDF</a>) <small>{{ item.date }}</small></li>
{% elsif item.type == "pdf" %}
<li>{{item.name}} (<a href="{{pbk}}">PDF</a>) <small>{{ item.date }}</small></li>
{% endif %}
{% endfor %}
</ol>

  
### Miscellaneous

<ol>
{% for bpage in site.bits %}
<li><a href="{{bpage.id}}">{{bpage.title}}</a>
{% for item in site.data.data %}
{% if item.name == bpage.title %} 
<span style="color:orange;"><small> - {{item.status}} - </small></span>
{% endif %}
{% endfor %}
</li>
{% endfor %}
</ol>


<div style="clear: both;"></div>
