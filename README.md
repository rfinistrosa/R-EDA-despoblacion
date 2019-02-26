# R-EDA-despoblación
Análisis exploratorio de datos en R sobre la despoblación en los municipios de España

Hemos creado un dataset a partir de datos públicos extraídos de distintas fuentes institucionales.

Utilizando R y sus librerías de representación geoespacial, demostramos cómo realizar un análisis exploratorio de datos (EDA)


## FUENTES
Datos | Fuente
------------ | -------------
Municipios | CENTRO DE DESCARGAS DEL CENTRO NACIONAL DE INFORMACIÓN GEOGRÁFICA
Padrón | INE
Paro por municipio en España | SEPE
Municipios IGN (Shapefiles)  | PORTAL DE DATOS ABIERTOS DE ESRI ESPAÑA - ARCGis
Provincias - ETRS89 UTM 30N  | PORTAL DE DATOS ABIERTOS DE ESRI ESPAÑA - ARCGis
Datos climáticos (temperatura media) | AEMET


## DATASET
Una vez realizado el proceso ETL sobre las fuentes, obtenemos el fichero municipios.csv con los siguientes datos:


ID | CAMPO | TIPO | DESCRIPCION
------------ | ------------- | ------------ | -------------
1 | COD_INE | CHAR(11) | Código dado por el Instituto Nacional de Estadística a cada una de las entidades poblacionales. Se caracteriza por ser un código único e intransferible formado por 11 dígitos de los cuales los dos primeros hacen referencia a la provincia a la que pertenece la unidad poblacional. Los tres siguientes identifican el número del municipio dentro de la provincia. Los dos siguientes indican si es o no entidad colectiva. Los dos siguientes indican si la población es un núcleo poblacional o es indican si es entidad singular. Y los dos finales población diseminada por el término municipal.
2 | COD_GEO | CHAR(5) | Código Geográfico
3 | COD_PROV | CHAR(2) | Código de la Provincia.
4 | PROVINCIA | CHAR(100) | Nombre de la provincia en la que se encuentra el Municipio.
5 | NOMBRE_ACTUAL | CHAR(100) | Nombre actual del municipio tal y como aparece inscrito en el REL.
6 | SUPERFICIE | NUMERO | Superficie oficial del término municipal (Ha).
7 | PERIMETRO | NUMERO | Perímetro del término municipal.
8 | LONGITUD_ETRS89 | FLOAT | Longitud de la Coordenada geográfica en el sistema ETRS89 para la Península e Islas Baleares, REGCAN95 para las Islas Canarias.
9 | LATITUD_ETRS89 | FLOAT | Latitud de la Coordenada geográfica en el sistema ETRS89 para la Península e Islas Baleares, REGCAN95 para las Islas Canarias.
10 | ALTITUD | NUMERO | Altitud correspondiente al centroide.
11 | HABITANTES | DOUBLE | Número total de habitantes
12 | HOMBRES | DOUBLE | Número de habitantes hombres
13 | MUJERES | DOUBLE | Número de habitantes mujeres
14 | TOTAL_PARO | NUMERO | Número total de parados
15 | PARO_H25 | NUMERO | Parados hombres < de 25 años
16 | PARO_H25_44 | NUMERO | Parados hombres de entre 25 y 44 años |
17 | PARO_H45 | NUMERO | Parados hombres >= de 45 años
18 | PARO_M25 | NUMERO | Paradas mujeres < de 25 años
19 | PARO_M25_44 | NUMERO | Paradas mujeres de entre 25 y 44 años
20 | PARO_M45 | NUMERO | Paradas mujeres >= de 45 años
21 | PARO_AGRICULTURA | NUMERO | Número de parados en agricultura
22 | PARO_INDUSTRIA | NUMERO | Número de parados en industria
23 | PARO_CONSTRUCCION | NUMERO | Número de parados en construcción
24 | SERVICIOS | NUMERO | Número de parados en servicios
25 | SINEMPLEOANTERIOR | NUMERO | Número de parados sin empleo anterior
26 | AÑO | NUMERO | Año de los datos (2017)
27 | EDAD_MEDIA | DOUBLE | Edad media del municipio
28 | de0-18 | INTEGER | Número de habitantes menores de 18 años
29 | de19-67 | INTEGER | Número de habitantes entre 19 y 67 años
30 | masde68 | INTEGER | Número de habitantes mayores de 18 años
31 | de0-12 | INTEGER | Número de habitantes entre 0 y 12 años


## EDA
Utilizando R y sus librerías de representación geoespacial, demostramos cómo realizar un análisis exploratorio de datos (EDA)


Las librerías R que se utilizan en éste ejercicio son:


* rgdal - Librería para uso de datos geoespaciales
* tmap - Librería para presentación de mapas
* ggplot2 - Librería para análisis exploratorio de datos
