# Convención de nombres Simpro Revision 1°

Este documento detalla las convenciones de nombres y formatos que deben tener todos los repositorios de I&D.



## Convención completa

### Repositorios de frontend:

- **Convención**:

    **<nombre_proyecto>**_frontend

- **Ejemplo**: 
    
    aplicacion_web_frontend


### Repositorios de APIs:

- **Convención**: 
    
    **<nombre_api>**_api

- **Ejemplo**: 
    
    autenticacion_api

### Repositorios de librerías:

- **Convención**: 
    
    **<nombre_libreria>**_lib

- **Ejemplo**: 

    utilidades_comunes_lib

### Repositorios de bases de datos:

- **Convención**: 
    
    **<nombre_base_datos>**_db

- **Ejemplo**: 
    
    clientes_db


### Repositorios de despliegue:

- **Convención**: 

    **<nombre_proyecto>**_deploy

- **Ejemplo**: 

    aplicacion_web_deploy

Repositorios de despliegue para el código fuente estático:

- **Convención**: 

    **<nombre_proyecto>**_static

- **Ejemplo**: 

    aplicacion_web_static

convencion en desarrollo
## Repositorios de bases de datos
Se refiere a un repositorio que contiene el codigo sql y las credenciales de una o más bases de datos de la empresa.


- **Nombre de repositorio**: name_project_db

- **Archivos obligatorios**:

    *  **name_project_tables.sql**: Este archivo debe contener toda la creacion de las tablas de dicha base de datos en formato sql siguiendo este formato.
        ```sql
        ---------------------------------------------------------------------------------------------------------------
        --
        -- PROJECT TEMPLATE
        -- example template db.
        --
        ---------------------------------------------------------------------------------------------------------------
        --
        --table template:
        ----tt_id: table id.
        ----atribute: atribute example.
        --
        CREATE TABLE table_template (
            tt_id SERIAL PRIMARY KEY, 
            atribute VARCHAR(40) NOT NULL,
        );
        ```
    *  **name_project_queries.sql**: Este archivo debe contener exemplos de consultas utiles para cada tabla.
        ```sql
        ---------------------------------------------------------------------------------------------------------------
        --
        --insert template:
        ----tt_id: table id.
        ----atribute: atribute example.
        --
        INSERT INTO table_template 
            (
                atribute,
            )
        VALUES 
            (
                "atribute");
        ```
    *  **name_project_user.sql**: Este archivo contiene las credenciales maestras y de servicio de la base de datos.
        ```sql   
        ---------------------------------------------------------------------------------------------------------------
        --
        -- ADMIN USER:
        --
        CREATE USER test WITH PASSWORD '';
        ALTER DATABASE template_project_db OWNER TO test;
        ---------------------------------------------------------------------------------------------------------------
        --
        -- SERVICE USER:
        --
        CREATE USER template_project_service WITH PASSWORD '';
        GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA public TO template_project_service;
        GRANT ALL PRIVILEGES ON ALL SEQUENCES IN SCHEMA public TO template_project_service;
        ```
*  **readme**: Este debe contener la información general de **acceso** a la base de datos.

## Procedimiento de despliegue de una nueva base de datos

Este procedimiento tiene como fin ultimo terminar con una base de datos en aws levantada y funcionando.

### Procedimiento

- **Levantamiento de requerimientos**: Basados en los requerimentos del proyecto se debe hacer una propuesta de base de base de datos que justifique la nesesidad de una nueva base de datos.

- **Aprobación de una nueva base de datos**: Se debe mandar una solicitud (no nesesariamente por escrito) a la Supervicion de la Unidad y debe ser aprobada por el encargado de Inovacion y desarrollo. En caso de aprobarse la crecion de una nueva base de datos se debe hacer la creacion de un nuevo repositorio basado en [Proyect-template](http://localhost/).
- **Creación de credenciales**: El encargado de la unidad (independiente del cargo) tendra la responsabilidad de generar unas credenciales con un minimo nivel de seguridad.

- **Propuesta de tablas**: Ante el encargado de la unidad deben entregarse una propuesta de tablas en caso de ser aprobada se puede continuar al siguiente paso.

- **Consultas de la base de datos**: se deben entregar minimo una consulta por tabla.

- **Estimación de uso**: Se debe hacer una estimacion de recursos de la base de datos el cual debe quedar por estricto en el readme del repositorio.

- **Entrega del repositorio**: Una ves las tablas y las consultas han sido iteradas suficientes veces para poder ser utilizadas se debe entregar el repositorio a revision.

- **Despliegue de la base de datos**: En base al repositorio se debe crear una base de datos en rds con las estimaciones de uso de esta, este procedimiento debe ser realizado por la persona que quedara acargo de la base de datos quien pasara a ser dueño de la base de datos.

#### Entregables del procedimiento

-  **Base de datos desplegada**: Se entiende que es la base de datos con acceso publico o restringido.
- **Repositorio de la base de datos**: repositorio que contiene toda la documentacion de la base de datos.


#### Dueño de la base de datos:
Persona responsable de la base de datos, tanto para diseño como operacion de esta.
atribuciones unicas
- Despliegue de la base de datos.
- Eliminacion de la base de datos.
- Detencion de la base de datos.
- Aprobación de nuevas tablas.
- Aprobacion de modificacion de tablas.
- Eliminacion de datos.
## Consideraciones en repositorios de bases de datos

-  Repositorio/base de datos sin dueño: se asume que el dueño de algun Repositorio va a ser el encargado de la unidad de informatica y es la unica persona que puede transferir la propiedad de algun artefacto.
## Repositorios Librerias
Se refiere a un repositorio que contiene el codigo que va a ser utilizado por uno o más repositorios


- **Nombre de repositorio**: name_library_lib

- **Archivos obligatorios**:

    *  **setup.py**: Este archivo debe contener toda libreria.
    *  **requirements.txt**: contiene los requerimientos explicitos de la libreria.

## Consideraciones en repositorios de librerias
-  Repositorio/base de datos sin dueño: se asume que el dueño de algun Repositorio va a ser el encargado de la unidad de informatica y es la unica persona que puede transferir la propiedad de algun artefacto.
- se debe mantener actualizada la lista de requerimientos de la libreria junto con la version de python que utiliza

## Used By

This project is used by the following companies:

- Company 1
- Company 2


## Authors

- [@octokatherine](https://www.github.com/octokatherine)


