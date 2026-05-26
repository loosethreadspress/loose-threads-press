---
layout: default
---

<article class="piece">
  <div class="container">

    <a href="{{ '/loom/' | relative_url }}" class="piece-back">The Loom</a>

    <header class="piece-header">
      {% if page.section %}
        <span class="piece-section-tag">{{ page.section }}</span>
      {% endif %}

      <h1 class="piece-title">{{ page.title }}</h1>

      {% if page.authors %}
        <p class="piece-byline">
          <span class="by">By</span>
          {% assign last_index = page.authors.size | minus: 1 %}
          {% for author in page.authors %}
            {{ author }}{% if forloop.index0 < last_index %}{% if forloop.index0 == last_index | minus: 1 %} &amp; {% else %}, {% endif %}{% endif %}
          {% endfor %}
        </p>
      {% elsif page.author %}
        <p class="piece-byline"><span class="by">By</span>{{ page.author }}</p>
      {% endif %}

      <p class="piece-date">{{ page.date | date: "%B %-d, %Y" }}</p>
    </header>

    <div class="piece-content">
      {{ content }}
    </div>

    <footer class="piece-footer">
      <a href="{{ '/loom/' | relative_url }}">← Back to The Loom</a>
      <span>Loose Threads Press</span>
    </footer>

  </div>
</article>
