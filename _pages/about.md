---
permalink: /
title: "About"
excerpt: "Biography"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---
{% include base_path %}

I am a Postdoctoral Research Associate in the Department of Electrical and Computer Engineering at Rice University. I work with [Prof. Santiago Segarra](http://segarra.rice.edu/) on machine learning for wireless networks, with a focus on using graph neural networks and reinforcement learning for resource allocation in wireless networks. My current research interests include next-generation wireless networks, machine learning for wireless communications, and network science.

I received Ph.D. degree in computer engineering from the Department of Computer Science and Engineering of University of Nebraska-Lincoln in 2019, under the guidance of [Dr. Mehmet C. Vuran](http://cse.unl.edu/~mcvuran/). My Ph.D. research is focused on [dynamic spectrum sharing]({{site.baseurl}}/portfolio/cognitive-radio-networks/), [large-scale wireless testbed and radio frequency machine learning](https://cpn.unl.edu/projects/cosec). Before my Ph.D program, I earned my B.Sc. and M.Sc. in Electronic Engineering from University of Electronic Science and Technology of China, and worked in ArrayComm and Ericsson developing 4th generation wireless base-stations.

My [CV]({{site.baseurl}}/files/zhongyuanzhao-cv.pdf)

Recent Posts
======

<ul>
{% assign posts = site.posts %}
{% for post in posts limit:5  %}
    {% include archive-single-talk-cv.html %}
{% endfor %}
</ul>

A little bit more about me
======

I also like finance, sports, and reading.