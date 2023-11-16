# Data Analytics with Apache Beam

## Description

![High level architecture](images/High_level_Arch.png "High Level Architecture")

The main aim of analytics engine is to get data from mqtt broker in stream format and apply rules on incoming data in real time and produce alert/action on mqtt broker. Getting data through pipeline and applying analysis function is done by using Apache Beam.

###  Apache Beam

Apache Beam is an open source, unified model for defining both batch and streaming data-parallel processing pipelines. Using one of the open source Beam SDKs, we can build a program that defines the pipeline.


#### Why use Apache Beam for analytics

There are many frameworks like Hadoop, Spark, Flink, Google Cloud Dataflow etc for stream processing. But there was no unified API to binds all such frameworks and data sources. It was needed to abstract out the application logic from these Big Data frameworks. Apache Beam framework provides this abstraction between your application logic and big data ecosystem.
- A generic dataflow-based model for building an abstract pipeline which could be run on any runtime like Flink/Samza etc.
- The same pipeline code can be executed on cloud(eg. Huawei Cloud Stream based on Apache Flink) and on the edge with a custom backend which can efficiently schedule workloads in an edge cluster and perform distributed analytics.
- Apache Beam integrates well with TensorFlow for machine learning which is a key use-case for edge.
- Beam has support for most of the functions required for stream processing and analytics.



