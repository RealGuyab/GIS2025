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
Debemos tener m uy en mente que toda proyección es valida para algunos lugares pero deforma otros. Tal com lo vimos anteriormente con la página [The True Size](https://thetruesize.com/)

### Proyecciones en funcion de las cualidades métricas

+ **Proyecciones Conformes**: Una proyección conforme mantiener las ángulos que se forman entre dos lineas en la superficie.

  
+ **Proyecciones Equivalentes**: Una proyección equivalente conserva la superficie del terreno. 
+ **Proyecciones Equidistantes**: En este tipo de proyección se mantiene la distancia entre dos puntos.
+ **Proyeccion Afilácticas**: N

### Proyecciones en función de las cualidades proyectivas

+ **Proyección Cónica**:
+ **Proyeccion Planar o Azimutal**:
+ **Proyección cilíndrica**:

## Coordenadas proyectadas

## ¿Qué es escala de trabajo?

##¿Qué es y para que sirve un Mapa?

### Relacion entre escala de trbajo y presentacion final

# Introducción al GIS con Qgis 

## Instalación de Qgis

## Interfaz de trabajo en Qgis

## Composición de Mapas

