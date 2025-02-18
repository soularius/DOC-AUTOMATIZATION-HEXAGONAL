# Procesador de Arquitectura Hexagonal en Laravel

## 📌 Descripción

Este proyecto es una herramienta que genera la estructura básica de una arquitectura hexagonal en PHP para Laravel. A partir de un archivo CSV, crea los diferentes componentes organizados en capas según el modelo hexagonal, permitiendo una mejor separación de responsabilidades y escalabilidad del código.

## 🚀 Características

- Generación de estructuras de dominio, aplicación e infraestructura basadas en un archivo CSV.
- Implementación de acciones CRUD automáticas en la capa de aplicación.
- Creación de repositorios, entidades y objetos de valor en la capa de dominio.
- Soporte para contexto delimitado (bounded context) y grupos de tablas.
- Interfaz gráfica para cargar archivos CSV y definir la carpeta de salida.
- Compresión del resultado en un archivo ZIP.

## 🔧 Requisitos

- Python 3.8 o superior
- Librerías adicionales:
  - `tkinter` (para la interfaz gráfica)
  - `pandas` (para procesamiento de CSV)
  - `shutil`, `zipfile` (para gestión de archivos)

## 🏗️ Estructura del Proyecto

La estructura principal del proyecto está organizada de la siguiente manera:

```
.
├── Basic Shared/               # Carpeta con elementos compartidos básicos
│   ├── Domain/
│   │   ├── ValueObjects/
│   │   │   ├── ArrayValueObject.php
│   │   │   ├── FloatValueObject.php
│   │   │   ├── IntegerValueObject.php
│   │   │   ├── StringValueObject.php
│   │   ├── Collection.php
│   │   ├── CollectionInterface.php
│   │   ├── DomainException.php
│   │   ├── UuidGenerator.php
│   ├── Infrastructure/
│   │   ├── Exceptions/
│   │   │   ├── NotFoundException.php
│   │   ├── Persistence/
│   │   │   ├── Eloquent/
│   │   │   │   ├── EloquentException.php
│   │   │   ├── Requests/
│   │   │   │   ├── InfrastructureException.php
│   │   ├── RamseyUuidGenerator.php
├── Layers/                    # Contiene la lógica de negocio y estructura principal
│   ├── ApplicationLayer/
│   │   ├── Actions/
│   │   ├── Responses/
│   │   ├── ApplicationLayer.py
│   ├── DomainLayer/
│   │   ├── ValueObjects/
│   │   ├── DomainLayer.py
│   │   ├── DomainLayerEntity.py
│   │   ├── DomainLayerException.py
│   │   ├── DomainLayerInterfaceObjectRepository.py
│   │   ├── DomainLayerValueObjects.py
│   ├── BoundedContext.py      # Manejo del contexto delimitado
├── Output/                   # Carpeta de salida donde se genera el código
├── temp/                     # Carpeta temporal para archivos generados
├── Templates/                # Plantillas para generación de código
├── Tools/                    # Utilidades y herramientas
│   ├── ToolsFiles.py         # Utilidades para manejo de archivos
│   ├── TypeValueObject.py    # Definición de tipos de objetos de valor
├── main.py                   # Punto de entrada principal del programa
├── InterfazView.py           # Interfaz gráfica para selección de archivo y carpeta
├── OutputManager.py          # Gestión de salida y compresión de archivos
├── ProcessContext.py         # Procesamiento del contexto y generación de código
├── ReadFormat.py             # Análisis y lectura del archivo CSV
├── format.csv                # Archivo de ejemplo para generación de código
└── .gitignore                 # Archivo para ignorar archivos en Git
```

## 🖥️ Uso

Este automatizador facilita la generación de las capas `ApplicationLayer` y `DomainLayer` dentro de una arquitectura hexagonal en Laravel. Su propósito principal es reducir el tiempo de desarrollo al generar automáticamente estructuras y archivos con base en un archivo CSV de configuración.

### Estructura del Archivo CSV

El archivo CSV contiene la definición del `bounded_context`, los nombres de las tablas y sus atributos. Se pueden definir relaciones entre tablas y restricciones como `unique`, `nullable` y `cascade`.

Existen dos formas de estructurar los datos:

1. **Sin grupos**: Los archivos generados se crean directamente dentro del contexto especificado.
2. **Con grupos**: Se agrupan las tablas dentro de carpetas específicas, permitiendo una mejor organización del código.

### Reglas de Nomenclatura

- **Bounded Context**: Se debe definir en minúsculas y en singular (`bounded_context:whatsapp`).
- **Tablas**: Se deben definir en singular (`table_name:whatsapp_action`).
- **Atributos**: Se deben definir con su tipo de dato y restricciones (`id:uuid:primary`).
- **Relaciones**: Se definen con el prefijo `relation` e incluyen el atributo referenciado y la acción (`action_id:uuid:relation|id.whatsapp_action.OM:delete|cascade`).

### Ejecución

Para ejecutar el script:

1. **En modo producción**

   - Se abre la interfaz gráfica.
   - Se selecciona el archivo CSV y la carpeta de salida.
   - Se genera un archivo ZIP con los archivos estructurados.
2. **En modo desarrollo**

   - Se ejecuta el script en un entorno local de Python 3+ con Anaconda o Visual Studio Code.
   - Se edita el `main.py` para definir `mode = "DEV"` y se ejecuta el script manualmente.

### Resultados

El sistema generará archivos organizados según el `bounded_context` y los `group`, incluyendo:

- **ApplicationLayer**: Acciones (`Create`, `Find`, `List`, `Remove`, `Update`) y Respuestas.
- **DomainLayer**: Repositorios, Objetos de Valor y Entidades.
- **Estructura basada en grupos**: Si el CSV define grupos, los archivos se organizarán en subcarpetas.

Este proceso permite automatizar la generación de código y enfocarse en la personalización de la infraestructura y lógica del negocio. Si bien la herramienta aún se encuentra en su primera versión, se planean mejoras para automatizar aún más la capa de infraestructura.

Este automatizador ayuda a construir rápidamente las capas de `ApplicationLayer` y `DomainLayer` dentro de la estructura hexagonal en Laravel. Su propósito es organizar la estructura de datos y generar automáticamente el código basado en un archivo CSV de configuración. Existen dos casos principales:

1. **Estructuras sin `group`**: Las tablas se generan directamente dentro del contexto delimitado (`bounded_context`).
2. **Estructuras con `group`**: Las tablas se organizan dentro de grupos específicos para mejorar la segmentación del código.

### Reglas y convenciones

- **Nombres en singular**: Se recomienda utilizar nombres en singular para tablas y grupos.
- **Formato del `bounded_context`**: Debe escribirse en minúsculas y sin espacios.
- **Definición de claves primarias**: Se deben especificar los identificadores y sus relaciones claramente.
- **Uso de separadores (`|`)**: Permite definir restricciones como longitudes máximas y tipos de datos.

### Ejecución del Programa

### Modo Productivo

Cuando se ejecuta en modo productivo, se abrirá una ventana en la cual se podrá seleccionar el archivo `format.csv` y la carpeta de salida para la generación del código. El sistema procesará los datos y generará un archivo ZIP con todos los archivos generados.

Ejecuta el siguiente comando para abrir la interfaz gráfica:

```bash
python main.py
```

1. Selecciona un archivo CSV con la estructura de la base de datos.
2. Escoge la carpeta de salida para almacenar los archivos generados.
3. El sistema procesará el archivo y generará la estructura en la carpeta seleccionada.

### Modo Desarrollador

El modo de ejecución se define en el archivo `main.py` estableciendo la variable `mode`. Para ejecutar en modo desarrollador, edita `main.py` y establece:

```python
if __name__ == '__main__':
    mode = "DEV"
    if mode == "DEV":
        run_developer()
    else:
        run_productive()
```

Esto usará un archivo CSV predeterminado (`./Format/format.csv`) y guardará la salida en `./temp/`. Para cambiar a modo productivo, ajusta `mode` a `"PROD"`.

## 📂 Ejemplo de Estructura Generada

La generación de archivos sigue esta estructura de salida basada en el `bounded_context` y los `group` definidos en el archivo CSV:

```
├── Output/                   # Carpeta de salida donde se genera el código
│   ├── CreditManagement/
│   │   ├── ApplicationLayer/
│   │   │   ├── Actions/
│   │   │   │   ├── Credit/
│   │   │   │   ├── CreditPayment/
│   │   │   │   ├── PersonalReference/
│   │   │   │   ├── State/
│   │   │   ├── Responses/
│   │   │   │   ├── Credit/
│   │   │   │   ├── CreditPayment/
│   │   │   │   ├── PersonalReference/
│   │   │   │   ├── State/
│   │   ├── DomainLayer/
│   │   │   ├── Credit/
│   │   │   ├── CreditPayment/
│   │   │   ├── PersonalReference/
│   │   │   ├── State/
│   ├── WhatsappManagement/
│   │   ├── ApplicationLayer/
│   │   │   ├── Actions/
│   │   │   ├── Responses/
│   │   ├── DomainLayer/
│   │   │   ├── ValueObjects/
│   │   │   │   ├── IWhatsappActionRepository.php
│   │   │   │   ├── IWhatsappActionTemplateRepository.php
│   │   │   │   ├── IWhatsappApplicationRepository.php
│   │   │   │   ├── IWhatsappApplicationStateRepository.php
```

## 📜 Ejemplo de Archivo [CSV](https://github.com/soularius/AUTOMATIZATION-HEX-LARAVEL/blob/master/Format/format.csv)

El archivo CSV puede definir un contexto delimitado (`bounded_context`) y opcionalmente un grupo (`group`). Debe seguir una estructura como la siguiente:

```
bounded_context:whatsapp
table_name:whatsapp_action;id:uuid:primary;name:string:unique;timestamps
...
bounded_context:credit
group:state
table_name:state;id:uuid:primary;name:string|50:unique;code:string|50:unique;timestamps
group:credit
table_name:credit;id:uuid:primary;credit_id:unsignedBigInteger:unique:autoIncrement;user_uuid:uuid;currency_uuid:uuid;status_uuid:uuid;principal:decimal|15|2;annual_interest_rate:decimal|5|2;num_payments:integer;credit_start_date:date;credit_end_date:date;disbursement_date:timestamp:nullable;timestamps
group:credit_payment
table_name:credit_payment;id:uuid:primary;credit_payment_id:unsignedBigInteger:unique:autoIncrement;credit_id:uuid:relation|id.credit.OM.credit:delete|cascade;payment_date:date;amount_paid:decimal|15|2;interest_paid:decimal|15|2;principal_paid:decimal|15|2;remaining_balance:decimal|15|2;payment_method:string|50;status_uuid:uuid;timestamps
group:personal_reference
table_name:personal_reference;id:uuid:primary;name:string;last_name:string;relationship:string;phone:string;workplace:string;type_reference:string;credit_id:uuid;timestamps
```

En este ejemplo:

- `bounded_context` define un contexto principal, como `whatsapp` o `credit`.
- `group` (opcional) agrupa las tablas dentro de un contexto, como `state` o `credit_payment`.
- `table_name` define la estructura de cada tabla, con sus atributos y relaciones.

Esto generará una estructura dentro del contexto `WhatsappManagement` con la tabla `whatsapp_action`.

## 👨‍💻 Autor

Desarrollado por: **Ing. Yined Milanyela Molina Barrios**

[https://github.com/soularius](https://)

[https://www.linkedin.com/in/yined-milanyela-molina-barrios/](https://)

Empresa: **OPPERWEB**

[https://opperweb.com/](https://)

## 🔮 Software

[https://github.com/soularius/AUTOMATIZATION-HEX-LARAVEL](https://)
