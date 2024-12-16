# Real-Time Data Processing Pipeline

Welcome to the **Real-Time Data Processing Pipeline** repository! This project focuses on building an efficient pipeline for real-time data ingestion, processing, storage, and visualization, leveraging cutting-edge big data technologies.

---

## Project Overview

This project demonstrates how to fetch data from external APIs, process it in real-time, store it in a distributed database, and visualize the insights using a dashboard. The primary use case focuses on processing financial data.

### Key Features:
- **Data Ingestion:** Fetching data from Financial Modeling Prep API.
- **Data Processing:** Using Apache Kafka for streaming and Apache Spark for processing.
- **Data Storage:** Storing processed data in HBase.
- **Data Visualization:** Syncing data to ElasticSearch and visualizing it using Kibana.

---

### Components:
1. **Zookeeper (3.4.14):** Coordination service for Kafka.
2. **Kafka (2.11_2.4.1):** Stream processing platform for real-time data ingestion.
3. **Spark (1.6.0) & Spark SQL:** Real-time data processing and querying.
4. **HBase (1.2.0):** Distributed database for storing processed data.
5. **Logstash (7.13.4):** Data pipeline for syncing HBase data with ElasticSearch.
6. **ElasticSearch (6.8.13):** Search engine for indexed data.
7. **Kibana (6.8.13):** Visualization tool for ElasticSearch data.

---

## System Workflow

1. **Data Source:** Financial data is fetched from the Financial Modeling Prep API.
2. **Data Ingestion:** 
    - Kafka is used to produce and consume data streams.
    - Connectors (`connect-standalone.bat`) are configured for seamless integration.
3. **Data Processing:**
    - Spark Streaming consumes data from Kafka.
    - Processed data is prepared for storage.
4. **Data Storage:**
    - HBase is used for storing structured, real-time data.
5. **Data Synchronization:**
    - Logstash syncs HBase data with ElasticSearch.
6. **Data Visualization:**
    - Kibana dashboards are set up for real-time data insights.

---

## Installation and Setup

### Prerequisites:
Ensure the following technologies are installed:
- **Java 8**
- **Zookeeper**
- **Kafka**
- **Spark**
- **HBase**
- **Logstash**
- **ElasticSearch**
- **Kibana**

### Steps to Run:
1. **Start Zookeeper**
    ```
    bin/zkServer.sh start
    ```
2. **Start Kafka**
    ```
    bin/kafka-server-start.sh config/server.properties
    ```
3. **Start Data Flow:**
    ```
    java -jar DataFlowProgram.jar
    ```
4. **Start Logstash:**
    ```
    logstash.bat -f hbase2CloudES.conf
    ```
5. **Run ElasticSearch and Kibana:**
    ```
    ./elasticsearch
    ./kibana
    ```

---

## Future Enhancements
- Implement machine learning models for predictive analytics.
- Add support for additional data sources.
- Optimize performance for larger datasets.

---
