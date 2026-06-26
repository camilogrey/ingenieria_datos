# Actividades de Investigación: Microsoft Fabric

## Actividad 3.1 · Investigación sobre OneLake en Microsoft Fabric

### ¿Es un data lake? ¿Qué features añade OneLake versus un Data Lake tradicional?

**Definición clara:**  
Sí, es un data lake, pero con una diferencia clave: **es lógico y único para toda la empresa**. Mientras un Data Lake tradicional es un "almacén de archivos suelto", OneLake funciona como "el OneDrive de tus datos", donde todo está conectado y ordenado sin necesidad de mover archivos entre equipos.

---

### Features adicionales que marcan la diferencia:

1. **Unificación automática:**  
   Aparece solo con contratar Fabric. Olvídate de crear cuentas de almacenamiento para cada proyecto; aquí todo vive en un mismo sitio.

2. **Accesos directos (Shortcuts):**  
   Es como un "acceso directo" de Windows, pero para la nube. Puedes ver y consultar datos que están en Amazon, Google o Azure **sin tener que copiarlos**. Ahorras espacio y dinero en transferencias.

3. **Formato abierto (Delta Parquet):**  
   Guarda los datos en un formato estándar. Esto significa que aunque uses diferentes herramientas (Spark, SQL, Python), todas leerán el mismo archivo sin problemas de compatibilidad.

4. **Gobernanza centralizada:**  
   La seguridad (quién puede ver qué) se aplica una sola vez para todo, evitando que cada equipo configure sus propias reglas.

---

### ¿Está basado en ADLS Gen2 o no tienen nada que ver?

**Relación directa:**  
Sí, OneLake está construido **sobre** la tecnología de Azure Data Lake (ADLS Gen2). Es como si ADLS Gen2 fuera el motor (el chasis del coche) y OneLake fuera el coche completo con dirección asistida y aire acondicionado (la experiencia de usuario).

**Compatibilidad:**  
Cualquier programa que funcione con ADLS Gen2 funciona con OneLake sin cambios.

---

### Similitudes y diferencias:

| **Similitudes** | **Diferencias (La clave)** |
|----------------|---------------------------|
| Ambos guardan archivos en carpetas y soportan grandes volúmenes de datos (Petabytes). | **ADLS Gen2** es un "lote de tierra" donde tú tienes que construir la carretera, poner la valla y la puerta (configurar redes, seguridad y redundancia manualmente). |
| | **OneLake** es un "edificio de oficinas inteligente" donde todo viene ya construido, iluminado y con seguridad incluida (SaaS). Tú solo te preocupas de tus datos, no de mantener el edificio. |

---

## Actividad 3.2 – Equivalente de ADF en Fabric

### Define y explica qué es Data Factory en Fabric:

**Definición:**  
Es la nueva herramienta para mover y transformar datos. Unifica lo mejor de dos mundos: la potencia de orquestación de Azure Data Factory (para programar tareas pesadas) y la facilidad visual de Power Query (para que los analistas manipulen datos sin saber programar).

---

### ¿Es lo mismo que ADF?

**Salvedad importante:**  
No, no es exactamente lo mismo. **ADF es un servicio independiente** que hay que configurar y pagar por separado.  
Data Factory en Fabric es una evolución nativa de la nube (SaaS), donde no pagas por máquinas, sino por la capacidad total de procesamiento que contrates para toda la plataforma.

---

### Similitudes, diferencias y conclusiones:

| **Similitudes** | **Diferencias (Lo que cambia)** |
|----------------|--------------------------------|
| En ambos arrastras y sueltas componentes para crear flujos de trabajo y los programas con horarios (triggers). | **Dataflows Gen2:** En Fabric, los analistas pueden transformar datos con clics (sin código) y guardarlos directamente en el Data Lake. En ADF clásico esto era más complejo. |
| | **Menos gestión:** En ADF tenías que instalar "máquinas virtuales" (Integration Runtime) para conectar con redes privadas. En Fabric, la conexión se simplifica muchísimo (usando gateways estándar). |
| | **Modelo de pago:** ADF cobra por cada vez que algo se mueve. Fabric cobra una tarifa plana mensual por la potencia contratada, lo que facilita la previsión de gastos. |

**Conclusión final:**  
Data Factory en Fabric **democratiza la ingeniería de datos**. Ya no es solo para programadores expertos; los analistas de negocio también pueden crear flujos de datos complejos de forma visual, reduciendo la dependencia del departamento de TI.

---

### ¿Podría desde Fabric conectarme a datos en Azure/AWS/GCP? ¿De qué formas y cuál sería la utilidad?

**Sí, absolutamente.** Hay dos formas principales:

1. **Accesos directos (Shortcuts):**  
   Ideal para cuando no quieres duplicar la información. Creas un enlace a los datos que están en AWS S3 o Google Cloud y trabajas con ellos **como si estuvieran en Microsoft**. Útil para no pagar costes de almacenamiento doble.

2. **Pipelines y Dataflows:**  
   Ideal para cuando necesitas **extraer** datos de bases de datos (como AWS Redshift o Google BigQuery), transformarlos y **cargarlos** en Fabric.

**Utilidad estratégica:**  
Permite tener una **estrategia Multi-cloud real**. Tu empresa puede tener datos repartidos en varias nubes, pero tus analistas trabajan desde un solo sitio (Fabric) sin importar dónde estén los datos, ahorrando tiempo y dinero en transferencias de red.

### Actividad 3.3 · Servicios equivalentes en AWS, GCP y Microsoft Fabric

#### Tabla Comparativa de Servicios

| Categoría | Azure | AWS | GCP | Microsoft Fabric |
|:---|:---|:---|:---|:---|
| **Base de Datos SQL** | Azure SQL Database | Amazon RDS | Cloud SQL | SQL Database / Warehouse |
| **Integración de Datos (ETL/ELT)** | Azure Data Factory (ADF) | AWS Glue / Step Functions | Cloud Data Fusion / Cloud Composer | Data Factory (Pipelines + Dataflows Gen2) |
| **Data Lake (Almacenamiento)** | Azure Data Lake Storage Gen2 | Amazon S3 | Google Cloud Storage (GCS) | OneLake |
| **Business Intelligence (BI)** | Power BI | Amazon QuickSight | Looker Studio / Looker | Power BI (integrado nativamente) |

> **Nota sobre OneLake:** OneLake no es un servicio independiente, sino que está construido sobre ADLS Gen2. Actúa como una capa de abstracción que unifica el almacenamiento en todo Fabric, similar a la experiencia de "OneDrive" para datos empresariales.

---

#### Resumen de Servicios

##### Amazon Web Services (AWS)
- **Amazon RDS:** Servicio administrado de bases de datos relacionales con soporte para MySQL, PostgreSQL, SQL Server, entre otros. Automatiza parches, backups y escalado.
- **AWS Glue:** Servicio serverless de ETL que descubre, cataloga y transforma datos, ideal para preparar información para analítica o machine learning.
- **AWS Step Functions:** Orquestador de flujos de trabajo que coordina múltiples servicios AWS en secuencias lógicas (similar a los pipelines de ADF).
- **Amazon S3:** Almacenamiento de objetos escalable y duradero, base de los data lakes en AWS.

##### Google Cloud Platform (GCP)
- **Cloud SQL:** Base de datos relacional gestionada para MySQL, PostgreSQL y SQL Server, con alta disponibilidad y réplicas de lectura.
- **Cloud Data Fusion:** Servicio visual y low-code para construir pipelines ETL/ELT, ideal para usuarios con menos experiencia en programación.
- **Cloud Composer:** Servicio de orquestación basado en Apache Airflow, para programar y monitorizar flujos de trabajo complejos.
- **Google Cloud Storage (GCS):** Almacenamiento de objetos unificado y geo-redundante, diseñado para data lakes a gran escala.

##### Microsoft Fabric
- **SQL Database/Warehouse:** Capacidades de bases de datos relacionales y almacenes de datos dentro del ecosistema Fabric, con experiencia unificada.
- **Data Factory:** Suite de integración que combina pipelines tradicionales (herencia de ADF) con Dataflows Gen2 (herencia de Power Query) para ETL/ELT visual y código.
- **OneLake:** Data lake único, lógico y gobernado para toda la organización, construido sobre ADLS Gen2 y accesible desde cualquier motor de Fabric (Spark, SQL, etc.).
- **Power BI:** Herramienta de visualización y análisis integrada nativamente en Fabric, permitiendo que los datos residan y se exploren en un mismo entorno.

---

#### Conclusión Estratégica

Cada proveedor ofrece un stack completo de datos, pero **Fabric destaca por su integración nativa**:

- **Frente a AWS:** AWS es más modular y requiere que el cliente ensamble los servicios (S3 + Glue + QuickSight + RDS). Fabric ofrece una experiencia empaquetada y unificada.
- **Frente a GCP:** GCP también ofrece servicios integrados, pero Fabric apuesta por la **simplicidad SaaS** y la **unificación del almacenamiento** (OneLake), reduciendo la gestión de cuentas separadas.

La elección depende de la estrategia cloud de cada organización: **AWS/GCP** son ideales para equipos que buscan flexibilidad y control total; **Fabric** es mejor para quienes priorizan la productividad, la gobernanza centralizada y la reducción de costes operativos.
