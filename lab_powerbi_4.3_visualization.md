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

