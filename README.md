streamsx.hbase
==============

This toolkit allows Streams to write tuples into HBase and to read tuples from [Apache HBase](https://hbase.apache.org/). 
Download the latest (version 2.0) [release](https://github.com/IBMStreams/streamsx.hbase/releases/tag/streams_4.1.0) of the toolkit for Streams 4.1.0.

## Connecting to HBase on  Bluemix with Streams 
Connecting to HBase in the BigInsights on Bluemix service requires the [HBase Toolkit for Bluemix](https://github.com/IBMStreams/streamsx.hbase/blob/bluemix/README.md).

## Overview
The toolkit includes the following operators, and at least one sample per operator:
*    HBASEPut, including checkAndPut support
*    HBASEGet
*    HBASEDelete, including checkAndDelete support
*    HBASEIncrement
*    HBASEScan

See the [documentation for operators and samples](http://ibmstreams.github.io/streamsx.hbase/com.ibm.streamsx.hbase/doc/spldoc/html/index.html) to learn more.

The toolkit has been tested with HBase 0.94.3 and Hadoop 1.1.0, but is expected to work for any later version of Hadoop or HBase.  

## Setup
To run these operators, you must install Apache HBase and its dependencies. An installation of IBM's BigInsights includes everything you need.  
Please see the individual product pages for instructions on installation. 
Once you have HBase installed, the operators need HBase configuration information in order to run.  It uses `hbase-site.xml` to do that.   You can supply that in two ways:
* You can set `HBASE_HOME`, the operator will look under `HBASE_HOME/conf/hbase-site.xml` for HBase configuration information.  This is probably the easiest thing to do if the operator is running on the HBase host.  
* You can copy hbase-site.xml from your HBase install's conf directory and then use `hbaseSite` parameter to point to `hbase-site.xml`.  You still need to set `HBASE_HOME`, but it need not point to anything, ie, `export HBASE_HOME=/dev/null`.



## Getting started
Download a [release](https://github.com/IBMStreams/streamsx.hbase/releases/tag/streams_4.1.0), or build the toolkit yourself from the source.  See the section below on how to build the toolkit.
The following applications in the `samples` directory are good starting points:
* PutSample
* PutRecord
* GetSample
* GetRecord

## Building the toolkit
The toolkit uses [Maven](http://maven.apache.org/) to download the needed dependencies.
* Set M2_HOME to point to the maven directory.
* Pick the correct pom file for your install.  In com.ibm.streamsx.hbase, there are three example pom files: 
      *  pom-v094.xml: HBase 0.94, hadoop 1
      *  pom-v096-hadoop1.xml, HBase 0.96, hadoop 1
      *  pom-v096-hadoop2.xml, HBase 0.96, hadoop 2
  Copy the correct file for your HBase and Hadoop install to pom.xml
* Run `ant` at the top level.  This will build the toolkit, but also download all the necessary jars into `opt/downloaded`.  These jars are used at toolkit build time, but also at the toolkit runtime.


## Troubleshooting
Please enter an issue on GitHub for defects and other problems.   

## Contributing
This repository is using the fork-and-pull model (https://help.github.com/articles/using-pull-requests).  If you'd like to contribute code, fork a copy of the repository, make changes, and when ready, issue a pull request.  For more details, see the wiki in the IBMStreams/toolkits repository.

## Releases
We will make releases after major features have been added.  If you wish to request a release, please open an issue.


## Learn more about Streams:
* [IBM Streams on Github](http://ibmstreams.github.io)
* [Introduction to Streams Quick Start Edition](http://ibmstreams.github.io/streamsx.documentation/docs/4.1/qse-intro/)
* [Streams Getting Started Guide](http://ibmstreams.github.io/streamsx.documentation/docs/4.1/qse-getting-started/)
* [StreamsDev](https://developer.ibm.com/streamsdev/)