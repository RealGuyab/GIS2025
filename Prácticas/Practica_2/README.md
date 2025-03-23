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


ahhs







## Coordendas Geográficas

## Tipos de proyecciones

### Proyección Cilindrica 

### Proyección Cónica

### Proyeccion Planar o azimutal

## Coordenadas proyectadas

## ¿Qué es escala de trabajo?

##¿Qué es y para que sirve un Mapa?

### Relacion entre escala de trbajo y presentacion final

# Introducción al GIS con Qgis 

## Instalación de Qgis

## Interfaz de trabajo en Qgis

## Composición de Mapas

