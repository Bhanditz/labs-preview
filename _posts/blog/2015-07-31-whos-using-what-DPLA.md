---
published: false
layout: blog-item
category: blog
permalink: blog/whos-using-what-DPLA
title: Who's Using What - Mark Matienzo and DPLA Developer Profile
imageurl: 
  - ""
tags: 
  - FLOSS
secondarytags:
  - DPLA
---
##Mark Matienzo and the DPLA
The [DPLA](http://dp.la/) has been making waves in the digital heritage sector since their official beginning in 2013. Their goal isn't much different than Europeana's, providing easy digital access to a large aggregated corpus of digitised heritage materials. DPLA built their [Metadata Application Profile](http://dp.la/info/developers/map/) (MAP) off of Europeana's EDM and have subsequently collaborated with Europeana on [International Rights Statements](http://pro.europeana.eu/blogpost/the-principles-for-establishing-international-interoperable-righ) and [putting them into action](http://pro.europeana.eu/blogpost/developing-and-implementing-a-technical-framework-for-interopera). But what drew me to the DPLA was something I heard at EuropeanaTech 2015 in Paris. There, DPLA Director Dan Cohen said in his wonderful presentation that the DPLA development team names all their tools after goats because "they're curious and consume everything". Well those sounded like developers I needed to talk to. So without further ado, read our interview with Mark Matienzo from the DPLA.  

*[Mark Matienzo](http://matienzo.org/) is the Director of Technology for the Digital Public Library of America. Prior to joining DPLA, Matienzo worked as an archivist and technologist specialising in born-digital materials and metadata management, at institutions including the Yale University Library, The New York Public Library, and the American Institute of Physics. Matienzo received a MSI from the University of Michigan School of Information and a BA in Philosophy from the College of Wooster, and was the first awardee (2012) of the Emerging Leader Award of the Society of American Archivists.*

### What open source tools are you currently working with?

Most of the current development work we’re doing is built using [Ruby on Rails](http://rubyonrails.org/), the [PostgreSQL](http://www.postgresql.org/) database system, and [Apache Solr](http://lucene.apache.org/solr/) or [Elasticsearch](https://www.elastic.co/) for indexing. For our metadata projects, such as to support ingestion and metadata enhancement, we’ve been using [Apache Marmotta](http://marmotta.apache.org/) as our triple store, and [ActiveTriples](https://github.com/ActiveTriples/ActiveTriples) to help with modeling RDF objects in Ruby code. We’re excited to start doing more with [Blacklight](http://projectblacklight.org/) and [Hydra](http://projecthydra.org/) as well. We also use [Ansible](http://www.ansible.com/home) for deployment and automation, and [Redmine](https://www.redmine.org/) for tracking issues.

### What open source tools have you used in the past to develop larger applications?

We’ve used a variety of tools, including [Omeka](http://omeka.org/), [Akara](http://akara.info/), and some of the same previous tools mentioned.

### What are you currently developing? 

All of DPLA’s current public projects are available on [our Github account](https://github.com/dpla). Most of our work has been going towards [Heiðrún](https://digitalpubliclibraryofamerica.atlassian.net/wiki/display/TECH/Heidrun) and [Krikri](https://github.com/dpla/KriKri) (parts of our new metadata ingestion system that’s been under development since October 2014). We’re also just beginning a project, called "[Hydra in a Box](http://dp.la/info/2015/04/15/far-reaching-hydra-in-a-box-joint-initiative-funded-by-imls/)", with Stanford University and DuraSpace, to develop a turnkey repository system built on the Hydra framework. 

### What would you like to see developed?

Our largest need are high-performance storage and querying solutions for RDF data. We’re particularly excited about work going into [Linked Data Fragments](http://linkeddatafragments.org/), but we’re hoping that there are more implementations that will be under way. We’d also like to see more convergence around developing shared metadata enhancement tools or common APIs for developing them, such as for geocoding and alignment of terms with authority files and vocabularies.

For more information about the DPLA read Joris Pekel's [interview with Dan Cohen from EuropeanaTech 2015](http://pro.europeana.eu/blogpost/looking-to-the-future-with-the-dpla-an-interview-with-dan-cohen).
