
# Certificación DP-600: Ingeniería de Datos de Gran Escala

Este repositorio contiene los apuntes consolidados y sintetizados sobre almacenamiento analítico, procesamiento en tiempo real y visualización empresarial utilizando herramientas líderes de la industria.

---

## 1. Almacenamiento Analítico: Arquitecturas y Plataformas

Las soluciones de análisis de datos a escala empresarial se fundamentan en estructurar los datos según la naturaleza de la carga de trabajo y el nivel de flexibilidad requerido.

### Comparativa de Conceptos de Almacenamiento

![h](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20175340.png)

| Concepto | Características Clave | Casos de Uso Ideales |
| :--- | :--- | :--- |
| **Almacenes de Datos <br>(Data Warehouses)** | • Bases de datos relacionales optimizadas para analítica.<br>• Esquemas estructurados (Estrella / Copo de Nieve).<br>• Tablas de hechos centrales y dimensiones descriptivas. | Datos transaccionales estructurados consultados mediante lenguaje SQL tradicional. |
| **Lagos de Datos <br>(Data Lakes)** | • Repositorios de archivos sobre sistemas distribuidos de alto rendimiento.<br>• Enfoque de "esquema en lectura" (*schema-on-read*). | Almacenamiento flexible de datos estructurados, semiestructurados y no estructurados sin restricciones al escribir. |
| **Enfoques Híbridos <br>(Data Lakehouses)** | • Almacenan archivos crudos en un lago pero los exponen como tablas mediante SQL.<br>• Habilitados por **Delta Lake** (soporta transacciones ACID y control de versiones). | Entornos que necesitan la escala económica de un lago combinada con el gobierno y rendimiento de un Warehouse. |

1. **Almacenes de Datos (Data Warehouses)** 

![Data warehouse](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20180325.png)

2. **Lagos de Datos (Data Lakes)**

![Data Lake](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20180351.png)

3. **Enfoques Híbridos (Data Lakehouses)**

![Data Lake house](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20183342.png)

![](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20191447.png)

**En reumen**

![](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20180419.png)

---
### Ecosistemas Analíticos en Microsoft Azure
![](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20173734.png)

![](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20173401.png)

#### A. Microsoft Fabric (Plataforma SaaS unificada sobre OneLake)
* **OneLake:** Capa única de almacenamiento compartido para toda la organización.
* **Fabric Lakehouse:** Almacena en formato Delta Lake, soporta Spark/Notebooks para ciencia de datos y expone un punto de conexión (*endpoint*) analítico de SQL. Ideal para datos mixtos.
* **Fabric Warehouse:** Almacén relacional totalmente administrado y compatible con SQL Server. Ofrece un control rígido de esquemas y alta concurrencia.
* **Estrategias de Ingesta:**
    * **Pipelines y Dataflows Gen2 (Data Factory):** Orquestación multisectorial (bajo código y código avanzado).
    * **OneLake Shortcuts:** Enlaces en vivo a nubes externas (ADLS Gen2, AWS S3, GCS) sin duplicación de archivos.
    * **Mirroring:** Replicación automatizada en tiempo casi real desde bases de datos operacionales (Azure SQL, Snowflake) hacia Delta Lake.

![](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20173856.png)

#### B. Azure Databricks (Plataforma PaaS basada en Apache Spark)
* Optimizado para ingeniería de datos a gran escala y cargas de trabajo complejas de machine learning.
* Usa **Delta Lake** de forma nativa para control de esquemas y consistencia transaccional.
* **Databricks SQL Warehouse:** Puntos de conexión dedicados y optimizados para herramientas de Business Intelligence (BI).
  
![](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20174211.png)

---

## 2. Ingesta y Procesamiento de Datos: Batch vs. Streaming

### Diferencias Clave

| Atributo | Procesamiento por Lotes (Batch) | Procesamiento en Tiempo Real (Streaming) |
| :--- | :--- | :--- |
| **Ámbito de Datos** | Conjunto completo de datos históricos (*Whole dataset*). | Ventanas de tiempo sumamente recientes (*Recent time window*). |
| **Granularidad** | Grandes volúmenes acumulados. | Eventos individuales procesados instantáneamente. |
| **Latencia** | Minutos u horas. | Segundos o milisegundos. |
| **Complejidad** | Consultas complejas y agregaciones pesadas. | Agregaciones simples y transformaciones rápidas. |

![](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20184234.png)


### Arquitectura General de Streaming

1.  **Evento:** Origen digital que genera datos continuamente (métrica de sensores, registros de logs).
2.  **Origen (Source):** Cola de mensajería encargada de capturar los eventos garantizando el procesamiento en orden único.
3.  **Procesamiento:** Consultas perpetuas operadas sobre ventanas de tiempo deslizantes.
4.  **Destino (Sink):** Capa final de persistencia de resultados procesados (tablas, archivos o cuadros de mando).

![](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20185724.png)

* **Tecnologías de Ingesta (Sources):** Azure Event Hubs (Cola de eventos que asegura el procesamiento ordenado y único), Azure IoT Hub, Azure Data Lake Store Gen 2 (Almacenamiento escalable usado como origen de archivos de streaming) y Apache Kafka (Solución de código abierto complementaria a Apache Spark).
  
![](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20185901.png)

* **Motores de Procesamiento:** Spark Structured Streaming (que mapea flujos vivos en Dataframes crecientes) y Azure Stream Analytics (PaaS independiente).

![](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20185839.png)

* **Destinos Analíticos (Sinks):** •	Azure Event Hubs: Para encadenar datos procesados hacia otros flujos descendientes.
•	Almacenamiento en archivos: Azure Data Lake Gen 2, Microsoft OneLake o Azure Blob Storage.
•	Almacenamiento en tablas: Azure SQL Database, Azure Databricks o Microsoft Fabric para consultas analíticas

![](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20185920.png)

* **Servicios de Análitica en tiempo real:**
•	Microsoft Fabric Real-Time Intelligence: Herramienta integrada en Fabric. Incluye Eventstreams ingesta y ruta, Eventhouse (base de datos optimizada para series temporales mediante consultas KQL), Real-Time Dashboards (visualización) y Activator (acciones automatizadas).
•	Spark Structured Streaming: Biblioteca de código abierto para soluciones complejas en Apache Spark (compatible con Fabric y Azure Databricks).
•	Azure Stream Analytics: Solución PaaS para definir trabajos analíticos con consultas perpetuas fuera del ecosistema de Fabric.

![](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20190845.png)

* **Procesamiento Masivo**
Apache Spark: Motor de procesamiento masivo diseñado para manejar grandes volúmenes de datos rápidamente, dividiendo el trabajo en paralelo a través de un clúster de máquinas. Está disponible en Azure mediante Microsoft Fabric y Azure Databricks, soportando Python, Scala, Java y SQL tanto para procesamiento por lotes (batch) como en tiempo real (streaming).

![](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20191230.png)

---

## 3. Visualización y Modelado Semántico Empresarial (Power BI)

Para habilitar la toma de decisiones empresariales de forma segura, Power BI encapsula flujos avanzados de modelado lógico y diseño de informes.

### Flujo de Trabajo Típico de Inteligencia de Negocio

![](/imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20192126.png)

![](/imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20193058.png)

### Modelado de Datos: Diseño de Esquemas Analíticos

Los datos crudos de las tablas de hechos (eventos numéricos como ventas) se organizan mapeando relaciones con tablas de dimensiones (entidades de negocio para filtrar, como Clientes o Tiempo).

![](/imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20193328.png)

* **Esquema de Estrella (*Star Schema*):** Modelo recomendado donde cada dimensión se vincula directamente a la tabla de hechos.

![](/imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20193458.png)

* **Esquema de Copo de Nieve (*Snowflake Schema*):** Extensión donde las dimensiones se normalizan y conectan a sub-tablas de detalle (ej. Producto ➔ Categoría).

![](/imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20193520.png)]


* **Jerarquías de Atributos:** Estructuras lógicas que configuran caminos de exploración analítica profunda (ej. Año ➔ Mes ➔ Día). El motor **VertiPaq** calcula en memoria estas agregaciones bajo demanda con un rendimiento ultra veloz.

![](/imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20193635.png)

* **Modo Direct Lake:** Conexión exclusiva dentro de Microsoft Fabric que lee directamente archivos Parquet de OneLake, evitando ciclos tradicionales de importación o duplicación de datos.

### Herramientas Visuales e Inteligencia Artificial en Informes

Además de los gráficos tradicionales (líneas, columnas, mapas), Power BI integra componentes nativos potenciados por Machine Learning para descubrir patrones ocultos de forma automatizada:

![](/imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20193705.png)

* **Narrativas Inteligentes (*Smart Narratives*):** Genera explicaciones textuales ejecutivas de forma dinámica según el estado de los filtros aplicados.
* **Esquema de Descomposición (*Decomposition Tree*):** Permite desglosar y desarmar visualmente una métrica a través de múltiples dimensiones consecutivas.
* **Elementos Influyentes Clave (*Key Influencers*):** Evalúa numéricamente qué variables contextuales impulsan un indicador de negocio hacia arriba o hacia abajo.
* **Visual de Preguntas y Respuestas (Q&A):** Responde preguntas de negocio con gráficos construidos al vuelo a partir de lenguaje natural.

![](/imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20194015.png)

<div align="center">
  <a href="Lab4_completo.md">⏪ Atrás (Menú)</a> | 
  <a href="Lab4_completo.md">🏠 Menú Principal</a> | 
  <a href="lab_fabric_4.1_lakehouse.md">Adelante ⏩</a>
</div>