# Documentación de Automatización en Arquitectura Hexagonal

## Índice de Contenido

### [00:09 - Introducción](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=9)

* Presentación y propósito del video.
* Explicación del automatizador para construir capas en una arquitectura hexagonal.

### [00:28 - Explicación del archivo Format.csv](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=28)

* Organización de la estructura de datos.
* Diferencias entre casos con y sin group.

### [00:57 - Ejemplo sin group (WhatsAppAction)](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=57)

* Migraciones requeridas.
* Estructura de la tabla WhatsAppAction.
* Nomenclatura del BoundedContext.
* Uso de nombres singulares en las tablas.
* Clave primaria y restricciones de columnas.

### [03:27 - Ejemplo de una tabla relacional (WhatsAppApplicationStates)](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=207)

* Explicación de tablas pivote y relacionales.
* Definición de claves foráneas y su relación.
* Ejemplo con WhatsappActionTemplate.
* Tipos de relaciones (1 a muchos).
* Restricciones cascade delete.

### [05:50 - Ejemplo con más restricciones y validaciones](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=350)

* Uso de atributos adicionales como max\_length.
* Definición de restricciones de longitud en columnas.

### [07:02 - Transición a ejemplos con group](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=422)

* Introducción a estructuras con agrupaciones.
* Explicación de restricciones adicionales aplicadas en grupos.

### [07:33 - Finalización del caso sin group y validaciones adicionales](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=453)

* Explicación de validaciones como max\_length.
* Importancia de definir correctamente restricciones para datos.

### [07:48 - Ejemplo con group (CreditService)](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=468)

* Diferencias entre estructuras con y sin grupos.
* Estructura del Domain Layer en un sistema con grupos.

### [08:12 - Comparación entre estructuras con y sin group](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=492)

* Ejemplo con CommunicationService (sin group).
* Ejemplo con CreditService (con group).
* Explicación de cómo los archivos se organizan en carpetas según la estructura del sistema.

### [08:40 - Ejemplo con group en la entidad Status](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=520)

* Definición de group state.
* Importancia de usar nombres en minúsculas y en singular.
* Impacto en la generación de scripts y automatización.

### [09:38 - Migraciones en estructuras con group (ejemplo con Credit)](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=578)

* Explicación de la estructura de migraciones en una tabla de créditos.
* Uso de nombres singulares en las tablas para evitar errores en scripts.
* Definición de claves primarias (UUID).
* Restricciones como unique y autoincrement.

### [10:52 - Ejemplo con Credit ID y User UUID](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=652)
- Diferencias entre UUID y UnsignedBigInteger.
- Aplicación de restricciones como unique.
- Explicación de cómo interpretar los datos de la migración.

### [11:00 - Continuación de la estructura de atributos en tablas](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=660)
- Definición de user_uuid, status_uuid y otros atributos clave.
- Explicación sobre tipos de datos (UUID, Decimal, Integer).
- Restricciones en atributos como 15-2 para decimales.

### [11:25 - Ejemplo de atributos adicionales y restricciones](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=685)
- interest_rate y number_of_payments.
- Importancia de definir restricciones explícitas en las migraciones.
- Uso del tipo timestamp y su condición nullable.

### [12:00 - Uso de la barra vertical | para definir relaciones y restricciones](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=720)
- Explicación de cómo se documentan atributos relacionales.
- Ejemplos de restricciones y relaciones en atributos.

### [12:21 - Resumen de la estructura de los archivos CSV](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=741)
- Definición de BoundedContext, TableName y atributos.
- Diferencias entre estructuras con y sin group.
- Convención de nombres: minúsculas y singulares.

### [12:55 - Ejemplo de estructura con group](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=775)
- Comparación entre tablas con agrupaciones y sin ellas.
- Posibilidad de múltiples tablas dentro de un grupo.

### [13:12 - Introducción a la automatización con el script](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=792)

* Explicación del propósito del script.
* Inicio de la demostración del funcionamiento del script.
* Disponibilidad del script en GitHub para compartirlo.

### [13:30 - Acceso al Script y Configuración del Entorno](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=810)

* Disponibilidad del script en GitHub.
* Requisitos para acceder y ejecutar el script.

### [13:37 - Compilación del Script en Python](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=817)

* Uso de main.py como punto de entrada.
* Preferencia por Anaconda para gestionar entornos de desarrollo.
* Instalación y configuración de Anaconda para evitar conflictos de paquetes.

### [13:47 - Ejecución en Distintos Entornos](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=827)

* Uso de Anaconda Navigator.
* Alternativa de ejecución en Python 3 sin Anaconda.

### [14:27 - IDE Recomendados para Desarrollo](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=867)

* Preferencia por PyCharm y Visual Studio Code.
* Configuración del entorno de ejecución en PyCharm.

### [14:45 - Apertura y Ejecución del Script en PyCharm](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=885)

* Cómo abrir main.py dentro del entorno configurado.
* Verificación de dependencias y preparación del entorno.

### [15:00 - Entorno de Pruebas con XAMPP y Laravel](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=900)

* Uso de XAMPP para pruebas locales.
* Configuración de un entorno Laravel para pruebas del script.
* Ejecución y depuración en PHPStorm.

### [15:30 - Consideraciones para Desarrollo en Servidores Locales y Remotos](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=930)
- Diferencias entre desarrollo local y servidor.
- Configuración recomendada para pruebas eficientes.

### [15:37 - Diferentes Métodos de Configuración](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=937)
- Explicación de dos maneras de configurar el entorno.

### [16:20 - Organización de Archivos y Carpetas](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=980)
- Eliminación de carpetas innecesarias.
- Compartición de carpetas básicas del shared.

### [16:47 - Configuración del Bounded Context](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1007)
- Uso del BoundedContext correcto.
- Copia del path absoluto para su ejecución.

### [17:00 - Configuración del main.py](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1020)
- Opciones disponibles en la ejecución del script.
- Ubicación y edición en la línea 50.
- Modificación entre development y production.

### [17:22 - Ejecución del Script](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1042)
- Selección del archivo main.py.
- Diferentes opciones al ejecutar el script.

### [17:27 - Carga de Archivos CSV](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1047)
- Selección del archivo format.csv.
- Carga y validación de la ruta absoluta.

### [17:59 - Ejecución del Proceso](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1079)
- Selección del archivo CSV.
- Inicio del procesamiento.

### [18:00 - Selección de Carpeta de Salida](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1080)
- Copia del path de la carpeta de salida (phpStorm).
- Configuración para almacenar la salida generada.

### [18:21 - Ejecución del Proceso de Generación](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1101)
- Inicio del proceso de generación de archivos.
- Creación del archivo output.zip en modo Producción.

### [18:43 - Verificación de la Salida Generada](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1123)
- Copia y apertura del output.zip.
- Extracción de los archivos generados.

### [19:00 - Exploración de Archivos Generados](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1140)
- Estructura de carpetas generadas (credit y WhatsappManagement).
- Validación de los BoundedContext procesados.

### [19:34 - Comparación con el Archivo de Formato](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1174)
- Verificación de los BoundedContext cargados en format.csv.
- Confirmación de que solo se generaron los BoundedContext especificados.

### [19:47 - Exploración del Dominio "Créditos"](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1187)
- Diferencias entre nombres en singular y plural.
- Código adicional para versiones antiguas de PHP.
- Generación automática de CRUD básico y excepciones.

### [20:30 - Generación Automática del CRUD](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1230)
- Implementación del CRUD en la capa de aplicación.
- Respuesta generada basada en el format.csv.

### [21:04 - Automatización de la Estructura](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1264)
- Pruebas iniciales del sistema.
- Posibilidad de extender la automatización a la infraestructura.

### [21:39 - Revisión del "WhatsappManagement"](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1299)
- Organización de archivos dentro del BoundedContext.
- Generación automática sin subdivisión de carpetas.

### [22:06 - Beneficios de la Automatización](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1326)
- Eliminación del trabajo manual en la generación de estructuras.
- Enfoque en la infraestructura y mejoras específicas.

### [23:31 - Revisión de la Estructura Generada](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1411)
- Validación de CRUDs, acciones y respuestas en singular y plural.
- Primera versión del código, con posibilidad de optimización.

### [23:50 - Depuración y Eliminación de Archivos Temporales](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1430)
- Eliminación del output.zip después de la validación.
- Trabajo en entornos locales o remotos.

### [24:01 - Ejecución y Selección de Carpeta de Descarga](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1441)
- Carga del CSV en el sistema.
- Especificación de la carpeta de salida (ejemplo: Descargas).

### [24:20 - Revisión del "Shared Básico"](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1460)
- Generador de UUIDs, Value Objects, y Excepciones Básicas.
- Tipos de valores predefinidos: Array, Float, Integer, String.
- Infraestructura y persistencia con Eloquent NotFound.

### [25:00 - Conclusión y Personalización del Proyecto](https://soularius.github.io/DOC-AUTOMATIZATION-HEXAGONAL/timeleft_video.html?time=1500)
- Explicación del enfoque modular y escalable del sistema.
- Personalización de Requests y funcionalidades específicas.
- Mensaje final y cierre del video.