---
layout: page
title: "Home"
class: home
---

# Hi, I'm Boyu LI

<div class="columns" markdown="1">

<div class="intro" markdown="1">
I am a Ph.D. student in the [Division of Arts and Machine Creativity](https://amc.hkust.edu.hk/) at [the Hong Kong University of Science and Technology](https://hkust.edu.hk/), supervised by [Prof. Hongbo Fu](https://hongbofu.people.ust.hk/), co-supervised by [Prof. Zeyu Wang](https://cislab.hkust-gz.edu.cn/members/zeyu-wang/). Prior to this, I was a master student at [CISLab](https://cislab.hkust-gz.edu.cn/)
in the [Computational Media and Arts Thrust](http://cma.hkust-gz.edu.cn/) at HKUST (Guangzhou), where I worked under the supervision of [Prof. Zeyu Wang](https://cislab.hkust-gz.edu.cn/members/zeyu-wang/), co-supervised by [Prof. Huamin Qu](http://huamin.org/). I obtained my bachelor’s degree in Automation from [Xi’an Jiaotong University](https://www.xjtu.edu.cn/?mobile) in 2023.

My main research interests lie at the intersection of Computer Vision, Human–Computer Interaction (HCI), and Computer Graphics, focusing on creativity support tools powered by Generative AI and 3D interaction in AR/VR environments. I am particularly interested in animation creation and 3D authoring systems that enhance human creativity and expressiveness.
My works have been published in top-tier HCI and graphics venues, including ACM UIST, IEEE VR, ACM CSCW, IEEE TVCG, and SIGGRAPH Asia. I also serve as a reviewer for major conferences such as CHI, IEEE VR, and CSCW, and as a Program Committee member for IUI.

Details are in my [CV]({{ "/cv/" | relative_url }}).
</div>

<div class="me" markdown="1">
<picture>
  <source srcset='images/Boyu Li Avatar.jpg' />
  <img
    src="images/BoyuLi_Avatar.jpg"
    alt='Boyu Li'>
</picture>

{:.no-list}
* <a href="mailto:{{ site.email }}">{{ site.email }}</a>
</div>

</div>






## Featured Publications

<!-- style 1: with border -->
<div class="pubs">
  {% assign sorted_publications = site.publications | sort: 'year' | reverse %}
  {% for pub in sorted_publications %}
    {% if pub.highlight%}
      {% include publication.html pub=pub %}
    {% endif %}
  {% endfor %}
</div>

<a href="{{ "/publications/" | relative_url }}" class="button">
  <i class="fas fa-chevron-circle-right"></i>
  Show All Publications
</a>

<div class="news-travel" markdown="1">


## Latest News

<div class="news" markdown="1">
<table>
<tbody>
{% for news in site.data.news limit:10 %}
  {% include news.html travel=news %}
{% endfor %}
</tbody>
</table>
</div>

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

<!-- <div class="travel" markdown="1">
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
</table> -->

<!-- </div> -->

</div>
