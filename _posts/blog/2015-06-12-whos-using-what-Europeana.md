---
published: false
layout: blog-item
category: blog
permalink: blog/whos-using-what-Europeana
title: Who's Using What - Europeana  Developers Profile
imageurl: 
  - "/img/blog/2015-03-20-whos-using-what-benjamin-rokseth.jpg"
tags: 
  - FLOSS
secondarytags:
  - Europeana
---
##Europeana and Development Lead Bram Lohman

The Europeana team consists of around 10 developers, ranging from back-end developers to front-enders, a sys-admin and tester. Our main developments are the [Europeana Portal](europeana.eu) and the home-grown ingestion system called [UIM](https://github.com/europeana/uim-europeana) (based on the OSGI framework), as well as several other tools to support our business needs (such as [REPOX](https://github.com/europeana/REPOX), [Europeana Cloud](https://github.com/europeana/Europeana-Cloud)). All of these can be found on our [GitHub](https://github.com/europeana)

Most of our back-end is in [Java](https://java.com/en/), and we have a [JavaScript](https://www.javascript.com/) front-end, but in the near future there are major changes underway that will see us using other languages, such as [Ruby](https://www.ruby-lang.org/en/) and more.

### What open source tools are you currently working with?
To support our development process we use the 'standard' tools: [Jenkins](https://jenkins-ci.org/), [Git](https://git-scm.com/), [JUnit](http://junit.org/), [Apache Maven](https://maven.apache.org/), [Selenium](http://www.seleniumhq.org/), etc. The software itself uses [MongoDB](https://www.mongodb.org/), [Apache Solr](http://lucene.apache.org/solr/), [PostgreSQL](http://www.postgresql.org/), [Apache Tomcat](http://tomcat.apache.org/), [CloudFoundry](https://www.cloudfoundry.org/index.html), [JQuery](https://jquery.com/), and a slew of other tools, too many to name.

###What open source tools have you used in the past to develop larger applications?
We moved from [Subversion](https://subversion.apache.org/) to Git a while back, and although each developer has their own preference a lot are using the [Eclipse IDE](https://eclipse.org/downloads/). There is a a shift towards [IntelliJ](https://www.jetbrains.com/idea/), but these flavours of IDE tend to change with the seasons. 

###What are you currently developing?
We're revamping the Europeana Portal, basing it on [Blacklight](http://projectblacklight.org/), which is written in Ruby. We're also nearly moving the [Europeana Cloud](http://pro.europeana.eu/structure/europeana-cloud) into a beta release, which uses [Apache Storm](https://storm.apache.org/)/[Apache Zookeeper](https://zookeeper.apache.org/), [Apache Cassandra](http://cassandra.apache.org/) and [OpenStack Swift](http://docs.openstack.org/developer/swift/) amongst others.
We've also "officialy" taken on REPOX (version 3 upwards, there are too many variations on earlier version to be able to support them), and have made major improvements on it. We're integrating [Swagger](http://swagger.io/) in most of our software as well.

###What would you like to see developed?
There is a keen interest in [Android](http://developer.android.com/reference/android/os/package-summary.html) here, although we don't do any development of it ourselves. We'll soon be tackling our ingestion workflow system to leverage the Europeana Cloud, so any open-source tools we can re-use for that would be very welcome.
