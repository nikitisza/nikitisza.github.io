---
layout: page
permalink: /about/index.html
title: Niki Tisza
tags: [Niki, Personal]
imagefeature: niki_bench.jpg
chart: true
---


{% assign total_words = 0 %}
{% assign total_readtime = 0 %}
{% assign featuredcount = 0 %}
{% assign statuscount = 0 %}

{% for post in site.posts %}
    {% assign post_words = post.content | strip_html | number_of_words %}
    {% assign readtime = post_words | append: '.0' | divided_by:200 %}
    {% assign total_words = total_words | plus: post_words %}
    {% assign total_readtime = total_readtime | plus: readtime %}
    {% if post.featured %}
    {% assign featuredcount = featuredcount | plus: 1 %}
    {% endif %}
{% endfor %}


**Hello there**, welcome to my blog. 

I have always enjoyed art from an early age. My earliest memory of this is doodling on paper. I can remember spending most of my childhood just drawing and being inspired to make and design anything and everything. This love of art has stayed with me and developed and grown, however I worked in many other industries before coming back to design a few years ago. Since I’ve been working for both startups and worldwide known companies internationally in Ireland, Hungary and New Zealand.

Continuous learning has been always big part of my life, although I feel most of my skills have been self-taught through experimentation and following the work and tutorials of others. At the moment, I design experiences for all digital products such as websites, web apps and mobile apps (for tablet and phone too). I also do front-end development and I'm keen on learning more back-end dev too. Also I study part-time towards a master degree in design innovation.

In my free time (when I'm not learning something), I love to write, draw, paint, sew, cook, train, hunting good coffee and walking with my dog.

Blog Stat: it currently has {{ site.posts | size }} posts in {{ site.categories | size }} categories which combinedly have {{ total_words }} words, which will take an average reader ({{ site.wpm }} WPM) approximately <span class="time">{{ total_readtime }}</span> minutes to read. {% if featuredcount != 0 %}There is <a href="{{ site.url }}/featured">{{ featuredcount }} featured post</a>, you should definitely check out.{% endif %} The most recent post is {% for post in site.posts limit:1 %}{% if post.description %}<a href="{{ site.url }}{{ post.url }}" title="{{ post.description }}">"{{ post.title }}"</a>{% else %}<a href="{{ site.url }}{{ post.url }}" title="{{ post.description }}" title="Read more about {{ post.title }}">"{{ post.title }}"</a>{% endif %}{% endfor %} which was published on {% for post in site.posts limit:1 %}{% assign modifiedtime = post.modified | date: "%Y%m%d" %}{% assign posttime = post.date | date: "%Y%m%d" %}<time datetime="{{ post.date | date_to_xmlschema }}" class="post-time">{{ post.date | date: "%d %b %Y" }}</time>{% if post.modified %}{% if modifiedtime != posttime %} and last modified on <time datetime="{{ post.modified | date: "%Y-%m-%d" }}" itemprop="dateModified">{{ post.modified | date: "%d %b %Y" }}</time>{% endif %}{% endif %}{% endfor %}. The last commit was on {{ site.time | date: "%A, %d %b %Y" }} at {{ site.time | date: "%I:%M %p" }}.


***This is the space to create.***