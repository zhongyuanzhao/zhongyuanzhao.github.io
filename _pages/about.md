---
permalink: /
title: "I'm Zhongyuan, I do research in"
excerpt: "Biography"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---
{% include base_path %}

wireless communications and networks, with a focus on machine learning for the next generation wireless communications and networked systems in general. My current research interests include: 1) developing intelligent wireless networks with improved performance, efficiency, scalability, and autonomy, and 2) applying machine learning for various tasks in the context of networks, which can be of many types including physical, engineered, information, social, biological, and economic networks.


Currently, I am a Postdoctoral Research Associate in the Department of Electrical and Computer Engineering at Rice University. I work with [Santiago Segarra](http://segarra.rice.edu/) on autonomous networking, with a focus on resource allocation in wireless networks. 

I got Ph.D. degree in computer engineering from the University of Nebraska-Lincoln in 2019, under the guidance of [Mehmet C. Vuran](http://cse.unl.edu/~mcvuran/). My Ph.D. research is focused on [dynamic spectrum sharing]({{site.baseurl}}/portfolio/cognitive-radio-networks/), [large-scale wireless testbed and radio frequency machine learning](https://cpn.unl.edu/projects/cosec). Before my Ph.D program, I earned my B.Sc. and M.Sc. in Electronic Engineering from University of Electronic Science and Technology of China, and worked in ArrayComm and Ericsson developing 4th generation wireless base-stations.

I am actively searching for a job in academia or industry. Here is my [CV]({{site.baseurl}}/files/zhongyuanzhao-cv.pdf).

Recent Posts
======

<ul>
{% assign posts = site.posts %}
{% for post in posts limit:20  %}
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