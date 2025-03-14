# Práctica N°1: Introducción a SIG y uso de Google Earth Pro

### Competencias
1. Reconocer la plataforma Google Earth Pro
2. Comprender los conceptos básicos de entidades geográficas
3. Generar entidades geográficas en Google Earth Pro
   
### Para que sirve Google Earth Pro

Google Earth Pro es una herramienta de exploración geográfica que permite a los usuarios visualizar imágenes satelitales, mapas en 3D y datos geoespaciales de cualquier parte del mundo. Su propósito principal es facilitar el análisis territorial y la planificación, proporcionando una visión detallada de la superficie terrestre.

Entre sus funciones más destacadas se encuentran la medición de áreas y distancias con precisión, la posibilidad de superponer capas de información como datos demográficos y de tráfico, así como la opción de retroceder en el tiempo para observar cambios en el paisaje a lo largo de los años. Además, permite grabar recorridos virtuales, importar y exportar archivos GIS (Sistema de Información Geográfica) y generar imágenes de alta resolución para presentaciones y estudios técnicos.

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

## Creación de proyectos y carpetas
Antes de proceder a crear una entidad geográfica es necesario reconocer el lugar donde se almacenará lo desarrollado en nuestra sesión. Para ello debemos echar un ojo al menú lugares. Allí encontraran algunos elementos que viene precargados por defecto. 

<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/sinelementos.png" alt="Ubicaciuon cato">
</p>

Como se pude observar en la imagen se tienen dos tipos de archivos que se pueden distinguir por sus logos. El primero que tiene un logo de mundo ![Interfaz de Google Earth Pro](https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/kml.png) es el archivo del proyecto. Podemos tener múltiples proyectos activos en una sola sesión. Al activar o desactivar el proyecto, por defecto se aplica a todo lo que se tenga dentro del mismo. Para abrir o crear nuevos proyectos tenemos que ir a la barra herramientas Archivo >> Abrir o Archivo >> Guardar. Tambien funciona Archivo >> Importar. 
El formato que da origen a los proyecto se conocen como archivos KML o KMZ. Estos dos son los archivos más importantes para el Google Earth Pro.

El segundo logo que se puede ver se encuentra dentro del proyecto ***Mis lugares*** son carpetas de trabajo ![Interfaz de Google Earth Pro](https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/carpeta.png). Las carpetas son la forma de organizar información dentro de cada proyecto. Un mismo proyecto puede tener múltiples carpetas. Para crear nuevas carpetas se debe seleccionar el proyecto en el que se quiera crear la carpeta, luego dar clic derecho, buscar y seleccinoar la opción Añadir >> Carpeta. Tal como se muestra en la imagen. 
<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/crear_carpeta.png" alt="Ubicaciuon cato">
</p>

Por defecto el proyecto ***Mis Lugares*** tiene dos carpetas:
La primera es ***Recorrido visual***, en ella se encuentran recorridos precargados a lugares del mundo reconocidos. Para desplegar las carpetas hay que hacer clic en el triángulo que tienen al costado, al desplegar la carpeta de recorrido encontraremos una serie de nombres con hipervínculos, si hacemos clic en cualquiera el programa entra en modo recorrido automático que nos permite visualizar el lugar y visitarlo. Es una buena opción para visitar lugares sin necesidad de estar allí o para ver que nos encontraremos si en algún momento tenemos planes de viajar a esos lugares. 
La segunda carpeta es ***Lugares temporales***, esta carpeta guardará como su nombre lo dice elementos que cuando se cierre la sesión o cerremos el programa desaparecerán y no los podremos ver luego. Para seleccionar una carpeta basta con solo hacer clic sobre ella y que se marque en azul, eso indica al programa que guardaremos todo lo que creemos en ese lugar.
Las carpetas pueden dar origen a nuevos proyectos, pero eso lo veremos un poco más adelante, al momento de exportar los elementos que deseemos.

Para mantener el orden en el trabajo necesitaremos crear carpetas, es una buena costumbre tener una carpeta por cada proyecto que desarrollemos. Por lo que crearemos la carpeta con el nombre "Primera Clase" y allí procederemos a guardar todo lo que creemos.
____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

### Actividad 1:  Creación de carpeta "Primera Clase"
1. Deberemos seleccionar el proyecto sobre el que se desee trabajar, para este caso es el Proyecto Mis Lugares, hacemos clic derecho y ubicamos la opción Añadir >> Carpeta
  <p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/crear_carpeta.png" alt="Ubicaciuon cato">
</p>
2. Se deberá desplegar un nuevo recuadro, en este podremos configurar el nombre de la carpeta de trabajo. Para este ejercicio debera ser "Primera Clase" 
<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/nueva_carpeta_menu.png" alt="Ubicaciuon cato">
</p>

3. Si todo salió bien deberá de aparecerles la nueva carpeta "Primera clase" en el menú lugares
<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/carpeta_nueva.png" alt="Ubicaciuon cato">
</p>

Si les surgió algún problema es mejor que eliminen lo que se haya creado, para ello seleccionan la carpeta con un clic, luego clic derecho y ubican la opción eliminar. 
<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/eliminar_carpeta.png" alt="Ubicaciuon cato">
</p>

____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

## Creación de entidades geográficas

### ¿Que es una entidad geográfica?

Una entidad geográfica es un elemento sobre la tierra que puede ser representado, analizado y gestionado dentro de un sistema geoespacial.

Las entidades geográficas pueden clasificarse en:

1. Puntuales: representan ubicaciones específicas, como una torre de transmisión o una estación meteorológica.
2. Lineales: representan elementos con longitud, como carreteras, ríos o fronteras.
3. Área o poligonales: representan superficies con área definida, como lagos, bosques o municipios.

### ¿Cómo se crean?

Retomenos donde nos quedamos en la Actividad N°1. Una vez creada la carpeta debemos seleccionarla, para ello basta con hacer un solo clic sobre el nombre de la carpeta y verán que se sombrea de un color azul ![seleccionada](https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/carpeta_seleccionada.png). Este proceso es importante porque al seleccionar la carpeta le decimos al programa que allí es donde queremos que se guarden nuestras entidades geográficas.

Con la capeta seleccionada nos dirigiremos al menú Utilidades, esta barra tiene todas las herramientas que nos permitirán editar, crear y modificar las entidades geográficas.
<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/menu_utilidades.png" alt="Ubicaciuon cato">
</p>

### Creación de puntos
![Interfaz de Google Earth Pro](https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/puntos.png) Esta opción permite crear puntos.

Para crear un punto basta con hacer clic en el ícono, se desplegará un menú con un recuadro al costado y veremos un cuadrado amarillo con una tachuela de color amarillo en el centro. Debemos desplazar la tachuela hacia la zona de interés y hacer clic en aceptar.

### Creación de polígonos
![Interfaz de Google Earth Pro](https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/poligonos.png) Esta opción permite crear polígonos. 

El procedimiento para crear un polígono es igual al de la creación de puntos. Hacemos clic en el ícono, se desplega el recuadro y el cursor cambia de forma. Los polígonos permiten ver áreas, por lo que cada que hagamos un clic se generará un vértice. Podemos colocar la cantidad de vértices que nosotros queramos. El área que quede dentro de los vértices quedará sombreada y se generará el polígono. Para finalizar, hacer clic en aceptar.
Si la entidad geográfica fue correctamente creada la encontrarán en el Menú lugares.

### Creación de líneas
![Interfaz de Google Earth Pro](https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/lineas.png) Esta opción permite crear líneas.

Se repite el proceso de creación anteriormente descrito. Las líneas son entidades unidimensionales, es decir como si fuera un trazo de lápiz en un papel. El cursor nos permitirá colocar vértices y cada vértice se unirá por un trazo de color negro por defecto.

____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

### Actividad 2: Creación de entidades geoográficas
1. Utilizar la barra de búsqueda para encontrar los siguientes lugares:
   
    * Ciudad de Arequipa.
    * Laguna de Salinas, Arequipa.
    * Puente de Fierro, Arequipa.
   
    La barra de búsqueda funciona para encontrar lugares dentro de Google Earth Pro que tengan algún nombre definido. Se encuentra sobre el Menú Lugares.
         <p align="center">
       <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/menubuqueda.png" alt="Ubicaciuon cato">
         </p>

    Para ejecutar una búsqueda se necesita colocar el nombre en el recuadro blanco y darle a buscar. Saldrán las opciones de búsqueda debajo como se muestran en la imagen.
         <p align="center">
           <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/busquedaejecutada.png" alt="Ubicaciuon cato">
         </p>

2. Crear un punto sobre la ciudad de Arequipa y analizar el resultado
     * Modificar el nombre del punto a Arequipa
     * Debajo del nombre encontrarán la zona de coordenadas, allí pueden ubicar el par de datos que correponden a los datos del punto. Si se mueve el punto las coordenadas cambian automáticamente.
     * Al final de todo el recuadro encontrarán un recuadro con pestañas, esta es la zona de edición, abordaremos las configuraciones que se pueden hacer.
<p align="center">
       <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/zonas_edicion_puntos.png" alt="Ubicaciuon cato">
         </p>
         
3. Generar un polígono sobre la ubicación de la Laguna de Salinas
    * Al momento de hacer clic sobre el logo de crear polígono ![Interfaz de Google Earth Pro](https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/poligonos.png). El cursor cambiará, pero no habrá ningún punto de referencia como si paso con los puntos.
    *  Para generar el polígono deberá hacer clic en cada uno de los márgenes, cada clic generará un vértice del polígono como se muestra en la imagen.
<p align="center">
       <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/Captura%20de%20pantalla%202025-03-12%20151357.png" alt="Ubicaciuon cato">
         </p>
    
   * Notar que el recuadro de coordenadas no existe en polígonos, pero si nombre y la ventana de edición.
   * Si se equivocan, pueden borrar el vértice haciendo clic sobre el que salió mal y darle clic en suprimir desde su teclado.
   * Pueden reposicionar vértices manteniendo clic sobre el vértice que quieran desplazar y moviendolo hacia su nueva posición.

4. Generar una línea a través de todo el Puente de Fierro
   * Ubicar la zona de Punte de Fierro y hacer clic en el ícono de edición de líneas ![Interfaz de Google Earth Pro](https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/lineas.png).
   * Al igual que con polígonos, el cursor desaparecerá y cada vez que se haga clic saldrá un vértice, las líneas generan trazos que unen los puntos.
     
   ![Interfaz de Google Earth Pro](https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/linea.png)

____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

## Edición de entidades geográficas

Las ediciones de cada entidad geográfica son bastante parecidas entre sí. Se presentan ligeras diferencias pero mantienen una misma lógica. 

Cada vez que creamos una entidad geográfica se desplega un recuadro al costado. En dicho recuadro, podremos encontrar las opciones de edición. Si la entidad ya se creo y se dio en aceptar el recuadro desaparece, para volver a aperturarlo basta con hacer clic derecho en el nombre del elemento y hacer clic en propiedades.

<p align="center">
       <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/edita.png" alt="Ubicaciuon cato">
         </p>

Dentro de todos los menús de ediciones de datos siempre se presentan las ventanas de Descripción, Estilo/color y Ver. 

* Ventana Descripción: En la ventana descripción podemos colocar información correspondiente a la entidad que estemos creando. Por ejemplo si tiene algun dueño, alguna referencia, etc. La descripcion no se moestrara en pantalla pero al consultar las propiedades podremos volver a verlas y editarlas 
* Ventana Estilo/color: La ventana estilo y color nos permite cambiar los colores de la entidad geográfica creada asi como de la etiqueta (nombre) que le colocamos. 
* Ventana ver: 


Las opciones que acompañan a estas ventanas cambien de acuerdo con la entidad geográfica que se este analizando por dicho motivo se abordará la edicion de cada una de ellas por separado. 



### Ediciones de puntos

<p align="center">
       <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/edicion_puntos.png" alt="Ubicaciuon cato">
         </p>

La edición de puntos consta de dos partes la edicion del icono y los menús de edición 

1. Edición de ícono. Si hacemos clic en la tachuelade color amarillo se nos desplegara una nueva ventana con multiples gráficos. Al seleccionar en algun grafico podremos cambiar el diseño del punto a cualquiera de los predefinidos o podemos ingresar nuestro propio icono haciendo clic en ![argregar icono](https://github.com/RealGuyab/Qgis/blob/main/imagenes/a%C3%B1adir_icono.png). Se aperturará una nueva ventan donde tendremos que dar clic en examinar y buscar nuestro ícono. Se recomienda no usar iconos muy complicados, muy grandes o llamativos.
2. El Menu de edicion se pueden encontrar las ventanas Descipcion, Estilo-Color, Ver y Altitud.
     * La ventana Estilo-color nos permite modificar el Color de la etiqueta o el nombre asi como su tamaño haciendo crecer el numero que se encuentra en la opcion escala. La opacidad nos dara el valor de la transparencia. Es decir, hara que la etiquea sea cada vez mas translucida el valor de 100% indica un color completamente solido mientras que 0% la hara complemetamente transparente puede mover el valor entre estos rango y analizar como cambia el resultado. Ocurre lo mismo en ícono con la única diferencia de que aqui cambia el color del logo que hayamoos configurado. 
     * La ventana Ver, configura la vista por defecto del punto. Si nosotros hacemos sobre el nombre de mi punto clic en el menú lugares en automatico la camara se reposicionara y podremos visualizar nuestro punto. Si repoosicionamos el punto se necesita darle a restablcer para que pueda reposicionarse a la nueva ubicacion que le dieron.
       
<p align="center">
       <img src="https://github.com/RealGuyab/Qgis/blob/main/imagenes/ver.png" alt="Ubicaciuon cato">
         </p>

   * Altitud en esta configuración no nos da ningún valor.
     
### Ediciones de poligonos

La edidion de poligonos es similar a la de puntos sin embargo aqui aparecen dos diferencias. La primera se encuentra en la ventana de Estilo/color y la segunda en la ventana de medidas.

1. Ventana estilo/color: las opciones son las mismas sin embargo ahora aparece area en lugar de ícono. encontraran que existe un pequeño recuadro desplegable con tres opcines, Relleno, Contorno y Relleno y contorno. Estas opciones permitiran darle detalle colores a las lineas de contorno como al area o solo dejar activa una a la vez les remendamos que lo prueban activando cada una a la vez y viendo como cambia el resultad.

<p align="center">
       <img src="https://github.com/RealGuyab/Qgis/blob/main/imagenes/dise%C3%B1o_area.png" alt="Ubicaciuon cato">
         </p>
 
2. Medias: aqui podran encontrar datos del area y perimetro que comprende el poligono que crearon. La opción desplegable permite cambiar las unidades al resultado.

<p align="center">
       <img src="https://github.com/RealGuyab/Qgis/blob/main/imagenes/medidas.png" alt="Ubicaciuon cato">
         </p>

### Ediciones de Lineas

Al igual que las entidad anterior existen ligeros cambios en la ventana Estilo/color y medidas 

1. Ventana estilo/color: aqui habra un ligero cambio en el nombre llamandose lineas. Sin embargo, las opciones de configuración se mantienen igual.

<p align="center">
       <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/linea_edicion.png" alt="Ubicaciuon cato">
         </p>
   
2. En medidas ahora solo aparece la longitud, que indica la longitud de la linea trazada en el mapa. recordar que el desplegable permite cambiar unidades al resultado.

<p align="center">
       <img src="https://raw.githubusercontent.com/RealGuyab/Qgis/main/Pr%C3%A1cticas/Practica_1/imagenes/medidas_linea.png" alt="Ubicaciuon cato">
         </p>   

IMPORTANTE: como se explico en es preferible evitar colores muy llamativos como por ejemplo colores fosforescentes o rojos.

____________________________________________________________________________________________________________________________________________________________________________________________________________________
### Actividad N°3 Edicion de entidades geográficas


____________________________________________________________________________________________________________________________________________________________________________________________________________________
## Cambio de coordenadas en Google Earth Pro

Cuando creamos un punto y entramos a sus propiedades vemos sus coordenadas. Las coordendas solo se muestran para objetos puntuales en una zona (puntos) es por ello que no encontramos coordenadas ni en lineas, ni en poligonos pero ello no significa que no las tengan. Existen multiples formatos de coordenadas pero las agruparemos en dos grupos para un mejor entendimiento.

### Coordenadas Geográficas 

Las coordenadas geográficas asumen un modelo esferico de la tierra y su unidad principal son los grados minutos y segundos. Para que estas coordenadas funcionen se tienen que tener lineas de referencia. Estas se encuentran distribudas a travez del mundo sobre dos 2 ejes que llamaremos longitud y latitud. 

   + Longitud o tambien conocido como eje X. La longitud se mide con lineas verticales paralelas entre sí. Para fines graficos estas lineas se distribuyen cada determinado número de ángulos. Estas lineas toman el nombre de meridianos y el meridiano de referencia es el Meridiano de Greenwitch o primer meridiano que se encuentra en Inglaterra. Si tuvieras que definirlo de una manera simple la linea de corte principal el Meridiano de Greenwitch divide el mundo en derecha e izquierda o mejor dicho "hemisferio Este" para el caso de lo que se encuentra a la derecha del meridiano de referencia y "hemisferio oeste" para lo que esta a la izquierda,

<p align="center">
       <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/este_oeste2.png" alt="Ubicaciuon cato" width="480">
         </p>

   + Latitud o tambien conocido como eje Y. La latitud se mide con líneas verticales entre sí. Al igual que en el anterior caso se distribuyen bajo determinado número de grados. La línea de referencia es la línea ecuatorial o ecuador geográfico. Esta línea divide el mundo en dos partes o Hemisferios El hemiferio Norte (N) y el hemisferio Sur (S).

<p align="center">
       <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_1/imagenes/norte_sur.png" alt="Ubicaciuon cato" width="480">
         </p>

### Coordenadas Proyectadas



Como les habia explicado anteiormente existen multiples tipos de formatos de coordenadas. Google Earth Pro nos permite cambiar estos sistemas. Esta opción es necesaria ya que algunas veces nos enfrentaremos a diversos formatos de coordenadas y se nos pedirá que las ubiquemos en el mapa. Por lo que tenemos que saber que hacer ante esta situacion. Los formatos de coordendas más comunes y que se encuentran en el programa son los siguientes:

| Sistema de Coordenadas  | Second Header | asdasd |
| :---: | :---: |  :---: |
| Content Cell  | Content Cell  | cell |
| Content Cell  | Content Cell  | cell |

+ Grados, minutos y segundos
+ Grados decimales
+ Grads, minutos decimales
+ Universal Trasversal Mercator (UTM)
+ Sistema de referencia de cuadricula militar

Para configurar el tipo de coordenadas 

____________________________________________________________________________________________________________________________________________________________________________________________________________________
### Actividad N°4 Cambio de coordenadas

____________________________________________________________________________________________________________________________________________________________________________________________________________________
## Asignación 
