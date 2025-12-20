---
layout: default
title: Resume
permalink: /resume/
---

<h1 class="resume-title">Favourite Books</h1>

<section id="books">
  {% assign books = "image.png|image10.png|image 1.png|image2.png|images3.jpg|image8.png|image 5.jpg|image7.png|image6.png|image9.png" | split: "|" %}
  <div class="books-grid">
    {% for b in books %}
      <figure class="book-item">
        <img src="{{ '/assets/images/' | append: b | relative_url }}" alt="Book {{ forloop.index }}">
      </figure>
    {% endfor %}
  </div>
</section>

<hr />

<p><strong>My favourite activities are:</strong></p>
<ul>
<li>Reading books</li>
<li>Drawing</li>
<li>Travelling</li>
<li>Coding (Python, Html, Css)</li>
</ul>
