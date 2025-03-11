# <p align="center"><ins>Qgis Prácticas<ins></p>

# Introducción al curso

![introduccion a GIS](https://github.com/RealGuyab/Qgis/blob/main/imagenes/geographic-information-system-vector.jpg)

## ¿Que es un Sistema de información Geográfica?
Los sistemas de información geográfica abreviado SIG o GIS en inglés son una serie de elementos que funcionan en conjunto y permiten analizar información espacial, estudiarla, representarla y generar productos útiles para la sociedad. Todos alguna vez hemos utilizado algún producto cuya fuente principal es el GIS. El ejemplo más común es Google Street View o el sistema de compartir ubicación de WhatsApp. Estos dos programas funcionan a través de una dispositivo fisico que bien pude ser una computadora o un celular y nos muestran un mapa en donde podemos hacer seguimiento buscar algunas ubicaciones alrededor del mundo. Todo GIS esta compuesto por elementos importantes los que son información espacial (data), plataformas de visualización de datos (Hardware), programas de procesamiento de datos (Software), desarrolladores y usuarios (personas). Para comprender algunos de estos terminos tenemos primero que definir algunos conceptos que vienen acontinuación.


## ¿Qué es ***información espacial***?

Cuando se habla de información espacial estamos hablando de información común y corriente pero que puede ser interpretada con coordenadas o una ubicación en el espacio. Para ilustrar ello nos pondremos en la siguiente situación. 
Supongan que un coompañero suyo les pregunta donde queda la clase de Sistemas de Informacion Geografica, lo primero que se nos viene a la mente al intentar responder esta pregunta es una serie de instruccion como un camino, multiples referencias y luego
todas ellas se estructuran y nos dan una ruta más óptima. La respuesta bien podria ser: 

"Entra por la ***<ins>puerta de Sán Juan<ins>***, llega al centro y dirígite a la ***<ins>plaza central<ins>***, voltea a la derecha donde se encuentran unas ***<ins>gradas<ins>*** y camina a la izquierda sigue como llendo a la ***<ins>biblioteca<ins>*** y la ***<ins>clase de GIS es el E103<ins>***" 

Basicamente su cerebro analizó el terreno encontrando algunas referencias espaciales y luego diseño la ruta que se tradujó en instrucciones. Sin embargo, toda esta información no tendria ningun sentido si en primer lugar las ubicaciones a las que hicimos referencia no estuvieran en un lugar en el espacio. Su cerebro es capaz de interpretar informacion espacial.

![Ubicaciuon cato](https://github.com/RealGuyab/Qgis/blob/main/imagenes/ubicacion_cato.png)

Entonces se entiende como información espacial a cualquier tipo de informacion que además de darnos datos sobre algo en especifico como los nombres de los pabellones o las clases tienen una ubicacion espacial definida que cualquier persona es capaz de encontrar. A esto se le coonoce como coordenadas.

### ¿Qué es una coordenada?

Las coordenadas son pares de numeros, que pueden estar en multiples formatos, que en resumen nos permiten encontrar algun objeto en la tierra. Cuando enviamos nuestra ubicación por Whastapp o cuando se busca algun sitio en google en resumen lo que queremos consultar 
son sus coordenadas. 
El formato más común de coordenadas es grados minutos y segundos. Sin embargo a travez del curso veremos que no es el unico y que existen algunos y analizaremos tambien sus ventajas y desventajas.
Como les habia comentado una coordenada es un par de numeros toda coordenada viene en pares puesto que analiza la longitud y la latitud respecto de algunas lineas que se trazan en el mundo. No es necesario que comprendan esto aun por que mas adelante abordaremos este tema en mayor profundidad pero si es necesario que tengan siempre en mente que una coordenada son dos numeros y uno es la longitud y el otro la latitud.

<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/imagenes/coordenadas.png" alt="Ubicaciuon cato">
</p>

## ¿Que hardware funciona para el GIS?

El tipo de hardware normalmente depende de lo que querramos lograr pero podemos dividirlo en dos tipos. El primero que tiene la finalidad de recolectar información espacial en este primer grupo se pueden incluir herramientas como GPS, estaciones metereologicas, satelites en sus multiples tipos, drones, etc. La funcion principal de este tipos de Hardware corresponde a recolectar la mayor cantidad de informacion con coordenadas que pueda ser extraida de un lugar para luego poder procesarla e interpretarla.
El segundo tipo de hardware tiene por finalidad la lectura, procesamiento, interpretacion y representacion de datos. Normalmente hacemos referencia a las computadoras, estaciones de trabajo, etc. Dependiendo del programa que se vaya a trabajar y del alcance al que se quiera llegar los requisitos pueden ser muy variables. El curso se enfoca en Qgis asi de acuerdo con los documentos oficiales los requisitos recomendados son Procesdador de 1.9 GHz o superior, Memoria RAM de 8 GB, Tarjeta de video de 2Gb o más, disco duro o SSD de 250 GB o más.
Los requisitos anteiormente descritos se dan para poder utilizar la mayoria de procesos en Qgis. Sin embargo, ello noo significa que computadoras con criterios bajos que los indicados no puedan correr el programa. Los requisitos minimos de Qgis son realmente bajos pr lo que cualqueir computadora moderna los cumple sin ningun problema. 

## ¿?









