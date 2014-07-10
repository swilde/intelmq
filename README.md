# IntelMQ

IntelMQ is a solution for CERTs to process data feeds, pastebins, tweets throught a message queue.


## How to Install

See [UserGuide](https://github.com/certtools/intelmq/blob/master/docs/UserGuide.md).


## Goals

* Reduce the complexity of system administration
* Reduce the complexity of writing new bots for new data feeds
* Reduce the probability of events lost in all process (even system crash)
* Provide easy communication with other systems via API
* Use and improve the existing Data Harmonization Ontology
* Use the existing AbuseHelper Event-like syntax: event.add("domain", "example.com")
* Use JSON format for all messages
* Use messages tags: report, abuse-event, pastebin, tweet
* Integration of the existing tools (AbuseHelper, CIF, etc...)

## System

### Main Components
* RabbitMQ as message queue for pipeline
* Redis as memcache for bots


### System Architecture

![System Architecture](http://i58.tinypic.com/n395bo.jpg)


### Code Architecture

![Code Architecture](http://s28.postimg.org/uwzthgqrx/intelmq_arch.png)


### System Details

* Configuration: ... details ...
* How to dedup using Redis TTL: ... details ...
* Experts using Redis as a cache and TTL: ... details ...
* RabbitMQ Queues: ... details ...


## Bots Available

### Input Bots
* [MalwareDomainList](https://github.com/certtools/intelmq/tree/master/src/bots/inputs/malwaredomainlist)
* [Arbor](https://github.com/certtools/intelmq/tree/master/src/bots/inputs/arbor) (Atlas Public)
* [VXVault](https://github.com/certtools/intelmq/tree/master/src/bots/inputs/vxvault)
* [AbuseHelper](https://github.com/certtools/intelmq/tree/master/src/bots/inputs/abusehelper)
* [CERT-EU](https://github.com/certtools/intelmq/tree/master/src/bots/inputs/certeu) (Mail)

### Expert Bots
* [TeamCymru IPtoASN](https://github.com/certtools/intelmq/tree/master/src/bots/experts/cymru) (DNS Service)
* [MaxMind GeoIP](https://github.com/certtools/intelmq/tree/master/src/bots/experts/geoip)
* [ContactDB](https://github.com/certtools/intelmq/tree/master/src/bots/experts/contactdb)
* [eCSIRT Taxonomy](https://github.com/certtools/intelmq/tree/master/src/bots/experts/taxonomy)
* [Events Deduplicator](https://github.com/certtools/intelmq/tree/master/src/bots/experts/deduplicator)
* [Events Sanitizer](https://github.com/certtools/intelmq/tree/master/src/bots/experts/sanitizer)

### Output Bots
* [Splunk](https://github.com/certtools/intelmq/tree/master/src/bots/outputs/logcollector)
* [MongoDB](https://github.com/certtools/intelmq/tree/master/src/bots/outputs/mongodb)
* [PostgreSQL](https://github.com/certtools/intelmq/tree/master/src/bots/outputs/postgresql)
* [ElasticSearch](https://github.com/certtools/intelmq/tree/master/src/bots/outputs/elasticsearch)
* [File](https://github.com/certtools/intelmq/tree/master/src/bots/outputs/file)

# Incident Handling Automation Project

* **URL:** http://www.enisa.europa.eu/activities/cert/support/incident-handling-automation
* **Mailing-list:** ihap@lists.trusted-introducer.org
