# Splunk is fun!

<<<<<<< HEAD
=======
https://www.youtube.com/watch?v=JQuzoceahww

>>>>>>> develop
Lets begin with common splunk commands ...

```
splunk help

splunk start

splunk stop

splunk restart

splunk status

splunk show splunkd-port

splunk show web-ports

splunk show servername

splunk show default-Hostname

splunk enable boot-start -user

```

Three main components of Splunk

1. Search heads  

2. indexers

3. Forwarders  

At the heart of splunk is the index. The index collects all the data. Think of the Indexer as a factory and data as raw material. As the data is entered the inspectors identify the data and then the workers put time stamps on those events. Then you enter a query in the search field using the Splunk query language. Splunk identifies all the issues. Splunk allows you to create graphs and pretty characteristics

**A little more about the Indexer**

  * Processes machine data, storing the results in Indexes as events enabling fast search and analysis.

  * As the Indexer indexes data, it creates a number of files organized in sets of directories by argument - contains compressed raw data and Indexes point(s) to the raw Data

**A little more on Search Heads**

  * Allows users to use the Search language to search the indexed Data

  * Distributes user search requests to the indexers

  * Consolidates the results and extract field value pairs from the events to the user

  * Knowledge Objects on the Search Heads can be created to extract additional fields and transform the data without changing the underlying Index Data.

  * Search Heads provide tools that enrich the search experience - i.e reports, visualization and dashboards

### Forwarders

Indexer processes machine data and organizes it by event. **Search Head** handles search requests from user and then distributes the requests to the indexers which does the searching on the data. The Search header then consolidates and enriches the data before returning them to the user. The Search Head also provides the dashboards and reports.
**Forwarders** consume data and send data to the indexers, require minimum resources and low performant. e.g. you can install the forwarder on a web server, so that the forwarder can send the data to the indexer.


more on Splunk Components -- Forwarders

      Splunk instances that consume and send data to the indexed

      Require minimal resources and have little impact on Performance

      Typically reside on the machines where the data originates

      Primary way data is supplied for Indexing

### Additional Splunk Components -

    * In addition to the 3 main Splunk processing components, there are some
    less-common components including :

### Deployment Server

### Cluster Master

### License Master

--------------------

## Deployment Servers --- Standalone

* Single Servers
  - All functions in a single instance of splunk
  -For testing, POC, personal use -- self-Learning
  -This is what you get when you download Splunk
  and install with default settings

  --Recommendation--
  -Have at least one test/dev setup your site.

## Deployment Servers --- basic

  **Splunk server**

    -Similar to server in Standalone configuration

    -Manage deployment of forwarder configurations

  **Forwarders**

    -Forwarders collect data and send it to splunk
    Servers

    -Install forwarders at data source (usually production
      servers)

## Splunk Deployment -- Multi instances

    -Increases indexing and searching capacity

    -Search management and index functions are split
    across multiple machines

## Splunk Deployment -- Increasing capacity

    * adding a search head cluster:
        -services more users for increased search capacity

        -allows users and searches to share resources

        -Coordinate their activities to handle search
        requests and distribute the requests across
        the set of indexers

    **Search Head Clusters** - require a min of 3 Search heads

    **A 'Deployer'** is used to manage and distribute apps to the
    members of the Search Head Cluster


## Splunk Deployment --Index Cluster

    * Traditional Index Clusters:
    --Configured to replicate Data
    --Prevent data loss  
    --Promote availability
    --Manage multiple indexers

    * Non-replicating Index Clusters
    --Offer simplified management
    --Do not provide availability or
    data recovery

---------------------------------------------------------------


**Splunk can scale**

In one single instance deployment can handle

* input

* Parsing

* Indexing

* Searching

Perfect env for proof of concept, personal use, learning, and for a small department.

In a prod env you will have to scale splunk to increase search and indexing capacity, you can cluster the search headers and indexers to increase search capacity.

## Install 'the' Splunk on your local

  -- Let's describe a Splunk installation

  -- Describe Splunk component installation

  -- Using Splunk Web Admin

  -- Identify common Splunk commands

  And last AND least -- identify splunk directory structure

**There are multiple Splunk Install Packages!**

They include -->

              Indexer (search peer)

              Search Heads

              Deployment Server

              License Master

              Heavy Forwarder

              Cluster Master

              Search Head Clusters

     **Installing Splunk Enterprise as an Indexer or Search Head is
     Identical as installing a single deployment instance**

     **The difference happens at the configuration level**

     - Installation as configuration is an interative and ongoing event as you build and scale your Deployment

     -Administrators need to be in control of the environment to fulfill emerging needs

     -Before installing Indexers or Search Heads make sure you have the right hardware requirements

Apps are workspaces, built to work a particular problem domain and use case.

There are three main roles in Splunk
Rolls determine what the user can do in Splunk

1. Admin - create apps and create knowledge objects

2. Power User - can create and share knowledge objects for users of an app and do real time searches

3. User Roll - can only see objects and those shared with them

Splunk Enterprise comes with two apps, home app, and the search & reporting is what will be used in this training. On a side note there are hundreds of splunk apps out there.


## More on Users and Roles -->

  * Splunk users are assigned roles

  * Roles determine capabilities and data access

  -- Out of the box - there are three main roles :

  **Admin**

  **Power**

  **User**

 * Remember that Splunk admins can create additional Roles

## So what are Apps?

    * Apps allow different workspaces tailored to a specific use case
    or user role, to exist on a single Splunk instances

Focus on the Search & Reporting App ( also called the Search App )

Administrators can create or install additional apps to their Splunk instances
from http://splunkbase.splunk.com


## Navigating the Splunk Landing Page -- Home App

Click on the Splunk logo which will return the user to the default app.
The default is the Launcher apps

After you've built dashboards with your data, you can choose one to appear
in your Launcher App.


## Search & Reporting App

  * Provides a default interface for searching and analyzing Data

  * Enables you to create knowledge objects, reports, and dashboards

  * Access by selecting the Search and Reporting button on the Home view
  or from an app view, select Apps, then select Search & Reporting


## Adding Data --

<<<<<<< HEAD
Administrators ca
=======
Administrators can access the Add Data menu by clicking the Add Data icon located on the
Splunk Enterprise home app

## Add Data menu

Add Data menu provides three options depending on the source to be Used

  **Upload option**

  Upload options allows users to upload local files that **only get indexed once.**
  Useful for testing or data that is created only once and is never updated.

  **Monitor Option** -

  Monitors files, directories, http events, network ports, or data gathering Scripts
  located on Splunk Enterprise instances.

  **Forward Option**

  Main source of input in most production environments. Installed on remote machines where Data
  is gathered on forwarded to an index over a receiving port.


## Additional Data input Management options

  - Data can also be added and managed by:

    **Settings > Data** Inputs below the Data headers

    **Splunk CLI**

    Editing - .conf files

## Set Sourcetype :

Data assigned by splunk will be assigned a pre-trained sourcetype, such as .csv

Using the **Source Type** dropdown menu, you can change the data to a different
predifined source type or create a new one.

## Adjusting Time Stamps and Event Breaks

Adjustments can be made to time stamps and event breaks by using the corresponding drop-down-menus.

*note the menu will change according to source type*

## How Splunk Uses Sourcetypes with data

    **Sourcetype** -- is Splunk's way of categorizing the type of data

    - Splunk indexing processes frequently reference Sourcetype
    -Many searches, reports, dahshboards, apps, etc.. also rely on Sourcetype
    - When using predefined sourcetypes, Splunk knows where to break the event,
    the location of the timestamp and automatically create field value pairs

## How Splunk Uses Sourcetypes with Data

    * When Splunk does not have a predifined way to break events, it looks for a time stamp to break the data.

    - In the case of multiple time stamps, a regular expression can be used to extract the desired time.

    -Regular expressions can be used with any expected patterns in the data to create a line break  


## Saving Sourcetypes

  * Devs have the following options to save Sourcetypes


## Using the Upload Option
  Is ideal for testing and searching small datasets that are not updated



>>>>>>> develop


### SOURCE TYPE is used for categorizing and indexing Data

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
