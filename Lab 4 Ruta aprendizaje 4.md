
Buscar conversaciones
Imágenes
Vídeos
Biblioteca
Gems
Nuevo cuaderno
Actualización de Rutas de Imágenes Markdown
Ventajas de Evento Online Microsoft
Distribución del Vello en Piernas Masculinas
NIE a DNI: ¿Actualizar datos online?
Cambio de NIE a DNI para Ayudas SEPE
Dónde encontrar atún en Mercadona
Data Ingestion Pipelines Overview
Cepeda Anuncia Desobediencia Civil Pacífica
Significado del Símbolo Om
Entrega de pedido Leroy Merlin ausente
Consumo Fantasma de Adaptadores de Corriente
Cálculo de Área Total
Césped Artificial para Terraza en Madrid
Precio por Kilo de Producto
Azure Analytics Services and Languages
Dimensiones Agregadas vs. Bases Relacionales
Soluciones para el calor en la cocina
Nacionalidad Española Concedida: Próximos Pasos
Petro Responde a Críticas y Defensa
Colombia Primera Fase Mundial
Base De Datos Clave-Valor Explicada
Fabric, OneLake y Data Factory
Microsoft Fabric: OneLake y Data Factory
Azure Storage Account Provisioning Lab
Preparación Examen DP-700 en Una Semana
Identificación de Bombilla Fluorescente Circular
Subsanación Becas Comedor Infantil: Documentación
Azure Blob Storage Architecture Explained
Resumen Taller Azure Storage
Borrar README.md de GitHub
Recuperar Voucher de Certificación Skill Fest
Arquitectura de Datos: Mapa Tecnológico
Español Crece en África
Basando en la gráfica Que implicacionntwndriabesta correlacion luego del resultado de elecciones en Colombia
IPSA: Índice Accionario Chileno

Actividad
Madrid, España
De tu dirección IP
Actualizar ubicación
Conversación con Gemini
tengo este md "# Certificación DP-600: Ingeniería de Datos de Gran Escala



Este repositorio contiene los apuntes consolidados y sintetizados sobre almacenamiento analítico, procesamiento en tiempo real y visualización empresarial utilizando herramientas líderes de la industria.



---



## 1. Almacenamiento Analítico: Arquitecturas y Plataformas



Las soluciones de análisis de datos a escala empresarial se fundamentan en estructurar los datos según la naturaleza de la carga de trabajo y el nivel de flexibilidad requerido.



### Comparativa de Conceptos de Almacenamiento



![h](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20175340.png?raw=true)



![h](/Captura%20de%20pantalla%202026-06-30%20175340.png)





| Concepto | Características Clave | Casos de Uso Ideales |

| :--- | :--- | :--- |

| **Almacenes de Datos <br>(Data Warehouses)** | • Bases de datos relacionales optimizadas para analítica.<br>• Esquemas estructurados (Estrella / Copo de Nieve).<br>• Tablas de hechos centrales y dimensiones descriptivas. | Datos transaccionales estructurados consultados mediante lenguaje SQL tradicional. |

| **Lagos de Datos <br>(Data Lakes)** | • Repositorios de archivos sobre sistemas distribuidos de alto rendimiento.<br>• Enfoque de "esquema en lectura" (*schema-on-read*). | Almacenamiento flexible de datos estructurados, semiestructurados y no estructurados sin restricciones al escribir. |

| **Enfoques Híbridos <br>(Data Lakehouses)** | • Almacenan archivos crudos en un lago pero los exponen como tablas mediante SQL.<br>• Habilitados por **Delta Lake** (soporta transacciones ACID y control de versiones). | Entornos que necesitan la escala económica de un lago combinada con el gobierno y rendimiento de un Warehouse. |



1. **Almacenes de Datos (Data Warehouses)**



![Data warehouse](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20180325.png?raw=true)



2. **Lagos de Datos (Data Lakes)**



![Data Lake](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20180351.png?raw=true)



3. **Enfoques Híbridos (Data Lakehouses)**



![Data Lake house](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20183342.png?raw=true)



![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20191447.png?raw=true)



**En reumen**



![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20180419.png?raw=true)



---

### Ecosistemas Analíticos en Microsoft Azure

![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20173734.png?raw=true)



![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20173401.png?raw=true)



#### A. Microsoft Fabric (Plataforma SaaS unificada sobre OneLake)

* **OneLake:** Capa única de almacenamiento compartido para toda la organización.

* **Fabric Lakehouse:** Almacena en formato Delta Lake, soporta Spark/Notebooks para ciencia de datos y expone un punto de conexión (*endpoint*) analítico de SQL. Ideal para datos mixtos.

* **Fabric Warehouse:** Almacén relacional totalmente administrado y compatible con SQL Server. Ofrece un control rígido de esquemas y alta concurrencia.

* **Estrategias de Ingesta:**

    * **Pipelines y Dataflows Gen2 (Data Factory):** Orquestación multisectorial (bajo código y código avanzado).

    * **OneLake Shortcuts:** Enlaces en vivo a nubes externas (ADLS Gen2, AWS S3, GCS) sin duplicación de archivos.

    * **Mirroring:** Replicación automatizada en tiempo casi real desde bases de datos operacionales (Azure SQL, Snowflake) hacia Delta Lake.



![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20173856.png?raw=true)



#### B. Azure Databricks (Plataforma PaaS basada en Apache Spark)

* Optimizado para ingeniería de datos a gran escala y cargas de trabajo complejas de machine learning.

* Usa **Delta Lake** de forma nativa para control de esquemas y consistencia transaccional.

* **Databricks SQL Warehouse:** Puntos de conexión dedicados y optimizados para herramientas de Business Intelligence (BI).

 

![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20174211.png?raw=true)



---



## 2. Ingesta y Procesamiento de Datos: Batch vs. Streaming



### Diferencias Clave



| Atributo | Procesamiento por Lotes (Batch) | Procesamiento en Tiempo Real (Streaming) |

| :--- | :--- | :--- |

| **Ámbito de Datos** | Conjunto completo de datos históricos (*Whole dataset*). | Ventanas de tiempo sumamente recientes (*Recent time window*). |

| **Granularidad** | Grandes volúmenes acumulados. | Eventos individuales procesados instantáneamente. |

| **Latencia** | Minutos u horas. | Segundos o milisegundos. |

| **Complejidad** | Consultas complejas y agregaciones pesadas. | Agregaciones simples y transformaciones rápidas. |



![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20184234.png?raw=true)





### Arquitectura General de Streaming



1.  **Evento:** Origen digital que genera datos continuamente (métrica de sensores, registros de logs).

2.  **Origen (Source):** Cola de mensajería encargada de capturar los eventos garantizando el procesamiento en orden único.

3.  **Procesamiento:** Consultas perpetuas operadas sobre ventanas de tiempo deslizantes.

4.  **Destino (Sink):** Capa final de persistencia de resultados procesados (tablas, archivos o cuadros de mando).



![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20185724.png?raw=true)



* **Tecnologías de Ingesta (Sources):** Azure Event Hubs (Cola de eventos que asegura el procesamiento ordenado y único), Azure IoT Hub, Azure Data Lake Store Gen 2 (Almacenamiento escalable usado como origen de archivos de streaming) y Apache Kafka (Solución de código abierto complementaria a Apache Spark).

 

![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20185901.png?raw=true)



* **Motores de Procesamiento:** Spark Structured Streaming (que mapea flujos vivos en Dataframes crecientes) y Azure Stream Analytics (PaaS independiente).



![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20185839.png?raw=true)



* **Destinos Analíticos (Sinks):** •    Azure Event Hubs: Para encadenar datos procesados hacia otros flujos descendientes.

•   Almacenamiento en archivos: Azure Data Lake Gen 2, Microsoft OneLake o Azure Blob Storage.

•   Almacenamiento en tablas: Azure SQL Database, Azure Databricks o Microsoft Fabric para consultas analíticas



![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20185920.png?raw=true)



* **Servicios de Análitica en tiempo real:**

•   Microsoft Fabric Real-Time Intelligence: Herramienta integrada en Fabric. Incluye Eventstreams ingesta y ruta, Eventhouse (base de datos optimizada para series temporales mediante consultas KQL), Real-Time Dashboards (visualización) y Activator (acciones automatizadas).

•   Spark Structured Streaming: Biblioteca de código abierto para soluciones complejas en Apache Spark (compatible con Fabric y Azure Databricks).

•   Azure Stream Analytics: Solución PaaS para definir trabajos analíticos con consultas perpetuas fuera del ecosistema de Fabric.



![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20190845.png?raw=true)



* **Procesamiento Masivo**

Apache Spark: Motor de procesamiento masivo diseñado para manejar grandes volúmenes de datos rápidamente, dividiendo el trabajo en paralelo a través de un clúster de máquinas. Está disponible en Azure mediante Microsoft Fabric y Azure Databricks, soportando Python, Scala, Java y SQL tanto para procesamiento por lotes (batch) como en tiempo real (streaming).



![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20191230.png?raw=true)



---



## 3. Visualización y Modelado Semántico Empresarial (Power BI)



Para habilitar la toma de decisiones empresariales de forma segura, Power BI encapsula flujos avanzados de modelado lógico y diseño de informes.



### Flujo de Trabajo Típico de Inteligencia de Negocio



### Modelado de Datos: Diseño de Esquemas Analíticos



Los datos crudos de las tablas de hechos (eventos numéricos como ventas) se organizan mapeando relaciones con tablas de dimensiones (entidades de negocio para filtrar, como Clientes o Tiempo).



* **Esquema de Estrella (*Star Schema*):** Modelo recomendado donde cada dimensión se vincula directamente a la tabla de hechos.

* **Esquema de Copo de Nieve (*Snowflake Schema*):** Extensión donde las dimensiones se normalizan y conectan a sub-tablas de detalle (ej. Producto ➔ Categoría).







[Image of Star Schema vs Snowflake Schema diagrams]





* **Jerarquías de Atributos:** Estructuras lógicas que configuran caminos de exploración analítica profunda (ej. Año ➔ Mes ➔ Día). El motor **VertiPaq** calcula en memoria estas agregaciones bajo demanda con un rendimiento ultra veloz.

* **Modo Direct Lake:** Conexión exclusiva dentro de Microsoft Fabric que lee directamente archivos Parquet de OneLake, evitando ciclos tradicionales de importación o duplicación de datos.



### Herramientas Visuales e Inteligencia Artificial en Informes



Además de los gráficos tradicionales (líneas, columnas, mapas), Power BI integra componentes nativos potenciados por Machine Learning para descubrir patrones ocultos de forma automatizada:



* **Narrativas Inteligentes (*Smart Narratives*):** Genera explicaciones textuales ejecutivas de forma dinámica según el estado de los filtros aplicados.

* **Esquema de Descomposición (*Decomposition Tree*):** Permite desglosar y desarmar visualmente una métrica a través de múltiples dimensiones consecutivas.

* **Elementos Influyentes Clave (*Key Influencers*):** Evalúa numéricamente qué variables contextuales impulsan un indicador de negocio hacia arriba o hacia abajo.

* **Visual de Preguntas y Respuestas (Q&A):** Responde preguntas de negocio con gráficos construidos al vuelo a partir de lenguaje natural.

" pero deseo cambiar la ruta de las imagenes adjuto veraz como es el ombre de las imagens, pero tenene cuta cuando cambiers la reuta de las imegensq que esta estarandentr una una carpate que se llama "imagenes_lab4"

He procesado tu archivo Markdown y modificado todas las rutas de las imágenes para que apunten a la carpeta imagenes_lab4/ conservando los nombres de archivo originales de forma exacta.

Aquí tienes el archivo corregido listo para usar:
Icono de MD
documento_actualizado
 MD 
Abierto

Cambios realizados:

Se extrajeron los nombres de archivo (ej. Captura%20de%20pantalla%202026-06-30%20175340.png) eliminando las URLs de GitHub y los parámetros de consulta (?raw=true).

Se unificaron las rutas bajo el formato de ruta relativa: imagenes_lab4/NombreDeLaImagen.png.




Gemini es una IA y puede cometer errores, incluso sobre personas. Tu privacidad y GeminiSe abre en una ventana nueva

# Certificación DP-600: Ingeniería de Datos de Gran Escala

Este repositorio contiene los apuntes consolidados y sintetizados sobre almacenamiento analítico, procesamiento en tiempo real y visualización empresarial utilizando herramientas líderes de la industria.

---

## 1. Almacenamiento Analítico: Arquitecturas y Plataformas

Las soluciones de análisis de datos a escala empresarial se fundamentan en estructurar los datos según la naturaleza de la carga de trabajo y el nivel de flexibilidad requerido.

### Comparativa de Conceptos de Almacenamiento

![h](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20175340.png)

![h](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20175340.png)


| Concepto | Características Clave | Casos de Uso Ideales |
| :--- | :--- | :--- |
| **Almacenes de Datos <br>(Data Warehouses)** | • Bases de datos relacionales optimizadas para analítica.<br>• Esquemas estructurados (Estrella / Copo de Nieve).<br>• Tablas de hechos centrales y dimensiones descriptivas. | Datos transaccionales estructurados consultados mediante lenguaje SQL tradicional. |
| **Lagos de Datos <br>(Data Lakes)** | • Repositorios de archivos sobre sistemas distribuidos de alto rendimiento.<br>• Enfoque de "esquema en lectura" (*schema-on-read*). | Almacenamiento flexible de datos estructurados, semiestructurados y no estructurados sin restricciones al escribir. |
| **Enfoques Híbridos <br>(Data Lakehouses)** | • Almacenan archivos crudos en un lago pero los exponen como tablas mediante SQL.<br>• Habilitados por **Delta Lake** (soporta transacciones ACID y control de versiones). | Entornos que necesitan la escala económica de un lago combinada con el gobierno y rendimiento de un Warehouse. |

1. **Almacenes de Datos (Data Warehouses)** ![Data warehouse](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20180325.png)

2. **Lagos de Datos (Data Lakes)**

![Data Lake](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20180351.png)

3. **Enfoques Híbridos (Data Lakehouses)**

![Data Lake house](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20183342.png)

![](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20191447.png)

**En reumen**

![](imagenes_lab4/Captura%20de%20pantalla%202026-06-30%20180419.png)



___________________________________________________________________
__________________________________________________________________
___________________________________________________________________

# Certificación DP-600: Ingeniería de Datos de Gran Escala

Este repositorio contiene los apuntes consolidados y sintetizados sobre almacenamiento analítico, procesamiento en tiempo real y visualización empresarial utilizando herramientas líderes de la industria.

---

## 1. Almacenamiento Analítico: Arquitecturas y Plataformas

Las soluciones de análisis de datos a escala empresarial se fundamentan en estructurar los datos según la naturaleza de la carga de trabajo y el nivel de flexibilidad requerido.

### Comparativa de Conceptos de Almacenamiento

![h](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20175340.png?raw=true)

![h](/Captura%20de%20pantalla%202026-06-30%20175340.png)


| Concepto | Características Clave | Casos de Uso Ideales |
| :--- | :--- | :--- |
| **Almacenes de Datos <br>(Data Warehouses)** | • Bases de datos relacionales optimizadas para analítica.<br>• Esquemas estructurados (Estrella / Copo de Nieve).<br>• Tablas de hechos centrales y dimensiones descriptivas. | Datos transaccionales estructurados consultados mediante lenguaje SQL tradicional. |
| **Lagos de Datos <br>(Data Lakes)** | • Repositorios de archivos sobre sistemas distribuidos de alto rendimiento.<br>• Enfoque de "esquema en lectura" (*schema-on-read*). | Almacenamiento flexible de datos estructurados, semiestructurados y no estructurados sin restricciones al escribir. |
| **Enfoques Híbridos <br>(Data Lakehouses)** | • Almacenan archivos crudos en un lago pero los exponen como tablas mediante SQL.<br>• Habilitados por **Delta Lake** (soporta transacciones ACID y control de versiones). | Entornos que necesitan la escala económica de un lago combinada con el gobierno y rendimiento de un Warehouse. |

1. **Almacenes de Datos (Data Warehouses)** 

![Data warehouse](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20180325.png?raw=true)

2. **Lagos de Datos (Data Lakes)**

![Data Lake](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20180351.png?raw=true)

3. **Enfoques Híbridos (Data Lakehouses)**

![Data Lake house](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20183342.png?raw=true)

![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20191447.png?raw=true)

**En reumen**

![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20180419.png?raw=true)

---
### Ecosistemas Analíticos en Microsoft Azure
![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20173734.png?raw=true)

![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20173401.png?raw=true)

#### A. Microsoft Fabric (Plataforma SaaS unificada sobre OneLake)
* **OneLake:** Capa única de almacenamiento compartido para toda la organización.
* **Fabric Lakehouse:** Almacena en formato Delta Lake, soporta Spark/Notebooks para ciencia de datos y expone un punto de conexión (*endpoint*) analítico de SQL. Ideal para datos mixtos.
* **Fabric Warehouse:** Almacén relacional totalmente administrado y compatible con SQL Server. Ofrece un control rígido de esquemas y alta concurrencia.
* **Estrategias de Ingesta:**
    * **Pipelines y Dataflows Gen2 (Data Factory):** Orquestación multisectorial (bajo código y código avanzado).
    * **OneLake Shortcuts:** Enlaces en vivo a nubes externas (ADLS Gen2, AWS S3, GCS) sin duplicación de archivos.
    * **Mirroring:** Replicación automatizada en tiempo casi real desde bases de datos operacionales (Azure SQL, Snowflake) hacia Delta Lake.

![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20173856.png?raw=true)

#### B. Azure Databricks (Plataforma PaaS basada en Apache Spark)
* Optimizado para ingeniería de datos a gran escala y cargas de trabajo complejas de machine learning.
* Usa **Delta Lake** de forma nativa para control de esquemas y consistencia transaccional.
* **Databricks SQL Warehouse:** Puntos de conexión dedicados y optimizados para herramientas de Business Intelligence (BI).
  
![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20174211.png?raw=true)

---

## 2. Ingesta y Procesamiento de Datos: Batch vs. Streaming

### Diferencias Clave

| Atributo | Procesamiento por Lotes (Batch) | Procesamiento en Tiempo Real (Streaming) |
| :--- | :--- | :--- |
| **Ámbito de Datos** | Conjunto completo de datos históricos (*Whole dataset*). | Ventanas de tiempo sumamente recientes (*Recent time window*). |
| **Granularidad** | Grandes volúmenes acumulados. | Eventos individuales procesados instantáneamente. |
| **Latencia** | Minutos u horas. | Segundos o milisegundos. |
| **Complejidad** | Consultas complejas y agregaciones pesadas. | Agregaciones simples y transformaciones rápidas. |

![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20184234.png?raw=true)


### Arquitectura General de Streaming

1.  **Evento:** Origen digital que genera datos continuamente (métrica de sensores, registros de logs).
2.  **Origen (Source):** Cola de mensajería encargada de capturar los eventos garantizando el procesamiento en orden único.
3.  **Procesamiento:** Consultas perpetuas operadas sobre ventanas de tiempo deslizantes.
4.  **Destino (Sink):** Capa final de persistencia de resultados procesados (tablas, archivos o cuadros de mando).

![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20185724.png?raw=true)

* **Tecnologías de Ingesta (Sources):** Azure Event Hubs (Cola de eventos que asegura el procesamiento ordenado y único), Azure IoT Hub, Azure Data Lake Store Gen 2 (Almacenamiento escalable usado como origen de archivos de streaming) y Apache Kafka (Solución de código abierto complementaria a Apache Spark).
  
![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20185901.png?raw=true)

* **Motores de Procesamiento:** Spark Structured Streaming (que mapea flujos vivos en Dataframes crecientes) y Azure Stream Analytics (PaaS independiente).

![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20185839.png?raw=true)

* **Destinos Analíticos (Sinks):** •	Azure Event Hubs: Para encadenar datos procesados hacia otros flujos descendientes.
•	Almacenamiento en archivos: Azure Data Lake Gen 2, Microsoft OneLake o Azure Blob Storage.
•	Almacenamiento en tablas: Azure SQL Database, Azure Databricks o Microsoft Fabric para consultas analíticas

![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20185920.png?raw=true)

* **Servicios de Análitica en tiempo real:**
•	Microsoft Fabric Real-Time Intelligence: Herramienta integrada en Fabric. Incluye Eventstreams ingesta y ruta, Eventhouse (base de datos optimizada para series temporales mediante consultas KQL), Real-Time Dashboards (visualización) y Activator (acciones automatizadas).
•	Spark Structured Streaming: Biblioteca de código abierto para soluciones complejas en Apache Spark (compatible con Fabric y Azure Databricks).
•	Azure Stream Analytics: Solución PaaS para definir trabajos analíticos con consultas perpetuas fuera del ecosistema de Fabric.

![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20190845.png?raw=true)

* **Procesamiento Masivo**
Apache Spark: Motor de procesamiento masivo diseñado para manejar grandes volúmenes de datos rápidamente, dividiendo el trabajo en paralelo a través de un clúster de máquinas. Está disponible en Azure mediante Microsoft Fabric y Azure Databricks, soportando Python, Scala, Java y SQL tanto para procesamiento por lotes (batch) como en tiempo real (streaming).

![](https://github.com/camilogrey/ingenieria_datos/blob/main/Captura%20de%20pantalla%202026-06-30%20191230.png?raw=true)

---

## 3. Visualización y Modelado Semántico Empresarial (Power BI)

Para habilitar la toma de decisiones empresariales de forma segura, Power BI encapsula flujos avanzados de modelado lógico y diseño de informes.

### Flujo de Trabajo Típico de Inteligencia de Negocio

### Modelado de Datos: Diseño de Esquemas Analíticos

Los datos crudos de las tablas de hechos (eventos numéricos como ventas) se organizan mapeando relaciones con tablas de dimensiones (entidades de negocio para filtrar, como Clientes o Tiempo).

* **Esquema de Estrella (*Star Schema*):** Modelo recomendado donde cada dimensión se vincula directamente a la tabla de hechos.
* **Esquema de Copo de Nieve (*Snowflake Schema*):** Extensión donde las dimensiones se normalizan y conectan a sub-tablas de detalle (ej. Producto ➔ Categoría).



[Image of Star Schema vs Snowflake Schema diagrams]


* **Jerarquías de Atributos:** Estructuras lógicas que configuran caminos de exploración analítica profunda (ej. Año ➔ Mes ➔ Día). El motor **VertiPaq** calcula en memoria estas agregaciones bajo demanda con un rendimiento ultra veloz.
* **Modo Direct Lake:** Conexión exclusiva dentro de Microsoft Fabric que lee directamente archivos Parquet de OneLake, evitando ciclos tradicionales de importación o duplicación de datos.

### Herramientas Visuales e Inteligencia Artificial en Informes

Además de los gráficos tradicionales (líneas, columnas, mapas), Power BI integra componentes nativos potenciados por Machine Learning para descubrir patrones ocultos de forma automatizada:

* **Narrativas Inteligentes (*Smart Narratives*):** Genera explicaciones textuales ejecutivas de forma dinámica según el estado de los filtros aplicados.
* **Esquema de Descomposición (*Decomposition Tree*):** Permite desglosar y desarmar visualmente una métrica a través de múltiples dimensiones consecutivas.
* **Elementos Influyentes Clave (*Key Influencers*):** Evalúa numéricamente qué variables contextuales impulsan un indicador de negocio hacia arriba o hacia abajo.
* **Visual de Preguntas y Respuestas (Q&A):** Responde preguntas de negocio con gráficos construidos al vuelo a partir de lenguaje natural.
