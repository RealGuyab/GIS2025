# Práctica N°2: Introducción a Qgis y desarrollo de mapas

## Competencias

1. Conocer la plataforma Qgis
2. Identificar las diferencias entre coordendas geograficas y proyectadas
3. Reconocer los elementos minimos que deben estar presentes en un mapa
4. Reconocer la plataforma de generacion de mapas de Qgis

## ¿Qué es una coordenada?

Las coordenadas como lo vimos anteriormente son números que nos indican la posición de un elemento en el espacio. Haciendo recuerdo hablamos de dos sistemas de coordenadas. 

+ Las coordenadas Geográficas
+ Las coordenadas Proyectadas

La sesión anterior definímos lo que es una coodenada geográfica y como es que se interpreta en base a los múltiples formatos que presenta Google Earth Pro. En esta sesión nos enfocaremos en la definición de las coordenadas Proyectadas principalmente pero abordaremos conceptos que tambien se aplican a las coordenadas geográficas. A continuacion analizaremos algunos conceptos previos que permitiran dar más detalle y un contexto a lo que es una coordenada. 

## ¿Cuál es la verdadera forma de la tierra?

Todos alguna vez en nuestra vida nos hemos hecho esa pregunta. Es bien conocido que la forma de la Tierra es esferica y ello se determino hace mucho tiempo atras esto fue propuesto en la antigua Grecia y fue Eratóstenes un matemático quien con un simple experimentos (utilizando palos y sombras) pudo medir la circunferencia con una precisión muy buena eso aproximadamente en el año 240 A.C. Pero cuando hablamos de una esfera el contexto pude ser un poco ambiguo. 
Existen multiples tipos de esfera, esferas perfectas, esferoides, elipsoides, etc.

<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_2/imagenes/esferas.png" alt="TIPOS ESFERAS" width=550>

## Generalización de la forma de la tierra

La superoficie de la tierra es algo muy irregular. Se tienen montañas, valles, cañones, rios, etc. Todos estos elementos son muy dificil de moodelar tomando en cuenta que en la mayoria de mapas o modelos de la tierra o se dispone unicamente de una superficie plana como una hoja o una pantalla. Es por ello que se desarrollan modelos con un mayor grado de simplificación. A esto se le llamaremops generalizacion de los moodelos de la tierra.

<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_2/imagenes/nivel_generalizacion.png" alt="TIPOS ESFERAS" width=300>

Como pueden observar en la imagen con forme vamos bajando en la misma encontramos diversos modelos. Estos modelos van perdiendo detalle si tomamos en cuneta la superficie inicial de la tierra. Sin embargo nos permiten desarrollar cálculos matemáticos mas precisos y de ellos generar herramientas como las coordenas o sistemas de posicionamiento. 

Los modelos de analizaremos en este apartado seran principalmente dos:
+ Elipsoides
+ Geoide
  
Esto nos permitira entender algunos elementos adicionales como los datum o las proyecciones. Todo esto se estudia en la Geodecia, que es la ciencia que permite ubicar cosas en la Tierra con mucha precisión. La información que se coloca en la página servirá como un inicio si alguno estuviera interesado en tomar mayor detalle espero que esto le sirva como punto de partida.  

## ¿Qué es un elipsoide?

Todos hemos visto el modelo más comun de la tierra, en donde se muestra una esfera completamente perfecta, esta fortma de representar la tierra es una representación artistica que no coincide con la fomra real de la tierra. Si tuviarmos que ser mas precisos sobre su forma real sin incluir todavia valles, montañas, etc. estariamos hablando de una esfea que se encuentra achatada en los polos (esfera oblata), si aún reducimos mas la complegidad o nos fijamos solo en los bordes la figura resultante es una elipse. 

<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_2/imagenes/ESFERA_OBLATA.png" alt="ELIPSOIDE" width=600>

El elipsoide surge entonces de esta idea de representar la tierra de forma más precisa. Sintetizando la idea un elipsoide es una superficie homogénea (sin perturbaciones) que englpba toda la tierra y la aproxima hacia una esfera. Se le conoce como la forma matematica de la Tierra por que mediante la aplicacion del calculo se puede llegar a la misma forma que hemos interpretado de forma visual. Este elipse da origen principalemente a las coordenadas Geografícas que como vimos la clase anterior asumen la tierra como una esfera o en este caso una semiesfera. 
Lamentablemente el elipse no es preciso en todos los lugares de la tierra. Como hemos hecho un resumen y la tierra tiene ciertas deformidades superficiales la linea que se establace como limite del elipsoide puede quedar por debajo o sobre el terreno a esteo se le conoce como ondulacion geoidal. Esto se corrige luego con algunos elementos adicionales que veremos más adelante. Existen multiples eliposoides desarrollaros hasta el momento algunos más precisos en algunas zonas. 
Se tienen dos tipos de elipsoides: 
* Elipsoides globales. Tienen la principal función de resumir la forma de la tierra de todo el mundo normalmente se desarrollan coincidiciendo el centro del elipse con el centro real de la tierra.
* Elipsoides locales. Tienen el objetivo de dar alto detalle en una zona definida de la tierra. Es decir mover la elipse de manera que coincida sin estar por encima o por debajo de alguna zona de interes.

<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_2/imagenes/ajuste_elipsoide.jpg" alt="ELIPSOIDE" width=300>

### ¿Qué es un geoide?

Como vimos en los dos apartados anteriores la tierra es una superficie compleja de modelar y el elipse resulta quitando mucho detalle. Por eso es que se desarrolla el modelo de geoide. De forma tecnica un geoide corresponde a medir como la tierra se modela en base a la atraccion de la gravedad en los multiples puntos del planeta y se mide en metros sobre el nivel del mar. De forma mas simple imaginen que estamos cubriend la Tierra con agua y eliminaramos la accion de las mareas o corrientes. En ese sentido el agua se orientaria de acuerdo con la gravedfad de los sitios. Y como la gravedad depende de la materia que tenga el cuerpo se orientaria más alto en las zonas más altas de la tierra (con más materia) como en zonas de montañas y más baja en las zonas bajas (donde menos materia hay). Esto resulta en un modelo que permite estimar las alturas con mayor detalle que el elipsoide permitiendo ver las tendecias de altitud que se da en la superficie del planeta. Pero aun no llegamos a incluir el detalle de las alturas al 100%.

<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_2/imagenes/Geoid.jpg" alt="ELIPSOIDE" width=450>


### ¿Como se relaciona todo esto? (Definición de DATUM)

Recodermos alguna informacion esencial 
+ El geoide tiene mayor detalle de la altura de la tierra y patrones de altitud y depresión en la superficie
+ El elipsoide permite resumir un area completa pero a veces puede quedar debajo o por encima del terreno.
+ Deben existir puntos en donde el elipsoide y el geoide coincidan.

Entonces tenemos dos elementos el elipsoide que nos da el marco de referencia en donde podemos establecer las coordenadas y el geoide que nos permite conocer la forma de la Tierra. Para relacionar ambos contextos debemos tener un elemento que permita interconectarlos y alli es donde cuadra el datum.
De forma simple el datum es un elemento matemático que permite situar a un elipsoide y hacerl coincidir de la mejor forma con el geoide. Para ello se necesita encontrar puntos del elipsoide que coinciden casi perfectamente con el geoide y luego aplicar modificaciones que pueden ser traslaciones, rotaciones, etc. Esto da como resultado un elemto grillado tal como lo vimos la vez pasada cuando analizarmos la regla en Google Earth Pro.

Interaccionando estos tres elementos tenemos lo que se conoce como Sistema de Coordenadas de Referencia (SRC) de momento la definición alcanza para detallar las coordenadas geográficas para analizar las coordendas pryectadas aun debemso hablar de proyecciones. 

*ingresar imagen de datum y desplazamientos

### Información adicional de Datum

El datum de forma muy generalizada funcina como un pegamento que une un elipsoide y una geoide dandole un contexto. Pero cuidado, por que existen multiples elipsoides y datum. Y los resultados finales tambien son diferentes. Por lo que si queremos cambiar de un sistema de coordenadas a otro las ubicaciones sera diferentes puesto qued pueden habier sido creados con elementos distintos entre sí. Asi que tener mucho cuidado en que sistema de coordenas se trabaja y esto incluye a todos los elementos que se vayan a proyectar o crear dentro de un mapa. Pues que pueden haber errores grandes al momento de subir información creada en diferentes elipsoides o datum y este error puede ser de hasta 50 metros por lo que es algo que tenemos que tener mucho en mente. 
Para finalizar tenemos dos tipos de datum, horizontales y verticales. 
  + Los **Datum horizontales** tienen por finalidad corregir el elipsoide de forma lateral
  + Los **Datum verticales** incluyen un elemento adicional que es la altitud. Entonces tenemos tambien coordenadas que modelan elementos 3D en un espacio tridimencional.

 Otra forma de categorizar los datum como como referencia el ambito de correción que tiene teniendo dos claisificaciones datum locales y datum mundial 
  + Los **Datum Locales** tienen un ambito de acción local y normalmente se usa para tener una alta definicnion y que el elipsoide cuadre de muy buena manera en una área muy localizada como un continente o un país. Por ejemplo el PASD56 (Provisional South American Datum 1956) es un sistema que fue muy utilizado en latinoamerica durante el siglo 20 debido a su presicion en la zona de américa del sur sin embargo si se queria usar este datum para zonas como Europa se tendria un error muy gende debido a la deformación del elipsoide para esta zona. 
  + Los **Datum Mundiales** tiene un ámbito de estudio global. Principalmente estos datum usan el centro del mundo como punto de referencia por lo que se establece un elipse bastante preciso para casi todo el mundo pero ojo que aún hay errores a nivel local. El más conocido es el datum WGS84 (World Geodesic System 1984). este lo usaremos constantemente durante el curso.

## Tipos de proyecciones

Con todo lo que hemos visto hasta el momento se einterpreta la tierra como una esfera. Sin embargo, para algunos trabajos es necesario generar un plano horizontal osea intentar deformar la esfera de manera que mantenga algunas propiedades en un plano por ejemplo una hoja. A esto se le llama proyecciones. Las podemos dividir en dos las que mantienen alguna propiedad dentro del terreno (en función de las cualidades métricas) y las que utilizan alguna contruccion geometrica para su conformación (en función de las cualidades proyectivas).
Debemos tener muy en mente que toda proyección es valida para algunos lugares pero deforma otros. Tal com lo vimos anteriormente con la página [The True Size](https://thetruesize.com/) en donde este sistema permitia tener alto detalle de la zona ecuatorial del mundo pero se deformaba cuando nos acercabamos a los polos. 

### Proyecciones en funcion de las cualidades métricas

+ **Proyecciones Conformes**: Una proyección conforme mantiener las ángulos que se forman entre dos lineas en la superficie.

  
+ **Proyecciones Equivalentes**: Una proyección equivalente conserva la superficie del terreno.

  
+ **Proyecciones Equidistantes**: En este tipo de proyección se mantiene la distancia entre dos puntos.

  
+ **Proyeccion Afilácticas**: Noo conserva ninguna propiedad interna del mapa pero mantienen una persepcion del aspécto general de la tierra teniendo muy bajas distorsiones.


### Proyecciones en función de las cualidades proyectivas

+ **Proyeccion Planar o Azimutal**: Imaginene que tenemos una hoja y la colocamos sobre un balon de futbol de manera que solo haya un punto de toque en la esfera y la hoja se mantenga plana. Si vemos desed arriba lo que se observara un nivel alto de detalle de la tierra en el punto donde se da el toque entre ambos objetvos pero que se ira deformando conforme nos alejemos a los bordes. Esto es basicamente una proyeccion planar. Se consigue asignando un plano de observacion sobre la esfera que tenga un punto de orientacion principal. Esto generá una proyección en donde el mayor nivel de detalle se encuentra en el puntos y en las áreas mas cercanas deformandose conforme nos vamos alejando del punto focal.



+ **Proyección Cónica**: Se utiliza la figura de un cono para establcer la proyección. Basicamente consiste en ingresar la tierra dentro de un cono. hay multiples sonas de toque entre ambas formas. Esto es util para establecer proyecciones en latitutes altas del munto (los polos y zonas aledañas). El detalle se hace mayor con forme nos acercamos al vertice del cono y va deformandose si nos vamos acercando a su base.



+ **Proyección cilíndrica**: las proyecciones cilindricas consisten en utilizar un cilintro e ingresar la esfera dentro de forma que quede suspendida en la mitad. Esta proyección es la más común y conocida. Esta guarda mucho nivel de detalle en la zona ecuatorial del mundo pero tiene deformaciones con forme nos acercamos a los polos. Es la misma proyección que podemos observar en la pagina [The True Size](https://thetruesize.com/). Esta proyecciíon asi mismo es la que se utiliza en el sistema UTM (Universal Transversal Mercator).
  


## Coordenadas proyectadas

Las coordendas proyectadas surgen de interaccionar todo lo que hemos visto hasta el momento. Una coordenada proyectada se basa inicialmente en una sistema de coordenadas geográfico al que se le asigna una proyección. Lo que permite establecer una nueva representacion de la tierra trabajada para tener una mejor resolución de la zona de interes. Existen multiples tipos de coordendas proyectadas para este curso tomaremos especial enfasis en las coodenadas UTM ya que corresponden al estandar genral de trabajos de ingeniería del Perú.

### Sistema de coordendas UTM 

El sistema de coordendas UTM se basa en el elipsoide y datum WGS84 y desarrolla una proyección cilindrica de la zona. Recuerdemos que el datum WGS84 hace referencia a las coordenadas geográficas.

Resultado de esta interacción se forman 60 zonas cuya longitud es 6° dentro del elipse de referencia. La unidad con la que se trabajan estos datos ya no son grados sino en su lugar son metros, este cambio de unidades es gracias a la proyección que ejecutamos, recuerden que al ejecutar una proyeccion estamos aplanando la esfera en una zona que es la que nos interesa. Estas zonas tienen una division marcada en el ecuador existiendo unas zonas norte y una sur,

Asi mismo se caracteriza por que las coordendas latitud y longitud cambian a coordenda Norte/Sur (mN o mS) y coordenada Este (mE) respectivamente. Tambien desaparecen los paralelos y meridianos de referencia. 

Este sistema de coordenadas trae mucho detalla a la zona de trabajo seleccionada pero se deforma el resto del mundo por lo que antes de configurar o cambiar las coordenadas de un area gregrafica seria bueno primero analizar en que zona se encuentra ubicada.



## ¿Qué es escala de trabajo?

El último concepto que abordaremos el dia de hoy es la escala. La escala es una forma de representar nuestro mundo en un espacio pequeño. El mundo real se ve en una escala de 1:1 es decir que todo guarda el tamaño que realmente tiene. Si por alguna razon todo se encogiera a la mitad con excepcion de la persona que esta leyendo esto la escala en la que vivirias seria 1:2 y si se siguiera encogiendo el numeoro iria aumentado. En este escenario, cada vez que la escala se haga mas grande la persona seria capaz cada ver de ver más zonas.+
De este ejemplo se resaltan dos cosas.
1. Con el numero se hace mas grande el area se hace cada vez mas pequeña
2. Mientras mas pequeña el area mas elementos del mundo somos capacez de observar.

![escala](https://github.com/user-attachments/assets/45ef8092-b7aa-44d6-bca4-26324cc3e5c1)

En la imagen pueden ver la misma zona pero en diferentes escalas y al ingual que en nuestro ejemplo mientras más grande se hace el numero podemos observar cada vez mas detalles de la ciudad. Este elemento hay que tenerlo siempre presente poro que nos permitira establecer una tamnaño tamto de impresion como de detalle del mapa que querramos crear. 
Asi pues para represntar una casa no se usaran escalas muy grandes y para representar una ciudad no se usaran escalas pequeñas.


# Introducción al GIS con Qgis 

Habiendo definido todo lo anterior estamos listos para iniciar con el manejo de la plataforma QGIS. Empezaremos analizando su interfaz el sistema de instalacion y luego crearemos nuestro primer mapa.

## Instalación de Qgis

* Ingresa a la sigueinte pagina https://qgis.org/download/
* Dar link a <img src="https://github.com/user-attachments/assets/ff91cc12-de8b-4d13-b86a-671c0a557bb7" alt="ELIPSOIDE" width=250> y hacemos click a Long Term Version
* Al finalizar la descarga ejecutamos el programa que descargamos y eso nos permitira tener instalado el programa. 

## Interfaz de trabajo en Qgis

La interfaz de Qgis se analiza en base a panales que pueden ubicarse a los costados y barras que se ubican en la parte superior por defecto. Más adelante veremos que todo ello se puede modificar. 

+ Barra Configuración: Aqui tendremos una serie de menús que nos permitiran modificar, operar y analizar una serie de elementos que vayamos generando y creando. Mas adelante pondremos enfasis en una de estas opciones
+ Barra de Utilidades: En la barra de utilidades encontraremos iconos que nos permiten ejecutar acciones dentro del visor. Cada complemento adicional que instalemos nos dara una nueva bara de utilidades.
+ Menú de capas: Aquí apareceran todos los elementos que ingresemos al Mapa al igual que el Gogle Erath Pro. Exploraremos sobre la creación de entidades y formatos de trabajo. 
+ Visor Principal: Es el analogo al visor de Google Earth Pro sin embargo este esta en blanco, con forme vayamois subiendo capas apareceran cada vez mas elementos.
+ Caja de herramientas: La caja de herramientas es parte del panel lateral este panel lateral puede ser adaptado modificado o eliminado de acuerdo a las configuraciones individuales de cada uno de ustedes. La caja de herramientas no da todas las opciones de procesamiento que nos ofrece el programa, las multiples herramientas que tenemos aqui nos van a permitir hacer una serie de trabajos y obtener mas informacion de los terrenos bajo análisis.
+ Navegador: El navegar es un elemtno que nos permite visualizar las carpetas que creamos. Es importante mantener el orden asi que procuren crear una carpeta por cara proyecto que tengan activo, asi mismo ordenar todos sus archivos para no tener ningun inconveniente luego.

<p align="center">
  <img src="https://github.com/user-attachments/assets/a90e69d4-df6a-45ad-8420-260661746961" alt="ELIPSOIDE" width=1000>

____________________________________________________________________________________________________________________________________________

## Actividad N°1 Configuración Inicial del Programa

### Creación de carpetas
1. Debemos verificar que el panel de Navegacion esta activo. Para ello haremos clic en cuaquiera de los lugares en blanco en las barras de utilidad y hacemois clic derecho debera salir una ventana con multiples opciones en las que debemos fijarnos que la opcion  ![image](https://github.com/user-attachments/assets/972e8261-a218-4ee2-a3f0-658f42540769) este activa como en la imagen.

![image](https://github.com/user-attachments/assets/b2346583-5ba5-41ef-a545-4bd3afec83c1)

2. Nos dirigimos al panel de Navegación y reconocemos que aparecen una serie de iconos con multiples elementos.  
![image](https://github.com/user-attachments/assets/613bfdb9-cd2a-4511-9f1a-5560842dc051)

En el panel se distinguen dos zonas la primera es de carpetas aqui crearemos nuetra carpeta de trabajo y la seguinda en una ventana con datos. Todo lo que observamos son los datos y tipos de archivos que puede leer el Qgis estas van desde servidores, formatos complejos de empaquetamiento de datos y mapas base descargados. Aqui tenemos que ubicar la opcion favoritos y darle clic derecho la unica opcion que saldra es "Añadir un directorio..." debemos dar clic a esa opción

![image](https://github.com/user-attachments/assets/0b140b73-cc94-4cd8-b600-1688cc599dda)

 4. Al hacer clic nos saldra una ventana estilo buscador en donde debemos colocar una carpeta. Dentro del disco C crearemos una nueva carpeta que se llame "clases_sig" y dentro de ella la carpeta que se llame "Primera_clase" seleccionaremos esta ultima carpeta. Si todo salio bien la carpeta debera aparecer como una opcion debajo de Favoritos como se puede ver en la imagen.

![image](https://github.com/user-attachments/assets/62ebee17-256f-4d99-a102-806f9d8c2e45)

### Instalacióin de complementos (Complemento QuickMapServices)
1. Nos dirigiremos a la barra de configuración y ubicamos la opcion complementos al hacer clic saldran dos opciones haremos clic en la primera "Administrar e instalar complementos..."

![image](https://github.com/user-attachments/assets/ce7f47c4-a035-4ba3-bb82-b5c9b22bee01)

3. Esto nos aperturara una nueva ventana. Los complementos son como como aplicaciones de celular nos permiten tener mas opciones y desbloquear mas funcionalidades. En la ventana que nos salio hay 5 opciones a las izquierda
   + Todos: Nos muestran todos los complmentos que estan disponibles para descargar e incluye los que ya tenga instalados en mi computadora. 
   + Instalado: Me muestra solo los complementos instalados en mi computadora
   + No instalado: Nos muestra los componentes que estan por instar en mi computadora 
   + Instar a partir de ZIP: Es una opción que me permite instalar complementos en versiones antiguas. Tenr cuidado con esto por que puede ser una ventana tambien para instalar virus.
   + Configuración: Opciones de configuracion de los complementos.

   Nos dirigiremos a la ventana de todos y aparecera un buscador alli colocar "QuickMapServices" ubicamos el complento con el mismo nombre y le damos clic. 

4. En esta nueva ventana haremos clic en instalar complemento y dejamos que se instale.
![image](https://github.com/user-attachments/assets/10ac69cb-5fd2-4c26-9d51-69a2d29fa868)

5. Finalizada la descarga deberemos activar el complemento. Para ello regresaremos a la barra de configuración y ubicaremos la opción de "Web" alli encontraran la opcion QuickMapServices y debemos desplegar sus opciones ubicaremos la opcion de configuracion (Settings) y haremos clic alli. 
![image](https://github.com/user-attachments/assets/d21d26c0-4d8c-4ade-9ee5-5f950f0161b0)

6. Se abrirá una nueva ventana y deremos ubicar la opcion More services y finalmente hacer clic en Get contributed pack. Esto se debe repetir en cada maquina en la que instalemos el complemento.

![image](https://github.com/user-attachments/assets/2af95780-a9cb-4a4e-bbfd-9ae79d811f8c)

6. Uan vez hecho ello regresaremos a la barra de configuracion en el menu web y desplegaremos nuevamente la opcion QuickMapServices alli veremos que hay multiples opciones de mapas desde Google hasta OpenStreetMaps esto se conoce como mapa base y permitira que visualicemos vistas satelitales al igual que en Google Earth Pro. Para este ejercicio haremos clic en google y seleccionaremos la opción Google Hybrid eso nos generar un mapa satelital que se mostrata en el panel de Capas. Les invitamos a que exploren el resto de los mapas base que trae este complemento.

![image](https://github.com/user-attachments/assets/2b1dd1c9-7f99-4ccb-92d9-17fae399ea77)
![image](https://github.com/user-attachments/assets/a1136473-fdeb-43e9-8b69-d54bc4efe3fc)
___________________________________________________________________________________________________________________________________________

## Descarga de datos y subida


____________________________________________________________________________________________________________________________________________
Actividad N°2 Descarga y seleccion de datos de trabajo

____________________________________________________________________________________________________________________________________________

## Composición de Mapas
____________________________________________________________________________________________________________________________________________
Actividad N°3 Introduccion a la creación de mapas

____________________________________________________________________________________________________________________________________________


#Asignación
