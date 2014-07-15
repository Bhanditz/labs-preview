---
published: false
layout: blog-item
category: blog
permalink: blog/2nd-Europeana-Creative-Challenge-workshop-Barcelona
title: "2nd Europeana Creative Challenge Workshop, Barcelona, 16 July 2014"
imageurl: 
  - "/img/blog/2014-07-16-2nd_Europeana_Creative_Challenge_workshop.jpg"
tags: 
  - "Europeana Creative"
  - challenge
---

This blog post has been created to support the [Europeana Creative Challenge workshop, Barcelona, 16 July 2014](/events/2nd-Europeana-Creative-Challenge-workshop-Barcelona/), held in association with Apps&Cultura.

It's also a place where you can post requests related to the API and the Challenge - just add comments below and we'll 

## Getting started
You should find everything you need to get started using the Europeana API in the Europeana Labs website.

### New to Europeana?
- explore our [sample datasets] to see exanples of just some of the openly licensed content that is available
- get inspiration from our [gallery of existing apps] to see what is possible

### New to the Europeana API?
- if you haven't already done so, [register for a Europeana API key](/api/registration/)
- take a little time to read the [Getting Started guide](/api/introduction/) to the Rest API 

### Give it a try
- our [API Console](/api/console/) allows you to easily build and test queries
- 

If you have any questions, just leave a comment below or 

## Hints & tips


### Retrieving media assets
Every item returned in a standard search call will have a url to a thumbnail e.g. "edmPreview": [
       "http://europeanastatic.eu/api/image?uri=http%3A%2F%2Fcoleccionfff.unav.es%2Fbvunav%2Fi18n%2Fcatalogo_imagenes%2Fimagen_id.cmd%3FidImagen%3D10000592&size=LARGE&type=IMAGE"
     ]


Hennings datasets

Client libraries

Hints and tips

Geo queries

Accessing original media
edmIsShownBy -  currently have to iterate through records; sniffer to detect file type
Show all records with something in edmIsShownBy
http://test.portal2.eanadev.org/api/v2/search.json?wskey=Lak7ykbsh&query=provider_aggregation_edm_isShownBy:*

Links to Console


Comments section?


---

<small>Image: [Opstand in Barcelona, 1640, Johann David Zunnern, 1701](http://europeana.eu/portal/record/90402/RP_P_1896_A_19368_1959.html?start=8&query=barcelona&startPage=1&qf=TYPE%3AIMAGE&qf=REUSABILITY%3Aopen&qf=provider_aggregation_edm_isShownBy%3A*&qf=PROVIDER%3ARijksmuseum&rows=24) from Rijksmuseum (Public Domain).</small>
