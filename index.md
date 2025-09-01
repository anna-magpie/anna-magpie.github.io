---
layout: default
title: "Anna Magpie – Biology × Computation"
---

<!-- Hero -->
<section class="py-10 flex items-center gap-6">
  <img src="https://avatars.githubusercontent.com/u/229820172?v=4" alt="Anna Magpie" class="w-28 h-28 rounded-full ring-2 ring-brand/40 object-cover">
  <div>
    <h1 class="text-4xl font-serif font-bold leading-tight">I’m Anna Magpie.</h1>
    <p class="mt-3 text-slate-700 dark:text-slate-300 max-w-prose">
      I work at the intersection of <strong>molecular biology</strong> and <strong>computation</strong>.
      I write about Julia, symbolic modeling, and systems biology.
    </p>
    <div class="mt-4 flex gap-3">
      <a href="{{ '/blog/' | relative_url }}" class="px-3 py-1.5 rounded-lg bg-brand/10 text-brand hover:bg-brand/20">Read the blog</a>
      <a href="{{ '/about/' | relative_url }}" class="px-3 py-1.5 rounded-lg border border-slate-200 dark:border-slate-700 hover:bg-slate-50 dark:hover:bg-slate-800">About me</a>
    </div>
  </div>
</section>

<!-- Latest posts -->
<section class="py-10 bg-white/50 dark:bg-darkbg/50 rounded-2xl">
  <h2 class="text-xl font-serif font-semibold mb-5">Latest posts</h2>
  <div class="grid gap-4">
    {% for post in site.posts limit:3 %}
    <article class="p-5 border border-slate-200 dark:border-slate-700 rounded-xl hover:bg-white dark:hover:bg-slate-800 transition">
      <h3 class="text-lg font-semibold">
        <a class="hover:text-brand" href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h3>
      <p class="text-xs text-slate-500">
        {{ post.date | date: "%Y-%m-%d" }} • {% for t in post.tags %}{{ t }} {% endfor %}
      </p>
      {% if post.excerpt %}
        <p class="text-sm text-slate-700 dark:text-slate-300 mt-1">{{ post.excerpt | strip_html }}</p>
      {% endif %}
    </article>
    {% endfor %}
  </div>
  <div class="mt-5">
    <a href="{{ '/blog/' | relative_url }}" class="text-brand">All posts →</a>
  </div>
</section>

<!-- Interests -->
<section class="py-10">
  <h2 class="text-xl font-serif font-semibold mb-4">What I’m interested in</h2>
  <ul class="list-disc pl-6 space-y-1 text-slate-700 dark:text-slate-300">
    <li>Symbolic–numeric workflows (Symbolics.jl, ModelingToolkit)</li>
    <li>Mechanistic modeling in molecular & systems biology</li>
    <li>Performance & ergonomics in scientific programming (Julia)</li>
  </ul>
  <a href="{{ '/about/' | relative_url }}" class="inline-block mt-3 text-brand">More about me →</a>
</section>

<!-- CV teaser -->
<section class="py-10 bg-white/50 dark:bg-darkbg/50 rounded-2xl">
  <h2 class="text-xl font-serif font-semibold mb-3">CV</h2>
  <p class="text-slate-700 dark:text-slate-300 max-w-prose">
    Molecular biology background with a focus on computational methods and modeling.
    Highlights include cloning strategy design for selective neuronal expression and
    building glue code around Ensembl, Primer3, and OpenCloning.
  </p>
  <a href="{{ '/cv/' | relative_url }}" class="inline-block mt-3 text-brand">View CV →</a>
</section>

