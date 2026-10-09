# RetailPro: Proyecto SQL y Power BI

## Descripción

RetailPro es un proyecto de análisis de datos para una distribuidora de tecnología. El repositorio reúne los scripts SQL utilizados para crear y consultar la base de datos, junto con los archivos desarrollados en Power BI Desktop.

Los scripts SQL se ejecutan sobre SQL Server, utilizando SQL Server Management Studio (SSMS) y la base de datos `Ventas_Tech_DB`.

Los archivos de Power BI Desktop fueron construidos a partir del archivo `Pipeline_ETL_Dataset.xlsx` provisto por el curso.

## Estructura del repositorio

```text
checkpoint/
├── README.md
├── Ventas_Tech_DB.sql
├── m4_consultas_negocio.sql
├── m5_consultas_joins.sql
├── Pipeline_ETL_Dataset.xlsx
├── Pipeline_ETL_Mónaco_Marina.pbix
├── Pipeline_ETL_Documentacion_Mónaco_Marina.docx
├── Boceto_Dashboard_RetailPro_Marina_Mónaco.png
├── Mónaco_Marina_Checkpoint2.pbix
├── Mónaco_Marina_Checkpoint2.docx
└── Marina_Mónaco_Preentrega9.docx
```

## Herramientas utilizadas

* **SQL Server:** motor de base de datos utilizado para ejecutar los scripts SQL.
* **SQL Server Management Studio (SSMS):** entorno utilizado para ejecutar y trabajar con las consultas SQL.
* **Power BI Desktop:** herramienta utilizada para construir los archivos `.pbix`.

## Scripts SQL

### `Ventas_Tech_DB.sql`

Este script crea las tablas de la base de datos `Ventas_Tech_DB` y carga los datos.

El comando `CREATE DATABASE` se encuentra comentado para permitir volver a ejecutar el script sin generar un error por intentar crear nuevamente una base de datos existente.

### `m4_consultas_negocio.sql`

Consultas de métricas de negocio sobre la tabla ventas.

* Consulta 1 — Resumen ejecutivo mensual
* Consulta 2 — Ranking de productos
* Consulta 3 — Clientes recurrentes
* Consulta 4 — Meses por encima/por debajo del promedio

### `m5_consultas_joins.sql`

Consultas que cruzan las tablas de la base.

* Consulta 1 — Vista base del proyecto (INNER JOIN)
* Consulta 2 — Clientes sin ventas (LEFT JOIN)
* Consulta 3 — Productos sin ventas (LEFT JOIN)
* Consulta 4 — Consolidado por canal (UNION ALL)

## Cómo ejecutar los scripts SQL

1. Abrir SQL Server Management Studio (SSMS).
2. Conectarse a la instancia de SQL Server correspondiente.
3. Abrir el archivo:

   ```text
   Ventas_Tech_DB.sql
   ```

4. La primera vez, descomentar la línea `CREATE DATABASE Ventas_Tech_DB;` y ejecutarla para crear la base. Después volver a comentarla: el resto del script se puede ejecutar todas las veces que sea necesario, porque elimina y vuelve a crear las tablas.
5. Ejecutar el script para crear las tablas y cargar los datos de `Ventas_Tech_DB`.
6. Abrir:

   ```text
   m4_consultas_negocio.sql
   ```

   y ejecutar las consultas de análisis de negocio.
7. Abrir:

   ```text
   m5_consultas_joins.sql
   ```

   y ejecutar las consultas basadas en JOINs.

Los scripts de análisis deben ejecutarse sobre la base `Ventas_Tech_DB`.

## Archivos de Power BI

El repositorio contiene los archivos desarrollados en Power BI Desktop:

* `Pipeline_ETL_Mónaco_Marina.pbix`: pipeline ETL en Power Query. Conexión a `Pipeline_ETL_Dataset.xlsx`, limpieza de duplicados y nulos, y carga de las tablas.
* `Mónaco_Marina_Checkpoint2.pbix`: modelo de datos con cuatro relaciones, incluida Dim_Categorias → Dim_Productos (esquema copo de nieve), tabla calendario Dim_Fechas, tabla _Medidas y cinco medidas DAX.
* `Pipeline_ETL_Documentacion_Mónaco_Marina.docx` y `Mónaco_Marina_Checkpoint2.docx`: documentación paso a paso de cada archivo.
* `Boceto_Dashboard_RetailPro_Marina_Mónaco.png`: boceto del dashboard de RetailPro.

Los archivos de Power BI fueron construidos a partir de `Pipeline_ETL_Dataset.xlsx`, archivo provisto por el curso.

## Uso de IA en el proyecto

* `Marina_Mónaco_Preentrega9.docx`: documentación del uso de IA en el proyecto: revisión de la consulta base de `m5_consultas_joins.sql`, hallazgos a partir de los resultados de `m4_consultas_negocio.sql`, generación de este README y reflexión final.
