#🇧🇷 Brazil Fuel Overview

Brazil is one of the world’s largest oil producers — yet it still depends on fuel imports.
This project builds an end-to-end data pipeline using public data from Brazil’s National Petroleum Agency (ANP), applying a Medallion Architecture to transform raw data into actionable insights.
The objective is to quantify and explain this gap: Why is Brazil not self-sufficient in fuels despite its strong oil production?


##📊 Project Overview

The project is organized in the following steps:
- 1️⃣ Extract public data from Brazil’s National Petroleum Agency (ANP) using Python and store the raw files in cloud storage (Volumes) using Spark.
- 2️⃣ Ingest and standardize raw data into the Bronze layer, preserving original structure and ensuring data traceability.
- 3️⃣ Clean, normalize the data in the Silver layer, applying data quality checks and business rules.
- 4️⃣ Model the data using a star schema, creating dimension and fact tables optimized for analytics.
- 5️⃣ Build curated fact tables and analytical views (Gold layer) for BI consumption.
- 6️⃣ Develop interactive dashboards in Tableau to analyze Brazil’s fuel dependency and refining capacity gap.

## 🏗️ Architecture

This project follows a Medallion Architecture implemented in Databricks.

![](/Workspace/Users/janaineberardi@gmail.com/ANP_FUEL_project/mermaid-diagram-5.png)



---


## 📂 Data Sources

- ANP – [Imports and Exports](https://www.gov.br/anp/pt-br/centrais-de-conteudo/dados-abertos/importacoes-e-exportacoes)
- ANP –  [Refinery Data ](https://www.gov.br/anp/pt-br/centrais-de-conteudo/dados-abertos/processamento-de-petroleo-e-producao-de-derivados$0)

All data is publicly available via ANP open data portal.

## 🧱 Data Model

The data is modeled using a star schema:

![](/Workspace/Users/janaineberardi@gmail.com/ANP_FUEL_project/mermaid-diagram.png)

## 📊 Key Metrics

- Import Dependency (%)
- Net Imports (m³)
- Refinery Equivalent (number of refineries required)

The refinery equivalent metric estimates the number of standard refineries (90k bpd capacity) required to eliminate fuel imports, adjusting for refinery yield factors and product-specific deficits.

## 📈 Dashboard

[View on Tableau](https://public.tableau.com/app/profile/janaine.xavier/viz/BrazilFuel/BrazilFuelOverview)

![Dashboard Preview](/Workspace/Users/janaineberardi@gmail.com/ANP_FUEL_project/Dashboard.png)

## 💡 Key Insights

- Brazil is a net oil exporter but depends heavily on diesel imports
- Refinery yield significantly increases required capacity
- Eliminating imports would require substantial refining expansion
- This analysis simplifies a complex system and does not account for all real-world factors that influence refining capacity and fuel dependency.

## 🧰 Tech Stack

| Layer            | Technology                     | Description |
|------------------|-------------------------------|------------|
| 🐍 Extraction     | Python                        | Data extraction from ANP public datasets |
| ⚡ Processing     | Apache Spark (Databricks)     | Distributed data processing and transformations |
| 🗄️ Storage        | Databricks Volumes            | Raw data storage (landing zone) |
| 🧱 Data Format    | Delta Lake                    | Storage format for Bronze, Silver, Gold layers |
| 🥉 Bronze Layer   | Spark + Delta                 | Raw data ingestion and standardization |
| 🥈 Silver Layer   | Spark + SQL                   | Data cleaning, normalization, and validation |
| 🥇 Gold Layer     | SQL (Databricks)               | Analytical modeling (fact and dimension tables) |
| 📊 Visualization  | Tableau                       | Dashboard development and data exploration |
| 🔧 Version Control| Git & GitHub                  | Code versioning and project management | 

## 🚀 Future Improvements

- Implement incremental data ingestion to automatically update datasets as new data becomes available  
- Improve data quality checks and validation in the Silver layer  
- Refine yield factors using product-specific and refinery-specific data  
- Incorporate additional datasets (e.g., refinery capacity, logistics)  
- Enhance the refinery equivalent metric with scenario analysis  
- Optimize storage and performance (partitioning, data types, query optimization)  
- Deploy the pipeline using automated workflows (Databricks Jobs / Workflows)  
- Expand dashboards with forecasting and simulation capabilities  



#👤 Author

Janaine Xavier

Petroleum Engineer exploring Data Engineering and Data Analytics.

Focus areas:

Energy data
Oil & gas analytics
Data pipelines
SQL & data warehousing


