---
layout: default
title: About me
permalink: /about/
---

I have participated in several coding workshops, where I learned the basics of <b>HTML</b> and <b>CSS</b>. These workshops helped me understand how websites are structured and how design works.

Over the years, I have taken part in international teamwork competitions such as [OCEP](https://www.eurolympic.org/olympic-culture-and-education-programme-launched-in-baku/) , [IEARN](https://www.iearn.org/) , and [E-twinning](https://school-education.ec.europa.eu/en/etwinning) , as well as science fairs and events like <b>“My Path in IT”</b> and the <b>Informatics Olympiad</b>. These experiences helped me grow as a communicator, collaborator, and critical thinker.


I also enjoy public speaking and have worked on presentations for conferences, academic projects, and competitions-including drawing contests, <b>Olympic Day events</b> , and <b>the Children’s Conference at the American Center Baku</b>. These opportunities helped me build confidence and express my ideas clearly in front of different audiences. 

<div class="left-logos" aria-hidden="false">
	<a href="https://iearn.org/" target="_blank" rel="noopener">
		<img src="https://www.globaledguide.org/assets/imgs/iearn_logo_vector.png" alt="iEARN logo" style="width:120px;">
	</a>
	<a href="https://www.pngegg.com/en/search?q=etwinning" target="_blank" rel="noopener">
		<img src="https://e7.pngegg.com/pngimages/350/447/png-clipart-etwinning-europe-school-teacher-education-school-text-logo.png" alt="eTwinning logo" style="width:120px;">
	</a>
</div>


<!-- Certificates gallery -->
<hr />
<section id="certificates">
	<h2>My Certificates</h2>

	{% assign certs = "sertificate8.jpeg|sertificate6.jpeg|sertificate7.jpeg|sertificate5.jpeg|sertificate.jpeg|sertificate2.jpeg|sertificate10.jpeg|sertificate9.jpeg|sertificate12.jpeg|sertificate11.jpeg|sertificate3.jpeg|sertificate4.jpeg" | split: "|" %}
	<div class="certificates-grid">
		{% for c in certs %}
			<figure class="cert-item">
				<img src="{{ '/assets/images/' | append: c | relative_url }}" alt="Certificate {{ forloop.index }}">
			</figure>
		{% endfor %}
	</div>
</section>

<!-- Favourite Books gallery -->
<hr />
<section id="books">
	<h2>Favourite Books</h2>

	{% assign books = "image.png|image10.png|image 1.png|image2.png|images3.jpg|image8.png|image 5.jpg|image7.png|image6.png|image9.png" | split: "|" %}
	<div class="books-grid">
		{% for b in books %}
			<figure class="book-item">
				<img src="{{ '/assets/images/' | append: b | relative_url }}" alt="Book {{ forloop.index }}">
			</figure>
		{% endfor %}
	</div>
</section>
