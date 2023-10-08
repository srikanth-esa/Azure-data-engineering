# Data operations

As a data engineer some of the main tasks that you'll perform in Azure include _data integration_, _data transformation_, and _data consolidation_.

#### Data integration <a href="#data-integration" id="data-integration"></a>

![Diagram representing a data integration operation.](https://learn.microsoft.com/en-us/training/wwl-data-ai/introduction-to-data-engineering-azure/media/2-integration-data-operation.png)

Data Integration involves establishing links between operational and analytical services and data sources to enable secure, reliable access to data across multiple systems. For example, a business process might rely on data that is spread across multiple systems, and a data engineer is required to establish links so that the required data can be extracted from all of these systems.

#### Data transformation <a href="#data-transformation" id="data-transformation"></a>

![Diagram representing a data transformation operation.](https://learn.microsoft.com/en-us/training/wwl-data-ai/introduction-to-data-engineering-azure/media/2-transformation-data-operation.png)

Operational data usually needs to be _transformed_ into suitable structure and format for analysis, often as part of an _extract, transform, and load_ (ETL) process; though increasingly a variation in which you _extract, load, and transform_ (ELT) the data is used to quickly ingest the data into a data lake and then apply "big data" processing techniques to transform it. Regardless of the approach used, the data is prepared to support downstream analytical needs.

#### Data consolidation <a href="#data-consolidation" id="data-consolidation"></a>

![Diagram representing a data consolidation operation.](https://learn.microsoft.com/en-us/training/wwl-data-ai/introduction-to-data-engineering-azure/media/2-consolidation-data-operation.png)

Data consolidation is the process of combining data that has been extracted from multiple data sources into a consistent structure - usually to support analytics and reporting. Commonly, data from operational systems is extracted, transformed, and loaded into analytical stores such as a data lake or data warehouse.
