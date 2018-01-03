# Splunk is fun!

Three main components of Splunk

1. Search heads  

2. indexers

3. Forwarders  


At the heart of splunk is the index. The index collects all the data. Think of the Indexer as a factory and data as raw material. As the data is entered the inspectors identify the data and then the workers put time stamps on those events. Then you enter a query in the search field using the Splunk query language. Splunk identifies all the issues. Splunk allows you to create graphs and pretty characteristics


Indexer processes machine data and organizes it by event. **Search Head** handles search requests from user and then distributes the requests to the indexers which does the searching on the data. The Search header then consolidates and enriches the data before returning them to the user. The Search Head also provides the dashboards and reports.
**Forwarders** consume data and send data to the indexers, require minimum resources and low performant. e.g. you can install the forwarder on a web server, so that the forwarder can send the data to the indexer.

**Splunk can scale**

In one single instance deployment can handle

* input

* Parsing

* Indexing

* Searching

Perfect env for proof of concept, personal use, learning, and for a small department.

In a prod env you will have to scale splunk to increase search and indexing capacity, you can cluster the search headers and indexers to increase search capacity.

## Install 'the Splunk on your local'

Apps are workspaces, built to work a particular problem domain and use case.

There are three main roles in Splunk
Rolls determine what the user can do in Splunk

1. Admin - create apps and create knowledge objects

2. Power User - can create and share knowledge objects for users of an app and do realtime searches

3. User Roll - can only see objects and those shared with them


Splunk Enterprise comes with two apps, home app, and the search & reporting is what will be used in this training. On a side note there are hundreds of splunk apps out there.

### The primary objective is to deliver applied engineering guidance along with Splunk Apps that act as reference implementation.

It is hoped that the guidance will help lower the entry barrier.

Here are the five guidance principles

      Proven: Based on real world experience, and validated by field engineers and partners.

      Authoritative: offers the best available advice, in context.

      Accurate: Technically validated and properly tested.

      Actionable: provides the steps to success.

      Relevant: Addresses a real world problem.

This guide covers a specific theme such as **UI design** or data onboarding. The three amigos for this project will be Splunk, WilSonWorks, AdamsAuth. AdamsAuth is new to Splunk enterprise.

AdamsAuth wishes to enable insights into how users are interacting with their AdamsAuth OAuth 2.0 service. And WilSonWorks wants to monitor secure document repos. These applications will be built using **Splunks Simple XML**

## WilSonWorks is a system integrator with the focus on being compliant.

Their consumers are business managers, compliance officers, auditors and investigators.


## AdamsAuth: is an Identity as a service infrastructure provider.
