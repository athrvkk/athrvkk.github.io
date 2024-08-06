---
layout: page
permalink: /news/
title: News
description: All news in reversed chronological order.
nav: true
nav_order: 3

---
<!-- _pages/news.md -->
<div class="news">
    {% if site.news != blank -%} 
        {%- assign news_size = site.news | size -%}
        <div class="table-responsive">
            <table class="table table-sm table-borderless">
                {%- assign news = site.news | reverse -%}
                {% for item in news %}
                    <tr>
                        <!-- <th class="date-header"><abbr class="badge">{{ item.date | date: "%b %Y" }}</abbr></th> -->
                        <!-- <th scope="row abbr"><abbr class="badge">{{ item.date | date: "%b %Y" }}</abbr></th> -->
                        <th scope="row" style="width:10%">{{ item.date | date: "%b %Y" }}</th>
                        <td>
                            {% if item.inline -%} 
                                {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
                            {%- else -%} 
                                <a class="news-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
                            {%- endif %} 
                        </td>
                    </tr>
                {%- endfor %} 
            </table>
        </div>
    {%- else -%} 
        <p>No news so far...</p>
    {%- endif %} 
</div>
