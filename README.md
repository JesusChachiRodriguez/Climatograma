# Análisis Meteorológico
## Tratamiento y transformacion de datos

**Lenguaje y/o Programas**
* Python con librerias numpy, pandas, datetime


**Entradas**
* *Temperatura, Humedad, Precipitacion, Direccion y Velocidad del viento* Datos meteorológicos de estaciones automáticas del [SENAMHI](https://www.senamhi.gob.pe/?p=estaciones), para este ejemplo se utilizó los datos de la Estación Santiago de Tuna en el 2021.
* *Rosa de Vientos* El rango angular de los [puntos cardinales](https://es.wikipedia.org/wiki/Rosa_de_los_vientos) en ocho rumbos colaterales.
* *Estaciones del año* La duracion de las estaciones astronomicas en el [Peru](https://www.gob.pe/11000-fechas-de-las-estaciones-astronomicas-en-el-peru).
* *Control de calidad de datos* Para fines de identificacion de datos dudosos se utilizo las pruebas que el [SENAMHI](https://www.senamhi.gob.pe/load/file/00711SENA-54.pdf) proporciona.

Todos los datos usados en el trabajo se pueden encontrar en la carpeta [data](https://github.com/JesusChachiRodriguez/Climatograma/tree/main/data).

**Procedimiento**

Ver el documento PROCEDIMIENTO en la carpeta [data](https://github.com/JesusChachiRodriguez/Climatograma/tree/main/data)

**Salidas**
* *dfTh* Temperatura horaria y calidad de datos
* *dfPh* Precipitacion horaria y calidad de datos
* *dfHh* Humedad horaria y calidad de datos
* *dfLluviaEstacion* Dias con lluvia y estacion astronomica
* *df2* Velocidad y direccion del viento horaria 
* *Estacion_descripcion* Ubicacion y descripcion de la estacion meteorologica 

## Visualizacion

**Lenguaje y/o Programas**
* Power BI con la extension de graficos Radar/ Polar Chart - Viz
* DAX

