---
layout: page
title: "Home"
class: home
---

# Hi, I'm Boyu LI

<div class="columns" markdown="1">

<div class="intro" markdown="1">
A mphil student at HKUST(GZ) [CISLab](https://cislab.hkust-gz.edu.cn), at Computational Media and Art Thrust of Hong Kong University of Science and Technology (GuangZhou), supervised by Prof. Zeyu Wang. Before that, I obtained my bachelor’s degree in Automation from Xi’an Jiaotong University (XJTU) in 2023.
My field of interest are: 

+ Augmented reality (AR) and Virtual Reality (VR)
  
+ Deep leaning or computer Vision in Robotics

Details are in my [CV]({{ "/cv/" | relative_url }}).
</div>

<div class="me" markdown="1">
<picture>
  <source srcset='https://avatars.githubusercontent.com/u/58367685?s=400&u=e835e201f8f23d37a53b4f9b72d6af15f28a4c6d&v=4' />
  <img
    src='[/images/dominik_berlin.jpg](https://avatars.githubusercontent.com/u/58367685?s=400&u=e835e201f8f23d37a53b4f9b72d6af15f28a4c6d&v=4)'
    alt='Boyu Li'>
</picture>

{:.no-list}
* <a href="mailto:{{ site.email }}">{{ site.email }}</a>
* NSH 2602B
</div>

</div>
<!-- {% include iframe.html src="https://www.bilibili.com/video/BV1LV411r756" %} -->

## Featured <a href="{{ "/projects/" | relative_url }}">Projects</a>

<div class="featured-projects">
  {% assign sorted_projects = site.data.projects | sort: 'highlight' %}
  {% for project in sorted_projects %}
    {% if project.highlight %}
      {% include project.html project=project %}
    {% endif %}
  {% endfor %}
</div>
<a href="{{ "/projects/" | relative_url }}" class="button">
  <i class="fas fa-chevron-circle-right"></i>
  Show More Projects
</a>

## Featured <a href="{{ "/publications/" | relative_url }}">Publications</a>

<div class="featured-publications">
  {% assign sorted_publications = site.publications | sort: 'year' | reverse %}
  {% for pub in sorted_publications %}
    {% if pub.highlight %}
      <a href="{{ pub.pdf }}" class="publication">
        <strong>{{ pub.title }}</strong>
        <span class="authors">{% for author in pub.authors %}{{ author }}{% unless forloop.last %}, {% endunless %}{% endfor %}</span>.
        <i>{% if pub.venue %}{{ pub.venue }}, {% endif %}{{ pub.year }}</i>.
        {% for award in pub.awards %}<br/><span class="award"><i class="fas fa-{% if award == "Best Paper Award" %}trophy{% else %}award{% endif %}" aria-hidden="true"></i> {{ award }}</span>{% endfor %}
      </a>
    {% endif %}
  {% endfor %}
</div>

<a href="{{ "/publications/" | relative_url }}" class="button">
  <i class="fas fa-chevron-circle-right"></i>
  Show All Publications
</a>

<div class="news-travel" markdown="1">

<div class="news" markdown="1">
## Latest News

<ul>
{% for news in site.data.news limit:10 %}
  {% include news.html news=news %}
{% endfor %}
</ul>

</div>

<div class="travel" markdown="1">
## Latest Travel

<table>
<tbody>
{% assign future_travel = site.data.travel | where_exp:'item','item.start == null' %}
{% for travel in future_travel %}
  {% include travel.html travel=travel %}
{% endfor %}
{% assign sorted_travel = site.data.travel | where_exp:'item','item.start' | sort: 'start' | reverse %}
{% for travel in sorted_travel limit:10 %}
  {% include travel.html travel=travel %}
{% endfor %}
</tbody>
</table>

</div>

</div>
