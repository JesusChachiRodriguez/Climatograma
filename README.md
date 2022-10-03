# Análisis Meteorológico
## Tratamiento y transformacion de datos

**Lenguajes y/o Programas**
* Python con librerias numpy, pandas, datetime


**Entradas**
* *Temperatura, Humedad, Precipitacion, Direccion y Velocidad del viento* Datos meteorológicos de estaciones automáticas del [SENAMHI](https://www.senamhi.gob.pe/?p=estaciones), para este ejemplo se utilizó los datos de la Estación Santiago de Tuna en el 2021.
* *Rosa de Vientos* El rango angular de los [puntos cardinales](https://es.wikipedia.org/wiki/Rosa_de_los_vientos) en ocho rumbos colaterales.
* *Estaciones del año* La duracion de las estaciones astronomicas en el [Peru](https://www.gob.pe/11000-fechas-de-las-estaciones-astronomicas-en-el-peru).
* *Control de calidad de datos* Para fines de identificacion de datos dudosos se utilizo las pruebas que el [SENAMHI](https://www.senamhi.gob.pe/load/file/00711SENA-54.pdf) proporciona.

Todos los datos usados en el trabajo se pueden encontrar en la carpeta [data](https://github.com/JesusChachiRodriguez/Climatograma/tree/main/data).

**Procedimiento**

Ver el documento Procedimiento en la carpeta [data](https://github.com/JesusChachiRodriguez/Climatograma/tree/main/data)

**Salidas**
* *dfTh* Temperatura horaria y calidad de datos
* *dfPh* Precipitacion horaria y calidad de datos
* *dfHh* Humedad horaria y calidad de datos
* *dfLluviaEstacion* Dias con lluvia y estacion astronomica
* *df2* Velocidad y direccion del viento horaria 
* *Estacion_descripcion* Ubicacion y descripcion de la estacion meteorologica 

## Visualizacion

**Lenguajes y/o Programas**
* Power BI con la extension de graficos Radar/ Polar Chart - Viz
* DAX

**Procedimiento**

* Con *df2* se ordeno la columna Tipo_cardinal por Orden 2 y se realizo la Rosa de Vientos. La cartilla se configuro para mostrar la direccion con mayor velocidad promedio.

* Con *dfTh* se calculo la temperatura mensual promedio, minima y maxima. Las cartillas se configuraron para mostrar el promedio de los datos promedios con o sin filtros aplicados, para ello se genero las columnas: Column, max Th, min Th. Luego se generaron medidas para las cartillas con valores promedio minimos y maximos. Con la columna TC_Th se realizo la tabla calidad de datos, dividiendolo segun  

* Con *dfHh* se calculo la humedad mensual promedio. La cartilla se configuro para mostrar el promedio con o sin filtros aplicados.

* Con *dfPh* se calculo la precipitacion acumulada mensual. La cartilla se configuro para mostrar la sumatoria total con o sin filtros aplicados.

* De estas 3 ultimas tablas , las columnas TC_Th, TC_Hh y TC_Ph se utilizaron para clasificar los datos en una matriz y ubicarlos en  la fecha correspondiente. Se agrego 3 filtros para estas columnas segun la categoria de calidad.

* Con *dfLluviaEstacion* se conecto la columna Fecha con todas las columnas Dia de las otras tablas. Se genero un filtro general por estacion astronomica y solo los dias de lluvia se sumaron mensualmente.  

* Con *Estacion_descripcion* se utilizaron las coordenadas para generar un mapa de ubicacion. Los nombres y el codigo se plasmaron en unas cartillas.

En la carpeta [data](https://github.com/JesusChachiRodriguez/Climatograma/tree/main/data) puede consultar el lenguaje DAX



