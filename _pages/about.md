---
permalink: /
title: "Hi, I'm Zhongyuan, "
excerpt: "Biography"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---
{% include base_path %}

a postdoc in the [ECE department](https://eceweb.rice.edu/) at Rice University. I am generally interested in systems and my research covers wireless communications, signal processing, and machine learning (artifical intelligence). Here are a few topics I recently worked on: 
- automomous networking with deep learning on graphs (networks) ([arXiv](https://arxiv.org/abs/2109.05536), [ICASSP](https://doi.org/10.1109/ICASSP39728.2021.9414098))
- radio frequency machine learning ([IEEE JSAC](https://doi.org/10.1109/JSAC.2021.3087241), [arXiv](Preprint), [git](https://github.com/zhongyuanzhao/dl_ofdm), [post](/publications/2018-10-23-Deep-Waveform.html))
- cloud radio access networks ([j.adhoc](https://doi.org/10.1016/j.adhoc.2020.102305), [post](/publications/2020-10-23-CoSeC-RAN.html))
- dynamic spectrum access ([IEEE TVT](https://doi.org/10.1109/TVT.2019.2892867), [post](/publications/2019-02-01-CogTV.html))
- vehicular communications ([j.comcom](https://doi.org/10.1016/j.comcom.2018.05.009), [post](/publications/2018-09-01-Vehicle-to-Barrier.html))

My past and current work seeks to make wireless communications more alive and fun (both the outcome and the process of research), rather than just a collection of (dead) standards and protocols. 
I am also interested in deep learning itself and its applications beyond radio. 

My current advisor is [Santiago Segarra](http://segarra.rice.edu/), and I finished my Ph.D. program under the advise of [Mehmet C. Vuran](http://cse.unl.edu/~mcvuran/) (13-19). A few years back, I was advised by [Zishu He](https://ieeexplore.ieee.org/author/37086032055) in a research-based master program (06-09), and by [Zhuming Chen](https://ieeexplore.ieee.org/author/37291477800) in China's national undergraduate electronic design contest (2005), in which my team was awarded the national 1st-class prize.


[Curriculum vitae]({{site.baseurl}}/files/zhongyuanzhao-cv.pdf)

Recent 
======

<ul>
{% assign posts = site.posts %}
{% assign news = site.news | concat: posts | sort: "date" | reverse %}

{% for post in news limit:20  %}
    <li>      
	<span class="archive__item-title" itemprop="headline">
      {% if post.link %}
        <a href="{{ post.link }}">{{ post.title }}</a> <a href="{{ base_path }}{{ post.url }}" rel="permalink"><i class="fa fa-link" aria-hidden="true" title="permalink"></i><span class="sr-only">Permalink</span></a>
      {% else %}
        <a href="{{ base_path }}{{ post.url }}" rel="permalink">{{ post.title }}</a>
      {% endif %}
    </span>
    {% if post.date %}<i style="color: gray;font-size: 0.7em;">{{ post.date | date: '%B %d, %Y' }}</i> {% endif %}
    </li>
{% endfor %}
</ul>

A little bit more about me
======

I also like finance, sports, and reading.