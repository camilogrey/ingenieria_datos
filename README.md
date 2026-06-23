# Reporte de Laboratorio: Explore Azure Storage

Este repositorio contiene las evidencias del laboratorio práctico **"Explore Azure Storage"**. El objetivo principal fue aprovisionar una cuenta de almacenamiento en Microsoft Azure, comprender las diferencias operativas entre un espacio de nombres plano y uno jerárquico (Azure Data Lake Storage Gen2), gestionar contenedores de blobs y configurar un recurso compartido de archivos clásico (Azure Files).

---

## 1. Creación de Storage account

![Contenedor Data Vacío](RUTA_A_TU_IMAGEN_190603)
![Contenedor Data Vacío](RUTA_A_TU_IMAGEN_191924)
![Contenedor Data Vacío](RUTA_A_TU_IMAGEN_192030)
---

## 2. Creacion del Blob 
![Notificación de Carga Exitosa](RUTA_A_TU_IMAGEN_192308)

---

## 3. Creacion del Conatiner llamado "data"



![Vista del Directorio Virtual en Storage Browser](RUTA_A_TU_IMAGEN_192712)

---

## 4. creación del directorio dentro del Blob llamado "products" y dentro del directorio la carpeta llamada "product_data" y dentor de esta carpeta el se almacena el json "product1.json" Se verifica que el almacenamiento Blob no contienene el order namespace 


![Menú Contextual sin Opciones](RUTA_A_TU_IMAGEN_193125)
![Menú Contextual sin Opciones](RUTA_A_TU_IMAGEN_193459)
![Menú Contextual sin Opciones](RUTA_A_TU_IMAGEN_193546)

---

## 5. Migración e Inserción en Azure Data Lake Storage Gen2
* **Descripción:** Tras ejecutar la actualización de la cuenta mediante la opción *Data Lake Gen2 upgrade* para habilitar el espacio de nombres jerárquico, se subió el archivo `product2.json`. Ambos archivos (`product1` y `product2`) coexisten de forma nativa en la misma ruta bajo la capa de acceso caliente (*Hot Inferred*).

![Convivencia de Archivos en Data Lake Gen2](RUTA_A_TU_IMAGEN_195542)

---

## 6. Habilitación de Operaciones de Directorio Real (Manage ACL)
* **Descripción:** Con la jerarquía de directorios activa, la carpeta pasa a ser un objeto real. Al abrir nuevamente el menú de opciones de la carpeta `product_data` desde la sección de contenedores, la interfaz web ahora despliega funciones avanzadas de administración, incluyendo la edición de permisos (**Manage ACL**) y el renombrado del directorio.

![Menú Contextual Activo con Manage ACL](RUTA_A_TU_IMAGEN_200253)

---

## 7. Inicialización de Azure Files (Classic File Shares)
* **Descripción:** Debido a la presencia del espacio de nombres jerárquico activo en la cuenta, el servicio de archivos compartidos se administra bajo la pestaña *Classic file shares*. En esta vista inicial se comprueba la ausencia de recursos compartidos creados.

![Panel de Classic File Shares Vacío](RUTA_A_TU_IMAGEN_193133)

---

## 8. Formulario de Creación de Unidad de Red Azure Files y creación de unidad de almacenamnto 
* **Descripción:** Configuración de los parámetros para el nuevo recurso compartido. Se le asignó el nombre `files` y se definió el nivel de acceso como optimizado para transacciones (*Transaction optimized*) bajo el estándar SMB.

![Asistente New Classic File Share](RUTA_A_TU_IMAGEN_200200)
![Asistente New Classic File Share](RUTA_A_TU_IMAGEN_200253)
---

## 9. Panel de Conexión y Scripts Multiplataforma
* **Descripción:** Una vez creado el recurso, se abrió la pestaña de conectividad (*Connect*). El portal generó de forma automatizada los scripts de montaje en la unidad `Z:` mediante comandos de consola nativos para Windows, Linux y macOS utilizando el puerto de red `445`.

![Instrucciones de Conexión Multiplataforma](RUTA_A_TU_IMAGEN_200408)

---

## 10. Desmontaje e Eliminación del Grupo de Recursos


![Eliminación de dp900-lab-rg](RUTA_A_TU_IMAGEN_200537)
