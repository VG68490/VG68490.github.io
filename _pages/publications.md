---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if site.author.googlescholar %}
  <div class="wordwrap">You can also find my articles on <a href="{{site.author.googlescholar}}">my Google Scholar profile</a>.</div>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}


<h2> Figure A:</h2>

![Map of Roads and Parking Lots in Glacier National Park](/images/Glacier2.jpg)
![Moran's I Graph](/images/moransi_graph.png)

<h2> Figure B: </h2>

![Median House Prices in Various U.S Counties](/images/counties_data.png)

<p> Figure A: Map displaying points, lines, and polygons of parking lots, roads, and the Glacier Naitonal Park. <p> 


<p> Figure B: A chart displaying the median and distribution of house prices in the U.S by county. </p>
