---
permalink: /
title: "Welcome!"
excerpt: "Biography"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---
{% include base_path %}

As a postdoc researcher at Rice University, I'm always on a journey of discovery. My current research leverages the power of machine learning to make wireless networks and distributed systems more alive, adaptable, and <span class="tooltip">fun<span class="tooltiptext">This is important for technological advancement and talent attraction.</span></span>. [This](#chatgpt) is how ChatGPT explains it. I have worked on a list of topics including autonomous networking, AI radio, cloud radio access networks, dynamic spectrum access, and vehicular communications. Checkout the [ highlight](#highlight) and [list of publications](/publications/) to learn more. 

Throughout my academic career, I've had the privilege of working with esteemed advisors including [Santiago Segarra](http://segarra.rice.edu/) (19-present), [Mehmet C. Vuran](http://cse.unl.edu/~mcvuran/) (13-19), [Zishu He](https://ieeexplore.ieee.org/author/37086032055) (06-09), and [Zhuming Chen](https://ieeexplore.ieee.org/author/37291477800) (04-06). Their mentorship has helped me become the researcher I am today, and I'm always grateful.

When not immersed in research, I enjoy reading, [finance](/portfolio/business-education/), and sports. I especially appreciate the Olympic Motto, "Citius, Altius, Fortius," which means "faster, higher, braver." I believe it encapsulates the spirit of always striving for improvement and pushing ourselves to be our best.

Feel free to reach out through my GitHub, email, or LinkedIn. Thanks for visiting!

[Curriculum vitae]({{site.baseurl}}/files/zhongyuanzhao-cv.pdf) 

-----

Current and recent research topics <a name="highlight"></a>
======
 
- Automomous networking ([ICLR'23](https://openreview.net/forum?id=yHIIM9BgOo), [IEEE TWC](https://ieeexplore.ieee.org/document/9962800) ([arXiv](https://arxiv.org/abs/2109.05536)), ICASSP'[22a](https://doi.org/10.1109/ICASSP43922.2022.9746926), [22b](https://doi.org/10.1109/ICASSP43922.2022.9747437), [21](https://doi.org/10.1109/ICASSP39728.2021.9414098), ) -- focus on graph (network)-based machine learning for distributed decisions & discrete problems
- AI radio: a neural OFDM receiver ([IEEE JSAC](https://doi.org/10.1109/JSAC.2021.3087241), [arXiv](https://arxiv.org/abs/1810.07181), [git](https://github.com/zhongyuanzhao/dl_ofdm), [post](/publications/2018-10-23-Deep-Waveform.html))
- Cloud radio access networks ([j.adhoc](https://doi.org/10.1016/j.adhoc.2020.102305), [post](/publications/2020-10-23-CoSeC-RAN.html))
- Dynamic spectrum access ([IEEE TVT](https://doi.org/10.1109/TVT.2019.2892867), [post](/publications/2019-02-01-CogTV.html); [M&SOM](https://doi.org/10.1287/msom.2018.0727), [manuscript](http://cbafiles.unl.edu/public/cbainternal/facStaffUploads/MSOM-template-final.pdf))
- Vehicular communications ([j.comcom](https://doi.org/10.1016/j.comcom.2018.05.009), [post](/publications/2018-09-01-Vehicle-to-Barrier.html))


News & Blogs <i class="fa fa-rss" aria-hidden="true"></i>
======

<ul>
{% assign posts = site.posts %}
{% assign news = site.news | concat: posts | sort: "date" | reverse %}

{% for post in news limit:10  %}
    <li>      
    {% if post.date %}<i style="color: gray;font-size: 0.7em;">{{ post.date | date: '%Y-%m-%d' }}</i> {% endif %}
    {% if post.collection == "news" %}
    {% else %}
      <i class="fa fa-bookmark" aria-hidden="true"></i>
    {% endif %}
	  <span class="archive__item-title" itemprop="headline">
    {% if post.link %}
        <a href="{{ post.link }}">{{ post.title }}</a> <a href="{{ base_path }}{{ post.url }}" rel="permalink"><i class="fa fa-link" aria-hidden="true" title="permalink"></i><span class="sr-only">Permalink</span></a>
    {% else %}
        <a href="{{ base_path }}{{ post.url }}" rel="permalink">{{ post.title }}</a>
    {% endif %}
    </span>
    </li>
{% endfor %}
</ul>
[more...](/news/)


ChatGPT explains machine learning for wireless systems using [Tom Scott](https://www.youtube.com/@TomScottGo)'s style.<a name="chatgpt"></a>
======

>Machine learning has become a crucial player in wireless communications and networking in recent years. Essentially, it helps these systems make predictions and decisions more efficiently, leading to better performance, lower costs, and improved user experiences.
>
>Imagine you're a wireless network trying to serve a large crowd at a concert. With traditional methods, you might struggle to manage all the devices and data flying around, leading to slow connections, dropped calls, and unhappy customers.
>
>Enter machine learning! By using algorithms that can learn from past data and experiences, the network can better understand how to allocate its resources, prioritize different types of traffic, and optimize signal quality. It's like having a smart, data-driven traffic cop helping manage the crowd and ensure everyone has a good time.
>
>And the cool thing is, machine learning can keep learning and adapting, meaning it can keep improving over time as it handles more data and encounters new challenges. So, in a nutshell, machine learning helps wireless networks make smarter decisions and provide a better experience for users.

