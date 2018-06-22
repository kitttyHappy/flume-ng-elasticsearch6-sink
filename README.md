# Flume 1.8.0 supporting ElasticSearch 6.2.4
Base on: https://github.com/arberzal/flume-ng-elasticsearch2-sink

This version of the Flume ElasticSearch sink works with ElasticSearch 6.2.4
but to do so, **some libraries used by Flume had to be updated to the newest
versions**,  **For this reason, many tests do not work retuning a pretty "jar
hell" exception.**

As Flume is packaged right now (sink and flume libraries in the  same class 
loader) seems difficult to find another solution. The best way, without
modifying Flume, would be a new ElasticSearch sink based on http API and 
built on top of a reactive framework.

## Modifications to your Flume lib path:
    
### Libraries to be added:
##### this project
- flume-ng-elasticsearch6-sink-1.8.0.jar

##### common library
- t-digest-3.0.jar
- guava-11.0.2.jar
- hppc-0.7.1.jar
- httpclient-4.2.1.jar
- httpcore-4.2.1.jar
- jackson-annotations-2.8.1.jar
- jackson-core-2.8.9.jar
- jackson-databind-2.8.9.jar
- jackson-dataformat-cbor-2.8.10.jar
- jackson-dataformat-smile-2.8.10.jar
- jackson-dataformat-yaml-2.8.10.jar
- joda-convert-1.2.jar
- joda-time-2.9.4.jar
- snakeyaml-1.17.jar

##### elasticsearch-6.2.4, plugins & dependencies
- elasticsearch-6.2.4.jar
- elasticsearch-core-6.2.4.jar
- lang-mustache-client-6.2.4.jar
- percolator-client-6.2.4.jar
- reindex-client-6.2.4.jar
- lucene-core-7.2.1.jar
- lucene-highlighter-7.2.1.jar
- lucene-join-7.2.1.jar
- lucene-queries-7.2.1.jar
- lucene-queryparser-7.2.1.jar
- lucene-sandbox-7.2.1.jar

##### transportClient dependencies
- transport-6.2.4.jar
- transport-netty4-client-5.0.0.jar
- netty-3.9.4.Final.jar
- netty-buffer-4.1.16.Final.jar
- netty-codec-4.1.16.Final.jar
- netty-common-4.1.16.Final.jar
- netty-resolver-4.1.16.Final.jar
- netty-handler-4.1.16.Final.jar
- netty-transport-4.1.16.Final.jar

##### log4j2 dependencies
- log4j-1.2.17.jar
- log4j-api-2.9.1.jar
- log4j-core-2.9.1.jar

#### avro dependencies
- jackson-dataformat-cbor-2.8.10.jar

### Libraries to be removed:
- flume-ng-elasticsearch-sink-1.8.0.jar
