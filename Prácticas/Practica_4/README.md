# Práctica N°4: Georreferenciación

## Competencias 
* Reconocer la importancia de los sistemas de coordenadas
* Asignar coordenadas a mapas antiguos o elementos que no presentan sistema de coordenadas
* Analizar el terreno en busca de elementos sin variación temporal

## Importancia de los Sistemas de Coordenadas

Como vimos previamente los Sistemas de Coordenadas nos indican la posicion de algún lugar en la tierra. Para poder cartografiar algo tenemos que ser concientes de las coordenadas con las que estamos trabajando. En caso tengamos coordenadas diferentes se tendran problemas para trabajar y esto nos obligara a transformar y homogenizar todo. 
Desde este momento hay que tener cuidado con la asignacion de coordenadas tanto del proyecto de Qgis como de cada una de las capas que subamos. En la actividad 1 estableceremos los criterios para ejecutar la georreferenciacion de un plano construido en 1905. 

### Actividad 1: Configuracion de coordenadas de trabajo



## Datos Raster 


### Actividad 2: Digitalización de mapas antiguos

Los mapas a escala antiguos son una fuente de información importante principalmente para analizar cambios en elementos que con el tiempo se han ido ampliando o desapareciendo. En el ejemplo que abordaremos el dia de hoy analizaremos su uso en el análisis de la evoluación urbana de la ciudad de Arequipa. 
Primero lo que se debe lograr es la digitalizacion de los elementos mas antiguos de la ciudad esta digitalización puede consistir en un escaneo o una foto. Lo mas importante es que este procedimiento no haga ninguna modificación en el aspecto del mapa o plano (no modifique la altura, ni el ancho). En caso esta modificacion se de los resultados saldrán dudosos. 

Para este ejercicio utilizaremos un mapa de Arequipa del año 1905 entraido de [descarga de mapa](https://www.facebook.com/photo/?fbid=1542811802691634&set=a.1542810076025140). 

<p align="center">
<img  src = "https://github.com/RealGuyab/GIS2025/blob/main/Pr%C3%A1cticas/Practica_4/descargables/mapa_arequipa_1905.jpg" alt="conforme" width=500>

### Descarga de datos

1. Ingresar a la carpeta de los adjunto del presente repositorio con el nombre de descagable y descargar la imagen [mapa_arequipa_1905](https://github.com/RealGuyab/GIS2025/blob/main/Pr%C3%A1cticas/Practica_4/descargables/mapa_arequipa_1905.jpg) descargar la imagen.
2. Aperturar Qgis y subir la imagen para ello deberemos conectar la carpeta como vimos en la [práctica N°1](https://github.com/RealGuyab/GIS2025/tree/main/Pr%C3%A1cticas/Practica_1)
3. Aperturaremos el QGIS y nos dirigiremos al administrador de fuentes de datos ![image](https://github.com/user-attachments/assets/bf3b5db7-3755-4d14-adb1-aeb5b393eaa8). Al hacer click se aperturará un nuevo menú en el que deberemos seleccionar la opcion raster. ![image](https://github.com/user-attachments/assets/20e6fcd4-bf03-45e9-a51e-186b134fe730).
4. Nos dirigiremos al menú *Fuente* de la nueva ventana. Haremos clic en los tres puntos de busqueda y ubicaremos nuestra imagen.

El resultado deberá mostrarse igual a lo siguiente 

<p align="center">
<img  src = https://github.com/user-attachments/assets/0e798a05-e526-48d2-99be-56d12bceb416 alt="resultado_raster" width=500> 

### Reconocimiento de datos en la imagen

Lo primero que salta a la vista es que la imagen que subimos a Qgis se representa sin ningún tipo de deformación y aparentemente esta ubicada. Sin embargo, podemos darnos cuenta que esta carece de coordenadas y lo podemos demostrar de forma práctica colocando un mapa base. 

<p align="center">
<img  src = https://github.com/user-attachments/assets/18b0d0e6-7457-4274-ae74-e327d3cbedd2 width=500>

Como se muestra en la imagen pueden observar que no existe una ubicación concreta e incluso la imagen ingresada es más grande que un mapa base. Esto se produce por un error en la proyección en resumen no tienen ningún sistema de coordenadas asignado lo que hace que sea imposible de ubicarse ni tener un espacio en los mapas.  
Otro elemento que nos indica que no existe una coordenada es el logo que sale al costado del nombre de la capa. 

<p align="center">
<img  src =https://github.com/user-attachments/assets/3f3e34e2-b61a-438a-9c8b-06752c9a8cf0>

La presencia de este logo ![image](https://github.com/user-attachments/assets/9ded266d-5cf6-4364-8c39-0930b5483f31) nos indica que la capa no presenta ningun sistema de coordenadas. 


## ¿Que es Georreferenciar?












