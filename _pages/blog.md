---
layout: leather_page
title: A Shine of Bootblacks
permalink: '/blog/'
---
<div class="row">
  <div class="col-sm-8">

    <article class="blog">
      <h1 class="page-title">{{ site.blog_title }}</h1>
    </article>

    <div class="posts">
      {% for post in site.posts %}
      <article class="post headroom">
        <h3 class="post-title">
          <a href="{{ post.url }}">
            {{ post.title }}
          </a>
        </h3>

        <time datetime="{{ post.date | date_to_xmlschema }}" class="post-date">{{ post.date | date_to_string }}</time>
        <p>
          {{ post.content | strip_html | truncatewords: 50 }} <a href="{{post.url}}"> (Read More) </a>
        </p>
      </article>
      {% endfor %}
    </div>

    <div class="pagination">
      {% if paginator.next_page %}
        <a class="pagination-item older" href="{{ site.baseurl }}page{{paginator.next_page}}">Older</a>
      {% else %}
        <span class="pagination-item older">Older</span>
      {% endif %}
      {% if paginator.previous_page %}
        {% if paginator.page == 2 %}
          <a class="pagination-item newer" href="{{ site.baseurl }}">Newer</a>
        {% else %}
          <a class="pagination-item newer" href="{{ site.baseurl }}page{{paginator.previous_page}}">Newer</a>
        {% endif %}
      {% else %}
        <span class="pagination-item newer">Newer</span>
      {% endif %}
    </div>
  </div>

  <div class="col-sm-4">
    {% include leather_sidebar.html %}
  </div>
</div>
