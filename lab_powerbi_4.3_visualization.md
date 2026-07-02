# Laboratiorio de visualización en Power BI
Se realizarán los siguientes procesos

* **Importar Datos**
* **Explorar el modelo**
* **Crear un reporte**

# Reporte de Laboratorio: Importación de Datos en Power BI Desktop

Este repositorio documenta el desarrollo práctico del laboratorio **"Import data"**. El objetivo principal fue utilizar Power BI Desktop para ingerir conjuntos de datos externos (archivos CSV de clientes, productos y órdenes) desde una fuente web pública (GitHub) hacia el modelo de datos local, preparando el entorno para el análisis y modelado relacional.

---

## 1. Interfaz Inicial de Power BI Desktop
* **Descripción:** Se ejecutó la aplicación Power BI Desktop. La pantalla de bienvenida y el lienzo principal se muestran vacíos, listos para iniciar un nuevo proyecto de reporte.

![Interfaz Inicial de Power BI Desktop](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20190729.png)

---

## 2. Selección de la Fuente de Datos (Get Data)
* **Descripción:** En la cinta de opciones, se seleccionó **Obtener datos** (*Get data*). Dentro del catálogo de conectores, se utilizó la barra de búsqueda para ubicar y seleccionar el conector **Web**, que permite extraer datos estructurados desde URLs directas.

![Menú Obtener Datos - Conector Web](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20191012.png)

---

## 3. Configuración de la URL de Origen (Customers)
* **Descripción:** En el cuadro de diálogo *De web*, se ingresó la URL directa al archivo de muestra `customers.csv` alojado en el repositorio de GitHub de Microsoft Learning.

![Ingreso de URL para dataset de Clientes](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20191041.png)

---

## 4. Confirmación de Acceso al Contenido Web
* **Descripción:** Al ser la primera vez que se accede a este dominio, Power BI solicitó la configuración de credenciales. Se mantuvo el nivel de acceso **Anónimo** (*Anonymous*) ya que el repositorio es público, y se procedió a **Conectar**.

![Configuración de Acceso Anónimo](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20191055.png)

---

## 5. Vista Previa y Carga del Dataset (Customers)
* **Descripción:** El sistema generó una previsualización de la estructura del archivo CSV reconociendo correctamente el delimitador de comas. Se validó la lectura de las columnas (CustomerID, Name, etc.) y se seleccionó **Cargar** (*Load*) para incorporar los datos al modelo.

![Vista Previa del Archivo Customers.csv](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20191114.png)

---

## 6. Nueva Solicitud de Extracción Web (Products)
* **Descripción:** Se repitió el proceso de ingesta dirigiéndose nuevamente al menú **Obtener datos > Web** para incorporar el segundo conjunto de datos necesario para el modelo.

![Selección del Conector Web para Productos](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20191230.png)

---

## 7. Vista Previa y Carga del Dataset (Products)
* **Descripción:** Tras ingresar la URL correspondiente a `products.csv`, se abrió la ventana de previsualización mostrando el identificador de producto, nombre y categoría. Se procedió con la carga directa al modelo de datos.

![Vista Previa del Archivo Products.csv](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20191302.png)

---

## 8. Ingesta Final del Dataset de Órdenes (Orders)
* **Descripción:** Siguiendo la misma metodología, se abrió la herramienta de extracción Web para vincular la URL del último archivo: `orders.csv`. Esta última carga completa las tres entidades esenciales (Clientes, Productos y Ventas) necesarias para realizar el modelado relacional en los pasos siguientes.

![Ingreso de URL para dataset de Órdenes](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20191347.png)


# Reporte de Laboratorio: Exploración del Modelo de Datos

Organizar, relacionar y refinar las tres tablas importadas (clientes, productos y órdenes) dentro de Power BI Desktop para optimizar su visualización y análisis.

---

## 1. Formato de Moneda para Ingresos (Revenue)
* **Descripción:** En la vista de Modelo (*Model view*), se seleccionó el campo `Revenue` dentro de la tabla `orders`.
* **Acción:** En el panel de Propiedades, se cambió su formato a **Moneda** (*Currency*). Esto garantiza que los valores financieros se representen con el símbolo adecuado en las futuras visualizaciones.

![Formato de Moneda para el Campo Revenue](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20193324.png)

---

## 2. Creación de Jerarquía Base (Category Hierarchy)
* **Descripción:** Se estructuró una relación de desglose de información para el inventario.
* **Acción:** En la tabla `products`, se hizo clic derecho sobre el campo `Category` y se seleccionó la opción **Crear jerarquía** (*Create hierarchy*), generando un nuevo elemento anidado en el modelo.

![Creación de Jerarquía de Categorías](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20193453.png)

---

## 3. Adición de Subniveles a la Jerarquía
* **Descripción:** Se completó la estructura jerárquica agregando el nivel de detalle de los productos.
* **Acción:** Se hizo clic derecho sobre el campo `ProductName`, seleccionando **Agregar a la jerarquía** (*Add to hierarchy*) y eligiendo la jerarquía recién creada. Esto permite funciones de profundización (*drill-down*) en los gráficos.

![Adición de ProductName a la Jerarquía](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20193543.png)

---

## 4. Renombrar la Jerarquía (Categorized Product)
* **Descripción:** Para mejorar la claridad semántica del modelo de datos de cara a los usuarios de negocio.
* **Acción:** Desde el panel de Propiedades, se modificó el nombre predeterminado de la jerarquía a **Categorized Product**.

![Renombrado de la Jerarquía en el Panel de Propiedades](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20194243.png)

---

## 5. Transición a la Vista de Tabla (Table View)
* **Descripción:** Se procedió a explorar los datos a nivel de fila individual.
* **Acción:** En el menú lateral izquierdo, se cambió de la Vista de Modelo a la **Vista de Tabla** (*Table view*), visualizando los registros crudos ingeridos y localizando la tabla de clientes.

![Transición a la Vista de Tabla](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20194413.png)

---

## 6. Configuración de Categoría Geográfica (City)
* **Descripción:** Se instruyó a Power BI sobre la naturaleza espacial de los datos de ubicación.
* **Acción:** Dentro de la tabla `customers`, se seleccionó la columna `City`. En la cinta de herramientas de columnas, se cambió su **Categoría de datos** (*Data Category*) a **Ciudad** (*City*), optimizando el campo para su uso correcto en mapas.

![Configuración de Categoría de Datos para Ciudades](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20194509.png)

# Creación de un Informe en Power BI

Generar visualizaciones gráficas interactivas y analizar el modelo de datos construido previamente.

---

## 1. Configuración de Visualizaciones de Mapas
* **Acción:** En el menú de Opciones y Configuración > Seguridad, se habilitó la casilla **Use Map and Filled Map visuals**.
* **Objetivo:** Garantizar que los componentes geoespaciales se rendericen correctamente en el lienzo.

![Habilitación de Mapas en Opciones](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20195957.png)

---

## 2. Acceso a la Vista de Informe
* **Acción:** Se seleccionó el icono de **Vista de informe** (*Report view*) en el margen izquierdo.
* **Objetivo:** Abrir el lienzo en blanco para comenzar el diseño del panel interactivo.

![Interfaz de Vista de Informe](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20200331.png)

---

## 3. Inserción del Título del Informe
* **Acción:** Se agregó un cuadro de texto en la parte superior con la leyenda **"Sales Report"**.
* **Formato:** Texto en negrita con un tamaño de fuente de 32 para destacar el propósito del panel.

![Título del Informe](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20200503.png)

---

## 4. Creación de Tabla Base de Productos
* **Acción:** Se hizo clic en un área vacía y se seleccionó el campo jerárquico **Categorized Product** desde la tabla `Products`.
* **Resultado:** Inserción automática de un componente de tabla en el lienzo.

![Tabla de Productos Categorizados](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20200550.png)

---

## 5. Integración de la Métrica de Ingresos (Revenue)
* **Acción:** Con la tabla seleccionada, se marcó el campo **Revenue** de la tabla `Orders`.
* **Resultado:** Los ingresos se añadieron como una nueva columna en la tabla, mostrando el formato de moneda configurado previamente.

![Tabla con Columna de Ingresos](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20200701.png)

---

## 6. Conversión a Gráfico de Columnas Apiladas
* **Acción:** Se cambió el tipo de visualización seleccionando el **Gráfico de columnas apiladas** (*Stacked column chart*) en el panel lateral.
* **Resultado:** Transformación de la tabla en un gráfico que facilita la comparación de ingresos por categoría.

![Gráfico de Columnas Apiladas](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20200755.png)

---

## 7. Función de Profundización (Drill-down)
* **Acción:** Se activó el modo de profundización (icono **↓**) y se hizo clic en una columna.
* **Resultado:** Desglose interactivo que muestra los ingresos específicos de los productos individuales dentro de la categoría seleccionada.

![Visualización de Drill-down por Producto](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20200956.png)

---

## 8. Retorno a la Vista Principal (Drill-up)
* **Acción:** Se utilizó el botón de subida (icono **↑**) para regresar a la vista consolidada de categorías y se desactivó la función de profundización.

![Gráfico Consolidado tras el Drill-up](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20201018.png)

---

## 9 y 10. Gráfico Circular de Cantidad por Categoría
* **Acción:** En un espacio en blanco, se cruzaron los campos **Quantity** (`Orders`) y **Category** (`Products`), transformando el resultado en un **Gráfico circular** (*Pie chart*).
* **Resultado:** Representación visual que resalta la contribución proporcional del volumen de ventas.

![Gráfico Circular de Cantidades](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20201123.png)

---

## 11. Mapa Geoespacial de Ingresos por Ciudad
* **Acción:** Se seleccionó el campo **City** (`Customers`) y **Revenue** (`Orders`).
* **Resultado:** Generación de un mapa interactivo con burbujas de calor que muestran los ingresos geolocalizados.

![Mapa de Ingresos por Ciudad](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20201243.png)

---

## 12. Interacción de Resaltado Cruzado
* **Acción:** Se seleccionó una ciudad específica directamente en el mapa.
* **Resultado:** Las demás visualizaciones (columnas y gráfico circular) se filtraron dinámicamente para resaltar únicamente los datos de la ciudad elegida (*Cross-highlighting*).

![Resaltado Cruzado Interactivo](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20201307.png)

---

## 13. Guardado del Proyecto
* **Acción:** Se guardó el progreso en el menú Archivo > Guardar.
* **Resultado:** Creación del archivo `.pbix` local, empaquetando el modelo de datos, conexiones y visualizaciones.

![Guardado del Archivo PBIX](imagenes_4.3/Captura%20de%20pantalla%202026-07-02%20201414.png)