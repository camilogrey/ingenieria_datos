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

