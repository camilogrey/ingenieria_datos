# Mapa Tecnológico de Arquitectura de Datos

## 1. Capa de Origen (Source Layer)
**Estado del dato:** TRANSACCIONAL (OLTP)

### Open Source
- PostgreSQL
- MySQL
- MongoDB

### De Pago (Comercial)
- Oracle Database
- SAP ERP / HANA
- Salesforce CRM

### Microsoft / Azure
- Azure SQL Database
- Azure Cosmos DB
- Microsoft Dataverse

---

## 2. Capa de Ingesta (Ingestion Layer)
**Estado del dato:** EN TRÁNSITO

### Open Source
- Apache Kafka
- Apache Nifi
- Airbyte Open Source

### De Pago (Comercial)
- Fivetran
- Confluent Cloud
- Informatica PC

### Microsoft / Azure
- Azure Data Factory
- Azure Event Hubs
- Azure IoT Hub

---

## 3. Capa Raw / Landing (Storage Layer)
**Estado del dato:** INMUTABLE / FIEL AL ORIGEN

### Open Source
- MinIO (S3 compatible)
- Ceph Object Store
- Apache Hadoop HDFS

### De Pago (Comercial)
- Snowflake Storage
- Databricks Storage
- Pure Storage

### Microsoft / Azure
- Azure Data Lake Storage Gen2
- Azure Blob Storage
- Azure Files

---

## 4. Capa de Procesamiento (Processing Layer)
**Estado del dato:** LIMPIO / NORMALIZADO / ACID (SILVER)

### Open Source
- Apache Spark
- Apache Flink
- Trino / Presto

### De Pago (Comercial)
- Databricks Platform
- Snowflake Compute
- Cloudera Data Platform

### Microsoft / Azure
- Azure Synapse (Spark Pools)
- Azure Databricks
- Azure HDInsight

---

## 5. Capa de Modelado (Semantic Layer)
**Estado del dato:** DIMENSIONAL / GOLD

### Open Source
- dbt Core
- Cube.js
- Apache Hive Metastore

### De Pago (Comercial)
- dbt Cloud
- AtScale Semantic Layer
- Snowflake Data Warehouse

### Microsoft / Azure
- Azure Synapse (Dedicated Pools)
- Power BI Semantic Models
- Azure Analysis Services

---

## 6. Capa de Acceso / Consumo (Consumption Layer)
**Estado del dato:** LISTO PARA NEGOCIO / CIENCIA DE DATOS

### Open Source
- Apache Superset
- Metabase
- Grafana / Jupyter

### De Pago (Comercial)
- Tableau
- Qlik Sense
- Looker

### Microsoft / Azure
- Power BI Pro / Premium
- Azure Machine Learning
- Microsoft Excel (Power Pivot)

---

## 7. Capa de Gobernanza y Orquestación (Governance & Orchestration Layer)
**Estado del dato:** TRANSVERSAL / CONTROL Y CALIDAD

### Open Source
- Apache Airflow
- Prefect / Dagster
- Apache Atlas

### De Pago (Comercial)
- Collibra
- Alation
- Solidatus

### Microsoft / Azure
- Microsoft Purview
- Azure Data Factory (Pipelines)
- Azure Policy
