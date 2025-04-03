---
name: Search portal Nuohtti
layout: page
tools: [HTML, CSS/LESS, Bootstrap, Javascript, jQuery, PHP]
image: assets/images/dasha/dasha-thumbnail.jpg
description: Web application to view digitized archival material related to Sámi culture.
# external_url: https://www.google.com
---

# Search portal Nuohtti

1–6 / 2021

In project *Digital Access to the Sámi Heritage Archives* I was part of techical team to build search portal [Nuohhti](https://www.nuohtti.com/?lng=fi). My employer was the University of Oulu. The project lasted several years but I was hired at the end of it.

Main part of my job was to design, implement and test [an interactive view](https://www.nuohtti.com/Content/material-survey-results) as part of the
search portal. It was used to publish the results of the material survey
conducted by part of the project. I also did manual testing and UI enhancements for the main site. User interfaces I made are fully responsive, multilingual and accessible.

Techniques I used: HTML, Javascript, LESS / CSS, Bootstrap, jQuery, PHP.

![results](assets/images/dasha/results.jpg)

In material survey search view user can set filtering criteria. The results are
converted from Excel spreadsheet source material to web format. Results include a description, links, and show what types of materials are available as badges. Descriptions can contain URL -links. If materials are available in the search portal, link to it is provided.
![results](assets/images/dasha/intro.jpg)

I also did intro page to material survey. Text, color scheme and images were
predetermined. I also did two column layout but single column version was ultimately chosen for publication.

![results](assets/images/dasha/menu.jpg)

User can select country filter either by generated dropdown -menu or by selecting
it in the map. Menu and map are synchronised using javascript and are responsive. I made the clickable vector map using [JQVmap](https://www.10bestdesign.com/jqvmap/) -Javascript library.


![results](assets/images/dasha/search.jpg)

User can also filter results by different material types.

![results](assets/images/dasha/mobile.jpeg)

All the pages are fully responsive and useable by touch.

{% include elements/button.html link="#" text="Back to start" block=true %}
