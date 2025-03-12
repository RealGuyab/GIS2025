# Práctica N°1: Introducción a SIG y uso de Google Earth Pro

### Competencias
1. Reconocer la plataforma Google Earth Pro
2. Comprender los conceptos básicos de entidades geográficas
3. Generar entidades geográficas en Google Earth Pro
   
### Para que sirve Google Earth Pro

Google Earth Pro es una herramienta de exploración geográfica que permite a los usuarios visualizar imágenes satelitales, mapas en 3D y datos geoespaciales de cualquier parte del mundo. Su propósito principal es facilitar el análisis territorial y la planificación, proporcionando una visión detallada de la superficie terrestre.

Entre sus funciones más destacadas se encuentran la medición de áreas y distancias con precisión, la posibilidad de superponer capas de información como datos demográficos y de tráfico, así como la opción de retroceder en el tiempo para observar cambios en el paisaje a lo largo de los años. Además, permite grabar recorridos virtuales, importar y exportar archivos GIS (Sistema de Información Geográfica) y generar imágenes de alta resolución para presentaciones y estudios técnicos.

### Entidad geográfica

Una entidad geográfica son elementos sobre la tierra que puede ser representado, analizado y gestionado dentro de un sistema geoespacial.

Las entidades geográficas pueden clasificarse en:

1. Puntuales: Representan ubicaciones específicas, como una torre de transmisión o una estación meteorológica.
2. Lineales: Representan elementos con longitud, como carreteras, ríos o fronteras.
3. Areal o poligonales: Representan superficies con área definida, como lagos, bosques o municipios.

## Instalación de Google Earth Pro
 + Ingresar en el siguiente link https://maps.google.com/intl/es/earth/download/gep/agree.html
 + Aceptar los términos y condiciones e iniciar la descarga
 + Ejecutar lo descargado y esperar a que finalice la instalación
 + Una vez finalizado tendrán acceso al programa

## Análisis de interfaz

Google Earth Pro cuenta con una interfaz con segmentos diferenciados. Para nuestro curso dividiremos la interfaz en 6 secciones las que se detallan:

1. Barra de Herramientas y configuración: se encuentra en la parte superior de la interfaz. Incluye los menús de configuración general del programa, guardar proyectos y exportar asi como otros más.
2. Menú lugares: Aquá encontrarán todas los elementos que ustedes creen durante su sesión. Podran activarlos, desactivarlos, exportalos y eliminarlos. Siempre que un elemento se muestre más arriba se mostrará primero.
3. Menú capas: en el menú capas encontran algunos ejes temáticos ya precargados por Google estos elementos no necesitan de ser descargados previamente. Cada vez que uno active una capa podrá obtener más información del terreno bajo estudio.
4. Menú Utilidades: Aqui se encuentran las herramientas que permiten crear entidades geográficas, asi como la opción retroceder en el tiempo, medición, exportación y cambio de planeta.
5. Visor principal: se encuentra el mapa principal donde saldrán gráficamente las entidades geográficas y ciudades. 
6. Herramientas de navegación: permite mover el ángulo de vista, el zoom y cuando este activo Google Street View 

![Interfaz de Google Earth Pro](https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/gep_interfaz.png)
<p align="center">Imagen 1: Interfaz y ubicación de secciones</p> 

## Creación de entidades Geográficas
Antes de proceder a crear una entidad geográfica es necesario reconocer el lugar donde se almacenara lo desarrolla en nuestra sesión. Para ello debemos hechar un ojo al menú lugares. Alli encontraran algunas carpetas que viene precargadas por defecto. 

<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/sinelementos.png" alt="Ubicaciuon cato">
</p>

La primera es <ins>Recorrido visual<ins>, en ella se encuentran recorridos precargados a lugares del mundo reconocidos. Para desplegar las carpetas hay que hacer clic en el triangulo que tienen al costado. a desplegar la carpeta de recorrido encontraremos una serie de nombres con hipervinculos si hacemos clic en cualquiera el programa entra en modo recorrido automatico que nos permite visualizar el lugar y visitarlo. Es una buena opción para visitar lugares sin necesidad de estar alli o para ver que nos encontraremos si en algún momento tenemoos planes de viajar a esos lugares. 
La segunda carpeta son de <ins>Lugares temporales<ins>, esta carpeta guardará como su nombre lo dice elementos que cuando se cierre la sesion o cerremos el programa desapareceran y no los podemos ver luego. Para seleccioonar una carpeta basta con solo hacer click sobre ella y que se marque en azul eso indica al programa que guardaremos todo lo que creemos en ese lugar.

Para crear entidades geográficas utilizaremos el menú de utilidades 

<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/menu_utilidades.png" alt="Ubicaciuon cato">
</p>

### Creación de puntos
![Interfaz de Google Earth Pro](https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/puntos.png) Esta opción permite crear puntos

Para crear un punto basta con hacer clic en el ícono, se desplegará un menú con un recuadro al costado y veremos un cuadrado amarillo con un clip de color amarillo en el centro. Debemos desplazar el clip hacia la zona de interés y hacer clic en aceptar.

### Creación de poligonos
![Interfaz de Google Earth Pro](https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/poligonos.png) Esta opción permite crear polígonos 

El procedimiento para crear un poligono es igual al de la creación de puntos. Hacemos clic en el ícono se desplega el recuadro y el cursor cambia de forma. Los polígonos permiten ver áreas por lo que esta vez cada que hagamos un clic se generá un vértice podemos colocar la cantidad de vértices que nosotros queramos. El área que quede dentro de los veértices quedara sombreada y se generará el poligono. Para finalizar nuevamente en aceptar.
Si la entidad geografica fue correctamente creada la encontraran en el Menú lugares

### Creación de líneas
![Interfaz de Google Earth Pro](https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/lineas.png) Esta opción permite crear líneas

Se repite el proceso de creacion anteriormente descrito. Las líneas son entidades unidimensionales, es decir como si fuera un trazo de lápiz en un papel. El cursor nos permitirá colocar vértices y cada vértice se unirá por un trazo de color negro por defecto.

### Edición de entidades geográficas

Las ediciones de cada entidad geográfica son bastante parecidas entre sí. Se presentan ligeras diferencias pero manteienen una misma lógica. 

1. Ingreso al menú de ediciones. Cada vez que creamos una entidad geográfica se desplega un recuadro al costado. En dicho recuadro podremos encontrar las opciones de edición. Si la entidad ya se creo y se dio en aceptar el recuadro desaparece, para volver a aperturarlo basta 


## Ejercicio Practico N°1: Creacion de entidades geográficas

## Ejercicio Practico N°2: Edición de entidades geográficas

## Asignación 
