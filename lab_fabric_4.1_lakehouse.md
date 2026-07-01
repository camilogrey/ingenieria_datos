# Reporte de Laboratorio: Creación de un Workspace en Microsoft Fabric

Este repositorio contiene las evidencias del laboratorio práctico **"Create a workspace"**. El objetivo de este ejercicio fue inicializar el entorno de trabajo dentro de la plataforma Microsoft Fabric, habilitando la capacidad de prueba (*Fabric Trial*) para disponer de la potencia de cómputo necesaria para tareas de ingeniería de datos.

---

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