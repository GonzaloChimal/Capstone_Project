# Google Analytics Capstone Project

Este repositorio contiene un análisis completado para el proyecto final del curso Certificado de análisis de datos de Google.

En este estudio de caso, utilicé los datos de una empresa ficticia de alquiler de bicicletas, Cyclistic, para tratar de determinar las principales diferencias entre los miembros anuales y los ciclistas ocasionales. Mostraré el proceso completo de limpieza, análisis y visualización de datos, junto con mis sugerencias finales y un resumen de los datos.

## Datos

Para analizar los datos históricos de viajes de Cyclystics, utilicé los datos de viajes de Cyclystic de los 12 meses anteriores extraídos de [divvy trip database](https://divvy-tripdata.s3.amazonaws.com/index.html). . Los conjuntos de datos contienen 13 columnas.

![download](https://user-images.githubusercontent.com/105673465/186822412-807f4511-3e11-40fd-aa87-8970215e2fc0.png)

## Proceso

Las herramientas que utilicé para analizar los datos fueron Excel, SQL y Tableau.

### Excel

Usé esto para la limpieza inicial y el procesamiento de los archivos .csv individuales. También agregué dos columnas más, ride_length y day_of_week, para recopilar más información sobre nuestro análisis. Al crear la columna ride_length, pude encontrar filas en las que la hora en que comenzó_en era posterior a la hora en que finalizó_en y pude eliminar esas filas.

### SQL

Dado que el conjunto de datos era demasiado grande para trabajar en Excel, importé los doce archivos CSV a SQL y los fusioné en un solo archivo llamado divvy_trip_data_merged. En total hay 5.723.387 filas. No se encontraron duplicados u otros errores en los datos. Debido a la gran cantidad de unidades opté por eliminar filas con valores nulos en start_station_name y end_station_name dejando un total de 4.641.279 filas.

>SELECT * 
FROM `divvy_trips.divvy_trip_data_2021_04`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2021_05`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2021_06`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2021_07`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2021_08`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2021_09`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2021_10`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2021_11`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2021_12`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2022_01`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2022_02`
UNION ALL
SELECT * 
FROM `divvy_trips.divvy_trip_data_2022_03`

### Tableau

Usé esto para crear visualizaciones sobre la información recopilada a través del análisis. Todo lo cual se puede ver [here](https://public.tableau.com/app/profile/gonzalo.chimal/viz/Caso1Google-Cyclistic/AverageRideLengthMonth)

## Análisis

* Encontré que de los 4.641.279 viajes los afiliados representaron 2.596.985 viajes (55,95%) y los eventuales 2.044.294 viajes (44,05%).
![download](https://user-images.githubusercontent.com/105673465/186812991-fc5c8fc9-ad9f-4e58-8a19-3c27600b3a1c.png)

* La duración media de un viaje para todos los cíclicos fue de 21,36 minutos, 32,05 para los casuales y 12,94 para los socios.
![download](https://user-images.githubusercontent.com/105673465/186813008-04f72dd0-b3c8-4432-9889-70aadcfa203c.png)

* De los tres tipos de bicicletas, la mayoría de los ciclistas casuales y los miembros usaban bicicletas clásicas.
![download](https://user-images.githubusercontent.com/105673465/186813027-b84d373e-d46b-4f55-822e-1024b63930de.png)

* Julio y Agosto son los meses con la mayor cantidad de viajes, siendo Julio el más alto para los casuales y Agosto el más alto para los miembros. Enero y Febrero son los meses con la menor cantidad de viajes para todos.
![download](https://user-images.githubusercontent.com/105673465/186813055-8d4505bb-1137-419c-be05-7dde5611a769.png)

* Los fines de semana son los horarios de viaje más populares para los pasajeros ocasionales, mientras que los días de semana son los más populares para los miembros.
![download](https://user-images.githubusercontent.com/105673465/186813067-70ddd363-a843-4af5-9b05-8f4bd9a7c3e9.png)

* Las estaciones más populares para los pasajeros ocasionales son 
![download](https://user-images.githubusercontent.com/105673465/186812667-df1ffd17-e27c-489c-a912-fff61c3a36bd.png)

* Las estaciones más populares para los miembros son
![download](https://user-images.githubusercontent.com/105673465/186812732-ee250cdb-d4df-4dc9-9ce8-b8f9802026c7.png)


## Conclusión

Con base en los hallazgos de este análisis, estas son mis principales recomendaciones.

* Al mirar los datos, los ciclistas ocasionales manejan más las bicicletas los fines de semana. Para atraer a los pasajeros ocasionales, sugeriría agregar promociones/descuentos dirigidos a tarifas más bajas para los viajes entre semana. Colocaría las promociones en las 10 principales estaciones de inicio y fin qué más frecuentan los ciclistas casuales para que así la empresa pueda llegar a la mayor proporción de estos ciclistas.

* Los ciclistas ocasionales dedican en promedio el doble de tiempo a andar en bicicleta que los miembros. Sugeriría poner carteles o mensajes en las estaciones para mostrar cuánto dinero se podría ahorrar a largo plazo al convertirse en miembro en lugar de pagar por viaje o duración.
