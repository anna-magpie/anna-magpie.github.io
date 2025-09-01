---
layout: default
title: "Blog — Anna Magpie"
---

# Blog

<div class="grid gap-4">
{% for post in site.posts %}
  <article class="p-5 border border-slate-200 dark:border-slate-800 rounded-xl hover:bg-slate-50 dark:hover:bg-slate-900 transition">
    <h2 class="text-lg font-semibold">
      <a class="hover:text-brand" href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </h2>
    <p class="text-xs text-slate-500">
      {{ post.date | date: "%Y-%m-%d" }}
      {% if post.tags %} • {{ post.tags | join: ", " }}{% endif %}
    </p>
    {% if post.excerpt %}
      <p class="text-sm text-slate-600 dark:text-slate-400">{{ post.excerpt | strip_html }}</p>
    {% endif %}
  </article>
{% endfor %}
</div>
