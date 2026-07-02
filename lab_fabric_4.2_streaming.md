# Explorar analitics en tiempo real con Fabric
Partiendo de que se ha creado un nuevo workspace se realizaran los siguientes procesos

* **Crear un Eventstream**
* **Crear un Eventhouse y almacenar el stream**
* **Consultar la captura de datos**

# Reporte de Laboratorio: Creación de un Eventstream en Microsoft Fabric

Este repositorio contiene las evidencias del laboratorio práctico **"Create an eventstream"**. El objetivo principal de este ejercicio fue explorar el *Real-Time Hub* de Microsoft Fabric para conectar un flujo continuo de datos en tiempo real (*streaming data*) basado en el origen público de pruebas de taxis amarillos de Nueva York (*Yellow taxi*).

---

## 1. Acceso al Centro de Tiempo Real (Real-Time Hub)
* **Descripción:** En la barra de menús lateral izquierda de la plataforma Fabric, se seleccionó el icono de **Real-Time hub**. La consola de inicio (*Discover, analyze, and act on data-in-motion*) expone los accesos directos para la monitorización y conexión de datos en movimiento.

![Consola Inicial del Real-Time Hub](imagenes_4.2/Captura%20de%20pantalla%202026-07-02%20170038.png)

---

## 2. Exploración del Catálogo de Orígenes de Datos
* **Descripción:** Dentro del menú de navegación del centro de tiempo real, se accedió a la sección **Add data**. El panel desplegado expone el catálogo completo de conectores y transmisiones de muestra disponibles para la suscripción.

![Catálogo de Conectores de Streaming Disponibles](imagenes_4.2/Captura%20de%20pantalla%202026-07-02%20170152.png)

---

## 3. Inicialización del Asistente del Conector (Yellow Taxi)
* **Descripción:** Se localizó la tarjeta de datos de prueba **Yellow taxi** y se hizo clic en *Connect*. El asistente abrió por defecto la pestaña de configuración de conexión, alertando inicialmente sobre los requisitos de licenciamiento para el espacio de usuario base (*My workspace*).

![Advertencia de Capacidad en el Asistente de Conexión](imagenes_4.2/Captura%20de%20pantalla%202026-07-02%20170334.png)

---

## 4. Redirección Hacia el Espacio de Trabajo Técnico
* **Descripción:** Para garantizar la compatibilidad de las características de ingeniería en tiempo real, se desplegó el selector de entornos en la sección *Stream details* y se cambió el destino desde el espacio personal hacia el Workspace dedicado del laboratorio (`dp900-streaming`).

![Seleccin del Workspace Dedicado](imagenes_4.2/Captura%20de%20pantalla%202026-07-02%20170430.png)

---

## 5. Parametrización y Nombramiento del Eventstream
* **Descripción:** Una vez asignado el entorno de trabajo correcto, se editaron los identificadores del flujo:
  * **Source name (Nombre del origen):** `taxi`.
  * **Eventstream name (Nombre del Eventstream):** `taxi-data`.
  * El sistema mapeó de forma automatizada el nombre del flujo interno resultante como `taxi-data-stream`.

![Asignación de Identificadores y Nombres Técnicos](imagenes_4.2/Captura%20de%20pantalla%202026-07-02%20170549.png)

---

## 6. Revisión de Parámetros Previos al Despliegue (Review + Connect)
* **Descripción:** Fase intermedia de validación donde el asistente expone el resumen estructural del flujo (`taxi YellowTaxi -> taxi-data-stream`). Se confirmaron los metadatos de enrutamiento y se presionó el botón **Connect**.

![Resumen Estructural del Flujo de Datos](imagenes_4.2/Captura%20de%20pantalla%202026-07-02%20170705.png)

---

## 7. Confirmación y Aprovisionamiento Exitoso
* **Descripción:** La plataforma ejecutó las tareas en segundo plano. La consola web reportó el estado **Successful** de manera simultánea para los procesos de creación del contenedor central (*Create Eventstream*) y de la fuente emisora (*Create Eventstream source*), habilitando el botón de acceso final **Open Eventstream**.

![Notificación de Despliegue Exitoso del Eventstream](imagenes_4.2/Captura%20de%20pantalla%202026-07-02%20170830.png)

# Reporte de Laboratorio: Creación de un Eventhouse y Almacenamiento de Streams

Este repositorio documenta el desarrollo práctico del laboratorio **"Create an eventhouse and store the stream"**. El objetivo principal fue configurar un destino de almacenamiento persistente optimizado para datos en tiempo real (*Eventhouse*) y enlazarlo de forma directa con el flujo continuo (*Eventstream*) previamente creado en Microsoft Fabric.

---

## 1. Adición de un Destino en el Lienzo de Diseño
* **Descripción:** Con el Eventstream abierto en modo de edición (*Edit mode*), se accedió a la barra de herramientas superior para desplegar las opciones de integración de datos.
* **Acción:** Se seleccionó la opción **Add destination** y se eligió **Eventhouse** como el componente para la persistencia duradera del flujo continuo.

![Menú Desplegable para Agregar Destino](imagenes_4.2/Captura%20de%20pantalla%202026-07-02%20172934.png)

---

## 2. Aprovisionamiento del Nuevo Eventhouse
* **Descripción:** En el panel lateral derecho de configuración, se establecieron las propiedades de la ingesta eligiendo el procesamiento de eventos antes de la inserción (*Event processing before ingestion*).
* **Acción:** Al no contar con una instancia previa, se seleccionó *Create new* para dar de alta un nuevo Eventhouse bajo el nombre técnico `taxi-eventhouse`, vinculándolo al espacio de trabajo del proyecto (`dp900-streaming`).

![Formulario Lateral de Creación de Eventhouse](imagenes_4.2/Captura%20de%20pantalla%202026-07-02%20174123.png)

---

## 3. Estructuración de la Tabla de Destino KQL
* **Descripción:** Continuando con el asistente de configuración del destino, se procedió a definir la estructura de almacenamiento relacional interna de la base de datos Kusto (KQL).
* **Acción:** Se seleccionó *Create new* bajo el campo de tabla destino y se creó la entidad llamada `yellow-taxi`, asegurando que la casilla de activación inmediata de ingesta quedara marcada antes de guardar los cambios.

![Asistente de Configuración de Tabla Yellow-Taxi](imagenes_4.2/Captura%20de%20pantalla%202026-07-02%20174302.png)

---

## 4. Visualización de la Topología en Modo de Edición
* **Descripción:** La interfaz gráfica actualizó el lienzo mostrando el nodo del destino *Eventhouse* conectado al flujo `taxi-data-stream`. La barra superior muestra alertas indicando que las modificaciones permanecen de forma local en modo de borrador hasta que sean distribuidas formalmente.

![Lienzo de Diseño Técnico en Modo Edit](imagenes_4.2/Captura%20de%20pantalla%202026-07-02%20174413.png)

---

## 5. Publicación de la Topología de Datos (Publish Changes)
* **Descripción:** Con la ruta de datos completamente trazada y validada en el lienzo, se procedió a hacer clic en el botón **Publish** para guardar y compilar los cambios en la infraestructura de la nube.
* **Resultado:** El portal desplegó la confirmación de éxito en la esquina superior derecha (*Successfully published. The topology changes were published*), iniciando el aprovisionamiento en caliente del nodo.

![Notificación de Publicación Exitosa](imagenes_4.2/Captura%20de%20pantalla%202026-07-02%20174508.png)

---

## 6. Validación de Ingesta Activa y Vista Previa de Datos
* **Descripción:** Una vez que el sistema cambió al modo en vivo (*Live mode*), todos los componentes de la topología (origen, stream y destino) pasaron a estado **Active** con indicadores verdes.
* **Acción final:** Al seleccionar el nodo del Eventhouse y abrir la pestaña inferior **Data preview**, se refrescó la vista hasta confirmar la llegada continua de registros estructurados con marcas de tiempo, confirmando el éxito del laboratorio.

![Vista Previa de Filas Ingeridas en Tiempo Real](imagenes_4.2/Captura%20de%20pantalla%202026-07-02%20175322.png)