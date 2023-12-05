# Data Analytics with Apache Beam

## Description

![High level architecture](images/High_level_Arch.png "High Level Architecture")

The main aim of analytics engine is to get data from mqtt broker in stream format and apply rules on incoming data in real time and produce alert/action on mqtt broker. Getting data through pipeline and applying analysis function is done by using Apache Beam.

###  Apache Beam

Apache Beam is an open source, unified model for defining both batch and streaming data-parallel processing pipelines. Using one of the open source Beam SDKs, we can build a program that defines the pipeline.


#### Demo 1.1 [Real-time alert]:Read batch data from MQTT,filter and generate alerts
- Basic mqtt read/write support in Apache Beam for batch data
- Reads data from an mqtt topic
- Create PCollection of read data and use it as the initial data for pipeline
- Do a filtering over the data
- Publish an alert on a topic if reading exceeds the value
![Demo1.1](images/Demo1.1.png "Demo1.1:Read batch data from MQTT,filter and generate alerts")

#### Demo 1.2 [Filter Streaming Data]: Reads streaming data from MQTT, filter at regular intervals
- Read streaming data using MQTT
- Do a filtering over the data at fixed time intervals
![demo1.2](images/Demo1.2.png "Demo1.2:Reads streaming data from MQTT, filter at regular intervals")

### Prerequisites
- Golang(version: 1.14+)
- KubeEdge(version: v1.5+)
- Docker(version: 18.09-ce+)

