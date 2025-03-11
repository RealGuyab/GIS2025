# <p align="center"><ins>Qgis Prácticas<ins></p>

# Introducción al curso

![introduccion a GIS](https://github.com/RealGuyab/Qgis/blob/main/imagenes/geographic-information-system-vector.jpg)

## ¿Que es un Sistema de información Geográfica?
Los sistemas de información geográfica abreviado SIG o GIS en inglés son una serie de elementos que funcionan en conjunto y permiten analizar información espacial, estudiarla, representarla y generar productos útiles para la sociedad. Todos alguna vez hemos utilizado algún producto cuya fuente principal es el GIS. El ejemplo más común es Google Street View o el sistema de compartir ubicación de WhatsApp. Estos dos programas funcionan a través de una dispositivo fisico que bien pude ser una computadora o un celular y nos muestran un mapa en donde podemos hacer seguimiento buscar algunas ubicaciones alrededor del mundo. Todo GIS esta compuesto por elementos importantes los que son información espacial (data), plataformas de visualización de datos (Hardware), programas de procesamiento de datos (Software), desarrolladores y usuarios (personas). Para comprender algunos de estos terminos tenemos primero que definir algunos conceptos que vienen acontinuación.


## ¿Qué es ***información espacial***?

Cuando se habla de información espacial estamos hablando de información común y corriente pero que puede ser interpretada con coordenadas o una ubicación en el espacio. Para ilustrar ello nos pondremos en la siguiente situación. 
Supongan que un compañero suyo les pregunta donde queda la clase de Sistemas de Informacion Geografica (GIS), lo primero que se nos viene a la mente al intentar responder esta pregunta es una serie de instrucciones como un camino, múltiples referencias y luego todas ellas se estructuran y nos dan la ruta más óptima. La respuesta bien podria ser: 

"Entra por la ***<ins>puerta de San Juan<ins>***, llega al centro y dirígite a la ***<ins>plaza central<ins>***, voltea a la derecha donde se encuentran unas ***<ins>gradas<ins>*** y camina a la izquierda sigue como yendo a la ***<ins>biblioteca<ins>*** y la ***<ins>clase de GIS es el E105<ins>***" 

Basicamente su cerebro analizó el terreno encontrando algunas referencias espaciales y luego diseño la ruta que se tradujo en instrucciones. Sin embargo, toda esta información no tendria ningun sentido si en primer lugar las ubicaciones a las que hicimos referencia no estuvieran en un lugar en el espacio.

![Ubicaciuon cato](https://github.com/RealGuyab/Qgis/blob/main/imagenes/ubicacion_cato.png)

Entonces se entiende como información espacial a cualquier tipo de informacion que además de darnos datos sobre algo en especifico como los nombres de los pabellones o las clases tienen una ubicación en el espacio definida que cualquier persona es capaz de encontrar. A esto se le conocen como coordenadas.

### ¿Qué es una coordenada?

Las coordenadas son pares de números, que pueden estar en múltiples formatos, que en resumen nos permiten encontrar algún objeto en la tierra. Cuando enviamos nuestra ubicación por WhatsApp o cuando se busca un sitio en google en resumen lo que queremos consultar son sus coordenadas. 
El formato más común de coordenadas es grados minutos y segundos. Sin embargo a través del curso veremos que no es el único que existe y analizaremos también sus ventajas y desventajas.
Toda coordenada viene en pares puesto que analiza la lóngitud y la latitud respecto de algunas lineas que se trazan en el mundo. No es necesario que comprendan esto aÚn por que más adelante abordaremos este tema en mayor profundidad pero si es necesario que tengan siempre en mente que una coordenada son dos numeros y uno es la longitud y el otro la latitud.

<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/imagenes/coordenadas.png" alt="Ubicaciuon cato">
</p>

## ¿Qué hardware funciona para el GIS?

El tipo de hardware normalmente depende de lo que querramos lograr pero podemos dividirlo en dos tipos. El primero que tiene la finalidad de recolectar información espacial en este primer grupo se pueden incluir herramientas como GPS, estaciones metereológicas, satélites en sus múltiples tipos, drones, etc. La función principal de este tipo de Hardware corresponde a recolectar la mayor cantidad de información con coordenadas que pueda ser extraida de un lugar para luego poder procesarla e interpretarla.
El segundo tipo de hardware tiene por finalidad la lectura, procesamiento, interpretación y representación de datos. Normalmente hacemos referencia a las computadoras, estaciones de trabajo, etc. Dependiendo del programa que se vaya a trabajar y del alcance al que se quiera llegar los requisitos pueden ser muy variables. El curso se enfoca en Qgis, asi de acuerdo con los documentos oficiales los requisitos recomendados son Procesdador de 1.9 GHz o superior, Memoria RAM de 8 GB, Tarjeta de video de 2Gb o más, disco duro o SSD de 250 GB o más.
Los requisitos anteriormente descritos se dan para poder utilizar la mayoria de procesos en Qgis. Sin embargo, ello no significa que computadoras con criterios más bajos que los indicados no puedan correr el programa. Los requisitos mínimos de Qgis son realmente bajos por lo que cualquier computadora moderna los cumple sin ningún problema. 

![Ejemplo de vuelo de dron](https://github.com/RealGuyab/Qgis/blob/main/imagenes/programacion_vuelo.png)

## ¿Qué software se utilizan para procesar GIS?

Existen multiples programa que permiten procesas y analizar informacion GIS algunos se encuentran especializados en algunas seccioones como el analisis de imagenes de satelites. Los más conocidos y utilizados a nivel mundial son dos. 

![arcgis vs qgis](https://github.com/RealGuyab/Qgis/blob/main/imagenes/arcgis_qgis.jpg)

### Arcgis
Es un programa desarrollado por ESRI empresa pionera en temas de GIS. Arcgis es un programa que funciona mediante una licencia que se compra y que da acceso a todas las potencialidades que el programa ofrece. Existen dos plataformas actualmente vigentes en donde se pude utilizar el producto de ESRI el primero es ARCMAP y todas sus dependencias. Este programa salio en 1999 y actualmente se encuentra en proceso de migracion a la segunda plataforma cabe resaltar que el fin del soporte de este software esta programado para marzo del 2026. 
La segunda plataforma es ARCGIS PRO tamien de licencia paga que es una evolución de ARCMAP ofrece una mejor interfaz de trabajo e integracioon mejorada comparada con su antecesor. Para poder utilizar todfos loos compoenentes que ofrecen estos programas existen requisitos más exigentes que puden consultar en la siguiente pagina. Para ARCMAP(https://desktop.arcgis.com/es/system-requirements/latest/arcgis-desktop-system-requirements.htm) y para ArcGIS PRO (https://pro.arcgis.com/en/pro-app/latest/get-started/arcgis-pro-system-requirements.htm).

### Qgis
Es una programa de desarrollo abierto lo que significa que no es necesario la compra de ninguna licencias. Tiene potencialidades muy similares al ArcGis manteniendo una interfaz de trabajo muy intuitiva y opciones de edición bastante completas. Cuenta con dos opcines de descarga la version LTR que presenta una mayor estabilidad y la version más actual. Qgis es una plataforma con un crecimiento constante año tras año. Su principal fortaleza es que es un software libre lo que permite expandir sus potencialidades constantemente generando nuevas herramientas de procesamiendo de acuerdo con las necesidades de los usuarios. 

Ambas plataformas permiten un analisis completo de la informacion espacial. Para fines de este curso nos enfocaremos en el Qgis. 









