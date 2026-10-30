---
layout: page
permalink: /writing/
title: Writing
description: Policy articles, blog posts, reports, and interviews published elsewhere, with short summaries and links to the originals.
nav: true
nav_order: 4
---

{%- for group in site.data.writing -%}

<h2>{{ group.title }}</h2>
<div class="entries">
  {%- for item in group.items -%}
    {%- assign first_link = item.links | first -%}
    {%- capture title_url -%}{%- if first_link.url contains '://' -%}{{ first_link.url }}{%- else -%}{{ first_link.url | relative_url }}{%- endif -%}{%- endcapture -%}
    <div class="entry">
      <div class="entry-date">{{ item.year }}</div>
      <div class="entry-body">
        <div class="entry-title"><a href="{{ title_url }}">{{ item.title | escape }}</a></div>
        {%- if item.title_en -%}<div class="entry-subtitle">{{ item.title_en | escape }}</div>{%- endif -%}
        <div class="entry-meta">{{ item.venue | escape }}{%- if item.authors -%}, {{ item.authors | escape }}{%- endif -%}</div>
        <div class="entry-text">{{ item.summary | escape }}</div>
        <div class="entry-links">
          {%- for link in item.links -%}
            <a href="{%- if link.url contains '://' -%}{{ link.url }}{%- else -%}{{ link.url | relative_url }}{%- endif -%}">{{ link.label }}</a>
          {%- endfor -%}
        </div>
      </div>
    </div>
  {%- endfor -%}
</div>
{%- endfor %}
