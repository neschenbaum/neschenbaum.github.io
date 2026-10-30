---
layout: page
permalink: /writing/
title: Writing
description: Policy articles, blog posts, reports, and interviews published elsewhere, with short summaries and links to the originals.
nav: true
nav_order: 4
---

{%- for group in site.data.writing -%}

<h2 class="wr-group">{{ group.title }}</h2>
<div class="writing">
  {%- for item in group.items -%}
    {%- assign first_link = item.links | first -%}
    {%- capture title_url -%}{%- if first_link.url contains '://' -%}{{ first_link.url }}{%- else -%}{{ first_link.url | relative_url }}{%- endif -%}{%- endcapture -%}
    <div class="wr-item">
      <div class="wr-year">{{ item.year }}</div>
      <div class="wr-body">
        <div class="wr-title"><a href="{{ title_url }}">{{ item.title | escape }}</a></div>
        {%- if item.title_en -%}<div class="wr-title-en">{{ item.title_en | escape }}</div>{%- endif -%}
        <div class="wr-meta">{{ item.venue | escape }}{%- if item.authors -%}, {{ item.authors | escape }}{%- endif -%}</div>
        <div class="wr-summary">{{ item.summary | escape }}</div>
        <div class="wr-links">
          {%- for link in item.links -%}
            <a href="{%- if link.url contains '://' -%}{{ link.url }}{%- else -%}{{ link.url | relative_url }}{%- endif -%}">{{ link.label }}</a>
            {%- unless forloop.last -%}<span class="wr-sep">·</span>{%- endunless -%}
          {%- endfor -%}
        </div>
      </div>
    </div>
  {%- endfor -%}
</div>
{%- endfor %}

<style>
  .wr-group {
    font-size: 0.95rem;
    font-weight: 600;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    color: var(--global-text-color-light);
    margin: 2.25rem 0 0.6rem;
  }
  .wr-item {
    display: flex;
    flex-direction: row;
    gap: 1.5rem;
    padding: 0.9rem 0;
    border-top: 1px solid var(--global-divider-color);
  }
  .writing .wr-item:last-child {
    border-bottom: 1px solid var(--global-divider-color);
  }
  .wr-year {
    flex: 0 0 4rem;
    color: var(--global-theme-color);
    font-weight: 600;
    font-size: 0.9rem;
    padding-top: 0.15rem;
  }
  .wr-body {
    flex: 1 1 auto;
  }
  .wr-title {
    font-weight: 500;
  }
  .wr-title-en {
    font-style: italic;
    color: var(--global-text-color-light);
    font-size: 0.95rem;
  }
  .wr-meta {
    font-size: 0.88rem;
    color: var(--global-text-color-light);
    margin-top: 0.15rem;
  }
  .wr-summary {
    margin: 0.45rem 0 0.35rem;
  }
  .wr-links {
    font-size: 0.85rem;
  }
  .wr-sep {
    margin: 0 0.45rem;
    color: var(--global-text-color-light);
  }
  @media (max-width: 576px) {
    .wr-item {
      flex-direction: column;
      gap: 0.2rem;
    }
    .wr-year {
      flex-basis: auto;
    }
  }
</style>
