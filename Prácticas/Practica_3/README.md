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

2.  Para configurar las coordenadas debemos ubicar la barra de buscador y escribir el nombre del sistema que necesitemos. Para que esto funcione existen dos formas la primera es escribir el nombre de la coordenada respestando espacios, caracteres y puntuación de ser necesario. La segunda es colocar el numero identificador de la coordenada o el EPGS. Este número es unico para cada uno de los sistemas de coordendas es decir que no se puede repetir y funciona para identificar. Con forme nosotros vayamos ingresando elementos en la barra de buscador las opciones en el menu de coordenadas predeterminadas iran cambiando. Cuando se termine de digitar debera a aprecer alli nuestra coordenada si eso no ocurre deberemos revisar la forma en la que escribimos la coordenada. A continuacion se les presenta una tabla con coordendas más utilizadas para el Perú tanto en coordenadas geograficas como proyectadas.


| Coordenada | EPGS | Tipo | Descripción |
| :---: | :---: | :---: | :--- |
| WGS 84 | 4326 | Geográfica | Este sistema de coordenadas se aplica para el trabajar con coordenadas cuando un proyecto tiene coordendas en multiples segmentos UTM. El sistema que se configura por defecto para Qgis es Grados decimales. Por elemplo -71.25652 o -25.58623. Su aplicación es a nivel mundial por lo que cualquier parte del mundo puede ser representada con este sistema de coordenadas. |
| WGS 84 / UTM zone 17S | 32719 | Proyectadas | Son coordenadas proyectadas planares que utilizan como base las zona norte de Perú principalmente hasta aproximadamente la parte sur de Ancash y la perpendicular que se forma. Visualizar la imagen para comprender mejor su espacio de aplicación. |
| WGS 84 / UTM zone 18S | 32719 | Proyectadas | Coordenadas proyectadas que se utilizan para la zona central de Perú desde la parte sur de Ancash hasta la ciudad de Mollendo en Arequipa. Visualizar la imagen para comprender mejor su espacio de aplicación. |
| WGS 84 / UTM zone 19S | 32719 | Proyectadas | Coordenadas proyectadas que se utilizan principalmente para la zona Sur. Desde la ciudad de Mollendo en Arequipa hasta Tacna. Visualizar la imagen para comprender mejor su espacio de aplicación. |

<p align="center">
  <img src="https://github.com/user-attachments/assets/839a422a-3940-45cf-bd5e-6e104726ab82" alt="aplicacion de zonas UTM" width=400>
</p>
<p align="center">Imagen 2: Zonas de UTM que aplican a Perú </p> 

Para este ejercicio se seleccionará las coordendas WGS 84 / zone 19S

3. Una vez que hayamos terminado de digitar el sistema de coordenadas nos dirigiremos a la zona de coordendas predeterminadas y selecionaremos el sistema que corresponde como se muestra en la imagen anexa.

<p align="center">
  <img src="https://github.com/user-attachments/assets/31bb21e5-6a59-474c-8942-eec4fde14005" alt="aplicacion de zonas UTM" width=400>
</p>

5. Una vez selecionada la coordenada verificamos como en la zona de previsualización cambiará mostrando la zona de interés dentro de una zona roja. Verificamos que corresponda a la zona 19S y damos clic en aceptar con ello el Qgis esta configurado a este nuevo sistema de coordendas.
   
<p align="center">
  <img src="https://github.com/user-attachments/assets/4b49efec-ed79-43da-a9a2-4842448649e2" alt="aplicacion de zonas UTM" width=400>
</p>
_________________________________________________________________________________________________________________________________________________________________________________

## Creación de elementos vectoriales

### Creación de Puntos
### Creación de lineas 
### Creación de Poligonos

### Edicion basica de elementos vectoriales

## Complementar seleccion por localización 


