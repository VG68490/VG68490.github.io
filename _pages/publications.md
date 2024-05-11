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

![Map of Roads and Parking Lots in Glacier National Park](/images/Glacier2.jpg)
<p> A map displaying points, lines, and polygons of parking lots, roads, and the Glacier Naitonal Park. <p> 

![Median House Prices in Various U.S Counties](/images/counties_data.png)
