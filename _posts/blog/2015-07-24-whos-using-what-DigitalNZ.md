---
published: false
layout: blog-item
category: blog
permalink: blog/whos-using-what-DigitalNZ
title: Who's Using What - Chris McDowall and DigitalNZ  Developer Profile
imageurl: 
  - "/img/blog/2015-03-20-whos-using-what-benjamin-rokseth.jpg"
tags: 
  - FLOSS
secondarytags:
  - DigitalNZ
---
Over the next three weeks we will present special "Who's Using What?" interviews with the development teams from three of the world's leading aggregators, protectors, and advocates for digital cultural heritage, [DigitalNZ](http://digitalnz.org/), [DPLA](http://dp.la/), and our very own [Europeana](http://www.europeana.eu/portal/). For any developer or instituion currently working on, or planning to manage such massive digital collections and succesfully re-present them to the global public, these three development teams combined hold an unprecedent amount of expertise and they do it all while using open source software. Read here what tools these teams are favouring, what they've made for the world to improve upon and use, and what they hope to see in the future. Up first, Chirs McDowall and the development team from DigitalNZ! 

## Chris McDowall and DigitalNZ

The National Library of New Zealand's [DigitalNZ](http://digitalnz.org/) team makes New Zealand's digital content available to find, share and use. Like Europeana, DigitalNZ aggregates metadata from many digital collections so it is available to search and also encourages the development of new discovery experiences through an [open API](http://digitalnz.org/developers). The team works with the collections from a wide range of organisations across the cultural sector, community groups, businesses and media organisations.  It also brings in metadata relevant to New Zealand from Europeana and DPLA. DigitalNZ is almost eight years old and its most recent development is the release of [Supplejack](http://digitalnz.github.io/supplejack/), an open source tool for aggregating, searching and sharing metadata records.  Supplejack collects metadata about millions of items from hundreds of data sources. The tool transforms messy data, creates a unified search index and makes the reconciled metadata widely available via an open API data service.

Chris McDowall is the manager of DigitalNZ Systems. He looks after the day to day running of the DigitalNZ infrastructure and coordinates feature development.

### What open source tools are you currently working with? 

Here is a list of the main open source tools we use. The true list would be much longer.

LANGUAGES/WEB FRAMEWORKS

- [Ruby](https://www.ruby-lang.org/en/) 
- [Rails](http://rubyonrails.org/)
- [jQuery](https://jquery.com/) 
- [SASS](http://sass-lang.com/)

DATABASES / DATA STORES / SEARCH

- [MongoDB](https://www.mongodb.org/)
- [MySQL](https://www.mysql.com/)
- [Redis](http://redis.io/)
- [Solr4](https://wiki.apache.org/solr/Solr4.0)

SERVERS

- [Apache](http://www.apache.org/)
- [Thin](http://code.macournoyer.com/thin/)

MISC

- [Git](https://git-scm.com/)
- [Chef](https://www.chef.io/)
- [Keepalived](http://keepalived.org/)

OUR HARVESTING / SEARCH PLATFORM

- [Supplejack](http://digitalnz.github.io/supplejack/)

### What open source tools have you used in the past to develop larger applications?

The tools mentioned above as well as a bunch that appear top of mind …

- [Python](https://www.python.org/)
- [Django](https://www.djangoproject.com/)
- [Flask](http://flask.pocoo.org/)
- [D3.js](http://d3js.org/)
- [PostgreSQL](http://www.postgresql.org/)
- [PostGIS](http://postgis.net/)
- [R](http://www.r-project.org/)
- [Bootstrap](http://getbootstrap.com/)
- [Angular.js](https://angularjs.org/)
- [Homebrew package manager](http://brew.sh/)
- [LINUX](https://www.linux.com/)!!!! (esp. [Ubuntu](http://www.ubuntu.com/) and [Mint](http://linuxmint.com/))

and lots of others I can’t think of right now ;)

### What are you currently developing? 

We are working on our open source metadata harvesting, aggregation and search platform called [Supplejack](http://digitalnz.github.io/supplejack/). Supplejack powers the DigitalNZ service. Its main purpose is to make it easy to aggregate heterogeneous data at scale and provide ways to surface that data so it is more useful. From a data management perspective there are several things you can do with Supplejack:

1.       Define common data schema that incoming data should map to
2.       Create search and database indexes that conform to your chosen schema
3.       Script instructions for extracting and mapping data from many different data sources
4.       Set up validation rules for your data harvesting activity
5.       Schedule data harvests to run at whatever frequency you like
6.       Run enhancement scripts to improve the quality or completeness of harvested data
7.       Deliver a public API of the standardised data
8.       Monitor API key activity and set query throttle rates
9.       View collected data on a demo website
10.      Supplejack was designed to provide assurance to the quality of data management activities when working at scale. 

### What would you like to see developed? 
Oh, that is a big question. My immediate answer is better and simpler tools for querying/exploring and visualising linked data.
