# Creación de Entidades Geográficas en QGIS

## Competencias

1. Diferenciar los diferentes usos de las entidades geográficas que se pueden crear en QGIS
2. Conocer las potencialidades de QGIS en ediciones básicas de entidades geográficas
3. Conocer la importancia de configurar correctamente las coordenadas de trabajo 

## Configuracion de coordenadas del proyecto

La primera etapa para el desarrollo de cualquier base de datos es definir el sistema de coordenadas con el que se trabajará. Esto se realiza con la finalidad de evitar problemas de compatibilidad con los sitemas de coordenadas de las capas que crearemos o sumaremos más adelante en los proyectos de Qgis. 

Antes de iniciar debemos hacer una diferencia entre los tipos de coordenadas que se pueden configurar en Qgis.

* Coordenadas del proyecto: Las coordenadas del proyecto correpondes a la configuración general de Qgis. Estas coordenadas modificaran la forma de presentación de los mapas base pero no de las capas vectoriales o raster que hayamos incluido. Para acceder a esta configuración de coordenadas se hace a través de las configuraciones generales de Qgis y son mas simples de modificar de uno a otro. 
* Coordendas de las capas: Cada capa tiene un propio sistema de coordenadas que puede ser igual o diferente al que se configura como coordenadas de proyectos. Estas coordenadas se establecen al momento de crear cada una de las capas. Para modificar este sistema de coordendas en la mayoria de casos es necesario generar nuevas capas.

En esta primera actividad estableceremos las coordenadas del proyecto al sistema de coordendas proyectadas WGS 84/UTM 19S que aplican para la zona de estudio. Sin embargo, no todos los proyectos se deben configurar a este mismo sistema ya que este depende de la zona en donde se desarrolla nuestro proyecto. Si tienen alguna duda sobre los diferentes sistemas de coordenadas lo invitamos a leer la parte teoria de las practica N°1 y N°2. 

IMPORTANTE. Reconocer la diferencia entre los sistemas de coordenadas proyectados y coordenadas geográficas. La coordendas geograficas en Qgis normalmente son **WGS 84 (EPGS: 4326)** y las coordendas proyectadas dependen de la zona de estudio y del sistema de proyección que hayan establecido. 

_________________________________________________________________________________________________________________________________________________________________________________

### Actividad N°1: Configuración de coordenadas del proyecto principal de Qgis

1. Ingresar al menu   <img src="https://github.com/user-attachments/assets/6eca5937-7bd8-4b91-9a9b-983b09e47663" alt="Ubicaciuon cato" width=70> >> <img src="https://github.com/user-attachments/assets/0a913eaa-ddb3-44a5-9151-9b0cd84786a3" alt="Ubicaciuon cato" width=100>
 y ubicamos la seccion SRC. El resultado debe ser el siguiente.

<p align="center">
  <img src="https://github.com/user-attachments/assets/ce80155b-4aae-4337-9509-286cf5a5277e" alt="Ubicaciuon cato" width=700>
</p>

<p align="center">Imagen 1: Interfaz de SRC de Qgis</p> 

2. sad
3. 

_________________________________________________________________________________________________________________________________________________________________________________

## Creación de elementos vectoriales

### Creación de Puntos
### Creación de lineas 
### Creación de Poligonos

### Edicion basica de elementos vectoriales

## Complementar seleccion por localización 


