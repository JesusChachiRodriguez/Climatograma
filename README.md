# Análisis Meteorológico
## Tratamiento y transformación de datos

**Lenguajes y/o Programas**
* Python con librerias numpy, pandas, datetime


**Entradas**
* *Temperatura, Humedad, Precipitación, Dirección y Velocidad del viento* Datos meteorológicos de estaciones automáticas del [SENAMHI](https://www.senamhi.gob.pe/?p=estaciones), para este ejemplo se utilizó los datos de la Estación Santiago de Tuna en el 2021.
* *Rosa de Vientos* El rango angular de los [puntos cardinales](https://es.wikipedia.org/wiki/Rosa_de_los_vientos) en ocho rumbos colaterales.
* *Estaciones del año* La duración de las estaciones astronómicas en el [Perú](https://www.gob.pe/11000-fechas-de-las-estaciones-astronomicas-en-el-peru).
* *Control de calidad de datos* Para fines de identificación de datos dudosos se usó las pruebas que el [SENAMHI](https://www.senamhi.gob.pe/load/file/00711SENA-54.pdf) proporciona.

Todos los datos del trabajo se pueden encontrar en la carpeta [data](https://github.com/JesusChachiRodriguez/Climatograma/tree/main/data).

**Procedimiento**

Ver el documento Procedimiento en la carpeta [data](https://github.com/JesusChachiRodriguez/Climatograma/tree/main/data)

**Salidas**
* *dfTh* Temperatura horaria y calidad de datos
* *dfPh* Precipitación horaria y calidad de datos
* *dfHh* Humedad horaria y calidad de datos
* *dfLluviaEstacion* Días con lluvia y estación astronómica
* *df2* Velocidad y dirección del viento horaria 
* *Estacion_descripcion* Ubicación y descripción de la estación meteorológica 

## Visualización

**Lenguajes y/o Programas**
* Power BI
* DAX

**Procedimiento**

* Con *df2* se ordenó la columna Tipo_cardinal por Orden 2 y se realizó la Rosa de Vientos con la extensión Radar/Polar Chart - Viz. La cartilla se configuró para mostrar la dirección con mayor velocidad promedio.

* Con *dfTh* se calculó la temperatura mensual promedio, mínima y máxima. Las cartillas se configuraron para mostrar el promedio de los datos promedios con o sin filtros aplicados, para ello se generó las columnas: Column, max Th, min Th. Luego se generaron medidas para las cartillas con valores promedio mínimos y máximos. 

* Con *dfHh* se calculó la humedad mensual promedio. La cartilla se configuró para mostrar el promedio con o sin filtros aplicados.

* Con *dfPh* se calculó la precipitación acumulada mensual. La cartilla se configuró para mostrar la sumatoria total con o sin filtros aplicados.

* De estas 3 últimas tablas, las columnas TC_Th, TC_Hh y TC_Ph se utilizaron para clasificar los datos en una matriz y ubicarlos en  la fecha correspondiente. Se agregó 3 filtros para estas columnas según la categoría de calidad.

* Con *dfLluviaEstacion* se conectó la columna Fecha con todas las columnas Día de las otras tablas. Se generó un filtro general por estacion astronomica y solo los días de lluvia se sumaron mensualmente.  

* Con *Estacion_descripcion* se usó las coordenadas para generar un mapa de ubicación. Los nombres y el código se plasmaron en unas cartillas.

Ver el documento codigoDAX en la carpeta [data](https://github.com/JesusChachiRodriguez/Climatograma/tree/main/data).

![dashboard final](https://github.com/JesusChachiRodriguez/Meteorologia-/blob/main/data/Estacion_meteorologica_page-0001.jpg)

