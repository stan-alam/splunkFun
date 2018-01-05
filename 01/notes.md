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

## SOURCE TYPE is used for categorizing and indexing Data

4. Adding Data in.

There are many ways to get data into SE. Your options are very large. Click on the Add Data icon. You get three options
1. Upload - good for data that gets uploaded/indexed once.

2. Monitor - allows you to monitor files, https events, file events, windows events -- if on windows machine, network, performance.

3. Forwarders - are installed on remote machines, on prod envs Forwarders are the main supply of data.

    You can add data by drag and drop, if data is static just upload it.
    e.g. .csv file. small data sets. Splunk uses source types to categorize the
     kind of data for indexing.
    Used in many search functions. Here it labels the data as .csv type.
    You can adjust how SE creates the timestamp at break events.
    You can save the source type, change the name, save as some other name.
    add description and app type - instrumentation, monitoring and console,
    search, system.

    Hostname is the machine from which the events originate.
    You can enter host field value with regex, the constant value, wildcards
    with partial name.
    Index are directory where the data is stored. Do not store all the data
    in the main index.

    Having separate indexes will make searches faster.
    Multiple indexes also allows you to differentiate views between roles,
    you can set retention policies on different indexes.

    being able to use the index for the search string, will help a lot in
    querying and focusing on certain events in certain index.

    By clicking submit you can index.

    The App selection dropdown allows you to select "Instrumentation,"
    "Monitoring," "Search & Reporting", "System."

    Which app to apply source type to...

    Upload is good for testing and learning. You can upload by selecting the
    file or drag and drop.

## When the data you want to index comes from files or ports on an indexer

### use the Monitor option


Using the monitor option -- you are brought to the monitor screen. There you can select

-Files and Directories-

-HTTP Event Collector-

-TCP/UDP-

-Scripts-

You have the ability to monitor continuously, you can monitor files by black list and white list options.


Let's say we're monitoring an apache log file, select the files. You can whitelist and blacklist directories to be selective what you want to save.

You select the hostname but unlike the upload option **you can also select which app context to use for the input** Clicking review will display the settings for the input and clicking submit will start indexing the data.



### The primary objective is to deliver applied engineering guidance along with Splunk Apps that act as reference implementation.

It is hoped that the guidance will help lower the entry barrier.

Here are the five guidance principles

      Proven: Based on real world experience, and validated by field engineers and partners.

      Authoritative: offers the best available advice, in context.

      Accurate: Technically validated and properly tested.

      Actionable: provides the steps to success.

      Relevant: Addresses a real world problem.

This guide covers a specific theme such as **UI design** or data onboarding. The three amigos for this project will be Splunk, WilSonWorks, AdamsAuth. AdamsAuth is new to Splunk enterprise.

AdamsAuth wishes to enable insights into how users are interacting with their AdamsAuth OAuth 2.0 service. And WilSonWorks wants to monitor secure document repos. These applications will be built using **Splunk's Simple XML**

## WilSonWorks is a system integrator with the focus on being compliant.

Their consumers are business managers, compliance officers, auditors and investigators.


## AdamsAuth: is an Identity as a service infrastructure provider.

The team members will include the following titles

1. Dev - expert user of splunk and developing splunk apps. It is imperative to make sure that the splunk app is well written.

2. Architect - wants to see a well-architected solution.

3. UX - a designer who wants to see an engaging, intuitive easy-to-use UI.

4. Test - A tester who wants to ensure the highest possible quality for the reference of implementation.

5. System Admin - wants to know how to deploy and monitor the apps, and wants to understand how to configure them.

6. Business Analysts - A representative
