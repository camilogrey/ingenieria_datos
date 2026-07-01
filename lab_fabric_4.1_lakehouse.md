# Reporte de Laboratorio: Creación de un Workspace en Microsoft Fabric

Este repositorio contiene las evidencias del laboratorio práctico: 
**"Crear un workspace, Crear un Lakehouse, Ingesta de datos & Consulta de datos en el Lakehouse "**. El objetivo de este ejercicio fue inicializar el entorno de trabajo dentro de la plataforma Microsoft Fabric, habilitando la capacidad de prueba (*Fabric Trial*) para disponer de la potencia de cómputo necesaria para tareas de ingeniería de datos.

---
# Creación de un Workspace

## 1. Acceso al Portal de Microsoft Fabric
* **Descripción:** Se ingresó al portal web oficial e inicio de sesión con las credenciales correspondientes. La interfaz inicial muestra el ecosistema de soluciones recomendadas e introducciones básicas.

![Inicio de sesión en el Portal de Fabric](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20180004.png)

---

## 2. Cambio de Experiencia (Experience Switcher)
* **Descripción:** Se interactuó con el selector de experiencias ubicado en la esquina inferior izquierda de la barra de menús. Se cambió el entorno de trabajo activo desde *Power BI* hacia la suite completa de *Fabric*, desbloqueando todas las herramientas de análisis de datos.

![Selector de Experiencia de Fabric Activo](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20180044.png)

---

## 3. Navegación al Panel de Workspaces
* **Descripción:** En la barra de navegación lateral izquierda, se seleccionó el icono de **Workspaces** (Áreas de trabajo). El menú desplegable lateral muestra las áreas existentes y expone el botón para la generación de nuevos entornos compartidos.

![Panel Lateral de Áreas de Trabajo](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20181004.png)

---

## 4. Configuración del Workspace y Asignación de Licencia (Fabric Trial)
* **Descripción:** Se inicializó el formulario de creación avanzada asignando el nombre técnico al proyecto (`dp900-fabric-lakehouse`).
* **Configuración clave:** En la sección avanzada de licenciamiento, se seleccionó explícitamente el modo **Fabric Trial** (Prueba gratuita de 60 días) para asociar el motor de procesamiento necesario y aislar los recursos del laboratorio.

![Configuración de Parámetros y Licencia del Workspace](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20181145.png)

---

## 5. Entorno de Trabajo Creado Exitosamente
* **Descripción:** El área de trabajo se desplegó correctamente en la plataforma. Al ser un entorno nuevo e independiente, se validó su estado inicial vacío (*There's nothing here yet*), quedando listo para la creación posterior de lakehouses o pipelines.

![Área de Trabajo Creada y Vacía](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20181320.png)

# Creación de un Lakehouse en Microsoft Fabric

Este repositorio contiene las evidencias del laboratorio práctico **"Create a lakehouse"**. El objetivo principal fue aprovisionar un entorno de almacenamiento unificado (*Lakehouse*) dentro del espacio de trabajo previamente creado, combinando la flexibilidad del almacenamiento de archivos (*Lake*) con la estructura de tablas relacionales optimizadas bajo el formato Delta Lake (*House*).

---

## 1. Selección del Recurso en el Espacio de Trabajo
* **Descripción:** Dentro del menú de herramientas del espacio de trabajo `dp900-fabric-lakehouse`, se hizo clic en el botón **+ New item** (Nuevo elemento). En el panel de catálogo, se filtró mediante la barra de búsqueda el término `lakehouse`, identificando la tarjeta principal para crear un almacén de datos masivos.

![Búsqueda del elemento Lakehouse](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20184901.png)

---

## 2. Configuración y Creación del Lakehouse
* **Descripción:** Se abrió la ventana de diálogo interactiva *New Lakehouse* para parametrizar el nuevo recurso de datos.
* **Configuración técnica:**
  * **Nombre asignado:** `taxi_lakehouse`.
  * **Ubicación:** Asociado directamente al espacio de trabajo actual.
  * **Característica:** Se mantuvo habilitada la opción **Lakehouse schemas** para dar soporte a la organización lógica y esquemas estructurados de bases de datos.

![Formulario de Creación de taxi_lakehouse](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20185015.png)

---

## 3. Inicialización del Entorno de Almacenamiento Unificado
* **Descripción:** Tras finalizar el proceso automatizado de aprovisionamiento, se desplegó la consola principal del Lakehouse. El panel izquierdo (*Explorer*) muestra la arquitectura base del almacenamiento:
  * **Carpeta Tables (Tablas):** Diseñada para almacenar colecciones estructuradas bajo el formato abierto Delta Lake, organizadas por defecto en el esquema `dbo` y listas para ser consultadas con lenguaje SQL.
  * **Carpeta Files (Archivos):** Destinada a alojar datos en su estado bruto (*raw data*) o de manera temporal sin un esquema rígido asignado, permitiendo además el uso de accesos directos (*shortcuts*).

![Interfaz Inicial de taxi_lakehouse en OneLake](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20185336.png)


# Ingesta de Datos 

Implementar una tarea automatizada de copia sin código (*Copy job*) para extraer un conjunto de datos de prueba externo (NYC Taxi - Green) e importarlo directamente como una tabla administrada dentro de nuestro Lakehouse.

---

## 1. Inicialización de la Tarea de Copia (New Copy Job)
* **Descripción:** En la consola principal de `taxi_lakehouse`, se desplegó el menú superior **Get data** (Obtener datos) y se seleccionó la opción **New copy job** para iniciar el asistente guiado de ingesta.

![Inicio de la Tarea de Copia](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20191443.png)

---

## 2. Creación y Nombramiento de la Tarea
* **Descripción:** Se abrió el cuadro de diálogo interactivo para parametrizar la tarea. Se le asignó el nombre comercial `Ingest Data` dentro del espacio de trabajo del proyecto antes de proceder a la creación del flujo.

![Parámetros de la nueva tarea Ingest Data](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20191523.png)

---

## 3. Conexión al Catálogo de Orígenes
* **Descripción:** Dentro del asistente *Copy job*, en la primera fase (*Choose data source*), la interfaz expone la lista de orígenes de datos disponibles en la plataforma Fabric.

![Catálogo de Conectores de Origen](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20191635.png)

---

## 4. Selección del Dataset de Prueba (NYC Taxi - Green)
* **Descripción:** Se accedió a la pestaña **Sample data** (Datos de muestra) y se seleccionó el conjunto de datos estandarizado `NYC Taxi - Green` (de 2 GB en formato Parquet) diseñado para simular flujos de Big Data.

![Selección de la Muestra NYC Taxi](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20191656.png)

---

## 5. Vista Previa de los Datos (Choose Data)
* **Descripción:** Avanzando a la etapa *Choose data*, el sistema cargó una previsualización estructural del archivo origen, permitiendo inspeccionar las columnas y formatos nativos de los viajes en taxi antes de procesar el flujo.

![Vista Previa de Filas y Columnas del Dataset](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20191731.png)

---

## 6. Configuración del Método de Lectura y Destino (Settings)
* **Descripción:** En la sección *Settings*, se determinó la lógica de ingesta:
  * **Método de lectura:** Copia completa (*Full copy*) para transferir toda la información en una sola corrida.
  * **Carpeta raíz destino:** Directorio de **Tables** (Tablas), garantizando la conversión directa del archivo origen a una estructura Delta Lake consultable.

![Configuración de Copia y Destino](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20192012.png)

---

## 7. Mapeo y Destino de Esquemas (Map to Destination)
* **Descripción:** En el paso *Map to destination*, se configuró el enrutamiento lógico hacia el almacén final. Se estableció el esquema de base de datos por defecto (`dbo`) y se especificó el nombre de la tabla destino (`parquet`).

![Mapeo de la Tabla Hacia dbo.parquet](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20192114.png)

---

## 8. Revisión y Confirmación de Ejecución (Review + Save)
* **Descripción:** Fase final de validación donde se muestra el resumen integral del origen y destino del flujo. Se habilitó el checkbox de inicio inmediato de la transferencia de datos (*Start data transfer immediately*) y se presionó **Save + Run**.

![Resumen General e Inicio del Flujo](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20192133.png)

---

## 9. Monitoreo y Éxito de la Ingesta
* **Descripción:** El panel de control e historial de ejecuciones (*Results*) reportó el estado del proceso en tiempo real. La ingesta finalizó de manera exitosa con estado **Succeeded** tras una duración de 2 minutos y 9 segundos, completando el procesamiento de la tabla (1/1).

![Estado Succeeded del Pipeline de Copia](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20192823.png)

---

## 10. Validación de Datos en la Tabla Delta Lake
* **Descripción:** Al retornar al explorador del Lakehouse, se refrescó el nodo de las tablas y se seleccionó la entidad recién creada. La consola web renderizó la vista de tabla expuesta (*Table view*), confirmando que las primeras 1,000 filas con sus 23 columnas de atributos se estructuraron correctamente bajo el formato Delta Lake.

![Inspección de Registros Ingeridos en taxi_lakehouse](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20193520.png)

# Consulta de Datos en un Lakehouse mediante SQL

Utilizar el punto de análisis de SQL (*SQL analytics endpoint*) integrado en Microsoft Fabric para interrogar la tabla Delta Lake mediante consultas relacionales tradicionales y extraer métricas agregadas sobre los viajes en taxi.

---

## 1. Cambio al Entorno de Análisis SQL (SQL Analytics Endpoint)
* **Descripción:** En la esquina superior derecha del panel del Lakehouse, se interactuó con el selector de vistas para cambiar desde el entorno de archivos hacia el **SQL analytics endpoint**. Esta consola expone las tablas del OneLake bajo una semántica de base de datos relacional optimizada para consultas de lectura.

![Activación del SQL Analytics Endpoint](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20195029.png)

---

## 2. Redacción de la Consulta de Agregación (New SQL Query)
* **Descripción:** Se creó una nueva hoja de trabajo seleccionando **New SQL query**. En el editor de código se estructuró una consulta SQL orientada a agrupar los registros por el nombre del día de la semana (`DATENAME`) y calcular la distancia promedio de los recorridos (`AVG`), tomando como origen de datos la tabla relacional.

![Editor de Consultas con el Script SQL](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20195201.png)

---

## 3. Ejecución del Script y Análisis de Resultados
* **Descripción:** Se presionó el botón **▷ Run** para procesar la consulta en el motor de Fabric. La sección inferior de resultados (*Results*) renderizó exitosamente el reporte consolidado mostrando la métrica calculada (`AvgDistance`) mapeada de manera independiente para cada uno de los 7 días de la semana.

![Métricas y Filas Resultantes de la Consulta SQL](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20195321.png)

## Eliminar Recursos

![Métricas y Filas Resultantes de la Consulta SQL](imagenes_4.1/Captura%20de%20pantalla%202026-07-01%20200230.png)

 