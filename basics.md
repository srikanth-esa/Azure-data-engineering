---
description: Concepts, Jargons etc., related to data
---

# BASICS

## Types of data <a href="#types-of-data" id="types-of-data"></a>

| Structured                                                                                                                                                                                                                                                                  | Semi-structured                                                                                                                                                                                                                   | Unstructured                                                                                                                                                                                                                                    |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![Diagram of Structured data type.](https://learn.microsoft.com/en-us/training/wwl-data-ai/introduction-to-data-engineering-azure/media/2-structured-data.png)                                                                                                              | ![Diagram of Semi-structured data type.](https://learn.microsoft.com/en-us/training/wwl-data-ai/introduction-to-data-engineering-azure/media/2-semi-structured-data.png)                                                          | ![Diagram of Unstructured data type.](https://learn.microsoft.com/en-us/training/wwl-data-ai/introduction-to-data-engineering-azure/media/2-unstructured-data.png)                                                                              |
| Structured data primarily comes from table-based source systems such as a relational database or from a flat file such as a comma separated (CSV) file. The primary element of a structured file is that the rows and columns are aligned consistently throughout the file. | Semi-structured data is data such as JavaScript object notation (JSON) files, which may require flattening prior to loading into your source system. When flattened, this data doesn't have to fit neatly into a table structure. | Unstructured data includes data stored as key-value pairs that don't adhere to standard relational models and Other types of unstructured data that are commonly used include portable data format (PDF), word processor documents, and images. |



## Data operations <a href="#data-operations" id="data-operations"></a>

&#x20;As a data engineer some of the main tasks that you'll perform in Azure include _data integration_, _data transformation_, and _data consolidation_.

### Data integration <a href="#data-integration" id="data-integration"></a>

![Diagram representing a data integration operation.](https://learn.microsoft.com/en-us/training/wwl-data-ai/introduction-to-data-engineering-azure/media/2-integration-data-operation.png)

Data Integration involves establishing links between operational and analytical services and data sources to enable secure, reliable access to data across multiple systems. For example, a business process might rely on data that is spread across multiple systems, and a data engineer is required to establish links so that the required data can be extracted from all of these systems.

### Data transformation <a href="#data-transformation" id="data-transformation"></a>

![Diagram representing a data transformation operation.](https://learn.microsoft.com/en-us/training/wwl-data-ai/introduction-to-data-engineering-azure/media/2-transformation-data-operation.png)

Operational data usually needs to be _transformed_ into suitable structure and format for analysis, often as part of an _extract, transform, and load_ (ETL) process; though increasingly a variation in which you _extract, load, and transform_ (ELT) the data is used to quickly ingest the data into a data lake and then apply "big data" processing techniques to transform it. Regardless of the approach used, the data is prepared to support downstream analytical needs.

### Data consolidation <a href="#data-consolidation" id="data-consolidation"></a>

![Diagram representing a data consolidation operation.](https://learn.microsoft.com/en-us/training/wwl-data-ai/introduction-to-data-engineering-azure/media/2-consolidation-data-operation.png)

Data consolidation is the process of combining data that has been extracted from multiple data sources into a consistent structure - usually to support analytics and reporting. Commonly, data from operational systems is extracted, transformed, and loaded into analytical stores such as a data lake or data warehouse.



## Common languages <a href="#common-languages" id="common-languages"></a>

Data Engineers must be proficient with a range of tools and scripting languages - in particular SQL and Python, and potentially others.

* **SQL** - One of the most common languages data engineers use is SQL, or Structured Query Language, which is a relatively easy language to learn. SQL uses queries that include SELECT, INSERT, UPDATE, and DELETE statements to directly work with the data stored in tables.
* **Python** - Python is one of the most popular and fastest growing programming languages in the world. It's used for all sorts of tasks, including web programming and data analysis. It has emerged as the language to learn for machine learning, and is increasing in popularity in data engineering with the use of notebooks.
* **Others** - Depending upon the needs of the organization and your individual skill set, you may also use other popular languages within or outside of notebooks including R, Java, Scala, .NET, and more. The use of notebooks is growing in popularity, and allows collaboration using different languages within the same notebook.



## Data engineering concepts

There are some core concepts with which data engineers should be familiar. These concepts underpin many of the workloads that data engineers must implement and support.

### Operational and analytical data <a href="#operational-and-analytical-data" id="operational-and-analytical-data"></a>

![Diagram representing operational and analytical data.](https://learn.microsoft.com/en-us/training/wwl-data-ai/introduction-to-data-engineering-azure/media/4-operational-analytical-data.png)

_**Operational**_** data** is usually transactional data that is generated and stored by applications, often in a relational or non-relational database.

_**Analytical**_** data** is data that has been optimized for analysis and reporting, often in a data warehouse.

### Streaming data <a href="#streaming-data" id="streaming-data"></a>

![Diagram representing streaming data.](https://learn.microsoft.com/en-us/training/wwl-data-ai/introduction-to-data-engineering-azure/media/4-stream-data.png)

Streaming data refers to perpetual sources of data that generate data values in real-time, often relating to specific events. Common sources of streaming data include internet-of-things (IoT) devices and social media feeds.

Data engineers often need to implement solutions that capture real-time stream of data and ingest them into analytical data systems, often combining the real-time data with other application data that is processed in batches.

### Data pipelines <a href="#data-pipelines" id="data-pipelines"></a>

![Diagram representing a data pipeline.](https://learn.microsoft.com/en-us/training/wwl-data-ai/introduction-to-data-engineering-azure/media/4-data-pipeline.png)

Data pipelines are used to orchestrate activities that transfer and transform data. Pipelines are the primary way in which data engineers implement repeatable extract, transform, and load (ETL) solutions that can be triggered based on a schedule or in response to events.

### Data lakes <a href="#data-lakes" id="data-lakes"></a>

![Diagram representing a data lake.](https://learn.microsoft.com/en-us/training/wwl-data-ai/introduction-to-data-engineering-azure/media/4-data-lake.png)

A data lake is a storage repository that holds large amounts of data in native, raw formats. Data lake stores are optimized for scaling to massive volumes (terabytes or petabytes) of data. The data typically comes from multiple heterogeneous sources, and may be structured, semi-structured, or unstructured.

The idea with a data lake is to store everything in its original, untransformed state. This approach differs from a traditional data warehouse, which transforms and processes the data at the time of ingestion.

### Data warehouses <a href="#data-warehouses" id="data-warehouses"></a>

![Diagram representing a data Warehouse.](https://learn.microsoft.com/en-us/training/wwl-data-ai/introduction-to-data-engineering-azure/media/4-data-warehouse.png)

A data warehouse is a centralized repository of integrated data from one or more disparate sources. Data warehouses store current and historical data in relational tables that are organized into a schema that optimizes performance for analytical queries.

Data engineers are responsible for designing and implementing relational data warehouses, and managing regular data loads into tables.

### Apache Spark <a href="#apache-spark" id="apache-spark"></a>

![Diagram representing an Apache Spark cluster.](https://learn.microsoft.com/en-us/training/wwl-data-ai/introduction-to-data-engineering-azure/media/4-apache-spark.png)

Apache Spark is a parallel processing framework that takes advantage of in-memory processing and a distributed file storage. It's a common open-source software (OSS) tool for big data scenarios.

Data engineers need to be proficient with Spark, using notebooks and other code artifacts to process data in a data lake and prepare it for modeling and analysis.

\
