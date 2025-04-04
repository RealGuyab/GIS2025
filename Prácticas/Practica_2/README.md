# Práctica N°2: Introducción a Qgis

## Competencias

1. Conocer la plataforma Qgis.
2. Identificar las diferencias entre coordendas geograficas y proyectadas.
3. Reconocer los elementos minimos que deben estar presentes en un mapa.


## ¿Qué es una coordenada?

Las coordenadas como lo vimos anteriormente son números que nos indican la posición de un elemento en el espacio. Haciendo recuerdo, hablamos de dos sistemas de coordenadas: 

+ Las coordenadas Geográficas
+ Las coordenadas Proyectadas

En la sesión anterior definímos lo que es una coordenada geográfica y cómo es que se interpreta en base a los múltiples formatos que presenta Google Earth Pro. En esta sesión nos enfocaremos principalmente en la definición de las coordenadas proyectadas, pero abordaremos conceptos que también se aplican a las coordenadas geográficas. A continuacion, analizaremos algunos conceptos previos que permitirán dar más detalle y contexto de lo que es una coordenada. 

## ¿Cuál es la verdadera forma de la tierra?

Todos alguna vez en nuestra vida nos hemos hecho esa pregunta. Es sabido que la forma de la Tierra es esférica, esto se determinó hace mucho tiempo. Esto fue propuesto en la antigua Grecia, aproximadamente en el año 240 A.C, y fue Eratóstenes, un matemático, quien con un simple experimento (utilizando palos y sombras) pudo medir la circunferencia de la tierra con una muy buena precisión. Sin embargo, cuando hablamos de una esfera el contexto pude ser un poco ambiguo. 
Existen múltiples tipos de esfera, tales como: esferas perfectas, esferoides, elipsoides, etc.

<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_2/imagenes/esferas.png" alt="TIPOS ESFERAS" width=550>

## Generalización de la forma de la tierra

La superficie de la tierra es algo muy irregular. Se tienen montañas, valles, cañones, ríos, etc. Todos estos elementos son muy difíciles de modelar, tomando en cuenta que en la mayoría de mapas o modelos de la tierra se dispone únicamente de una superficie plana como una hoja o una pantalla. Es por esto que se desarrollan modelos con un mayor grado de simplificación. A esto le llamaremos generalización de los modelos de la tierra.

<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_2/imagenes/nivel_generalizacion.png" alt="TIPOS ESFERAS" width=300>

Como pueden observar en la imagen, conforme vamos bajando, encontramos diversos modelos. Estos modelos van perdiendo detalle si tomamos en cuenta la superficie inicial de la tierra. Sin embargo, nos permiten desarrollar cálculos matemáticos más precisos y a partir de ellos generar herramientas como las coordenadas o sistemas de posicionamiento. 

Los modelos que analizaremos en este apartado serán principalmente dos:
+ Elipsoides
+ Geoide
  
Esto nos permitirá entender algunos elementos adicionales como los datum o las proyecciones. Todo esto se estudia en la Geodecia, que es la ciencia que permite ubicar cosas en la Tierra con mucha precisión. La información que se coloca en la página servirá como un inicio si alguno estuviera interesado en tomar mayor detalle espero que esto le sirva como punto de partida.  

### ¿Qué es un geoide?

Como vimos en los dos apartados anteriores la tierra es una superficie compleja de modelar y el elipse resulta quitando mucho detalle. Por eso es que se desarrolla el modelo de geoide. De forma técnica, un geoide corresponde a medir cómo la tierra se modela en base a la atracción de la gravedad en la superficie del planeta y se mide en metros sobre el nivel del mar. De forma más simple, imaginen que estamos cubriendo la Tierra con agua y eliminamos la acción de las mareas o corrientes. En ese sentido el agua se orientaría de acuerdo con la gravedad de los sitios. Como la gravedad depende de la materia que tenga el cuerpo se orientaría más alto en las zonas más altas de la tierra como en zonas de montañas (con más materia) y más bajo en las zonas bajas (donde hay menos materia). Esto resulta en un modelo que permite estimar las alturas con mayor detalle que el elipsoide, permitiendo ver las tendecias de altitud que se da en la superficie del planeta. Pero aún no llegamos a incluir el detalle de las alturas al 100%.

<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_2/imagenes/Geoid.jpg" alt="ELIPSOIDE" width=450>

## ¿Qué es un elipsoide?

Todos hemos visto el modelo más comun de la tierra, en donde se muestra una esfera completamente perfecta. Esta forma de representar la tierra es una artística, ya que no coincide con su forma real. Si tuvieramos que ser más precisos sin incluir todavia valles, montañas, etc. estariamos hablando de una esfera que se encuentra achatada en los polos (esfera oblata), si reducimos aún más la complejidad o nos fijamos solo en los bordes, la figura resultante sería una elipse. 

<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_2/imagenes/ESFERA_OBLATA.png" alt="ELIPSOIDE" width=600>

El elipsoide surge de esta idea de representar la tierra de forma más precisa. Sintetizando la idea, un elipsoide es una superficie homogénea (sin perturbaciones) que engloba toda la tierra y la aproxima hacia una esfera. Se le conoce como la forma matemática de la Tierra, por que mediante la aplicación de cálculos se puede llegar a la misma forma que hemos interpretado de forma visual. Este elipse da origen principalmente a las coordenadas geográficas que, como vimos la clase anterior, asumen la tierra como una esfera o, en este caso, una semiesfera. 
Lamentablemente, el elipse no es preciso en todos los lugares de la tierra. Como hemos hecho una simplificación y la tierra tiene ciertas deformidades superficiales la línea que se establace como límite del elipsoide puede quedar por debajo o sobre el terreno, a esto se le conoce como ondulación geoidal. Esto se corrige posteriormente con algunos elementos adicionales que veremos más adelante. Existen múltiples elipsoides, desarrollaremos hasta el momento, algunos más precisos en algunas zonas. 
Se tienen dos tipos de elipsoides: 
* Elipsoides globales: tienen la función principal de resumir la forma de la tierra, normalmente se desarrollan coincidiendo el centro del elipse con el centro real de la tierra.
* Elipsoides locales: tienen el objetivo de dar alto detalle en una zona definida de la tierra. Es decir mover la elipse de manera que coincida sin estar por encima o por debajo de alguna zona de interes.

<p align="center">
  <img src="https://github.com/RealGuyab/Qgis/blob/main/Pr%C3%A1cticas/Practica_2/imagenes/ajuste_elipsoide.jpg" alt="ELIPSOIDE" width=300>

### ¿Cómo se relaciona todo esto? (Definición de DATUM)

Recodermos información esencial 
+ El geoide tiene mayor detalle de la altura de la tierra, patrones de altitud y depresiones en la superficie.
+ El elipsoide permite resumir un área completa, pero a veces puede quedar debajo o por encima del terreno.
+ Deben existir puntos en donde el elipsoide y el geoide coincidan.

Entonces, tenemos dos elementos: el elipsoide que nos da el marco de referencia en donde podemos establecer las coordenadas y el geoide que nos permite conocer la forma de la Tierra. Para relacionar ambos contextos debemos tener un elemento que permita interconectarlos, allí es donde cuadra el DATUM.
De forma simple, el DATUM es un elemento matemático que permite situar a un elipsoide y hacerlo coincidir de la mejor forma posible con el geoide. Para ello, se necesita encontrar puntos del elipsoide que coincidan casi perfectamente con el geoide y, luego, aplicar modificaciones que pueden ser traslaciones, rotaciones, etc. Esto da como resultado un elemento grillado, tal como lo vimos la vez pasada cuando analizamos la regla en Google Earth Pro.

La interacción de estos tres elementos  se conoce como Sistema de Coordenadas de Referencia (SRC), de momento la definición alcanza para detallar las coordenadas geográficas, para poder analizar las coordenadas proyectadas aún debemos hablar de proyecciones. 

### Información adicional de DATUM

El DATUM de forma muy generalizada funciona como un pegamento que une un elipsoide y un geoide, dandole un contexto. Pero cuidado, porque existen múltiples elipsoides y datum. Y los resultados finales también son diferentes. Por lo que, si queremos cambiar de un sistema de coordenadas a otro, las ubicaciones seran diferentes puesto que pueden haber sido creados con elementos distintos entre sí. Asi que tengan mucho cuidado en que sistema de coordenas se trabaja y esto incluye a todos los elementos que se vayan a proyectar o crear dentro de un mapa. Puesto que pueden haber errores grandes al momento de subir información creada en diferentes elipsoides o datum y este error puede ser de hasta 50 metros, por lo que es algo que tenemos que tener mucho en mente. 
Para finalizar tenemos dos tipos de DATUM: horizontales y verticales. 
  + Los **Datum horizontales** tienen por finalidad corregir el elipsoide de forma lateral.
  + Los **Datum verticales** incluyen un elemento adicional que es la altitud. Entonces tenemos también coordenadas que modelan elementos 3D en un espacio tridimensional.

 Otra forma de categorizar los DATUM es en base al ámbito de correción que tiene dos clasificaciones: datum locales y datum mundiales.
 
  + Los **Datum locales** tienen un ambito de acción local y normalmente se usa para tener una alta definición y que el elipsoide cuadre de muy buena manera en una área muy localizada, como un continente o un país. Por ejemplo, el PASD56 (Provisional South American Datum 1956) es un sistema que fue muy utilizado en latinoamérica durante el siglo XX debido a su presición en la zona de América del Sur. Sin embargo, si se quisiera usar este datum para zonas como Europa se tendría un error muy grande debido a la deformación del elipsoide para esta zona. 
  + Los **Datum mundiales** tiene un ámbito de estudio global. Principalmente estos datum usan el centro del mundo como punto de referencia, por lo que se establece un elipse bastante precisa para casi todo el mundo, pero ojo que aún hay errores a nivel local. El más conocido es el DATUM WGS84 (World Geodesic System 1984). Este lo usaremos constantemente durante el curso.

<p align="center">
  <img src="https://github.com/user-attachments/assets/e5063edf-afb1-458b-96e5-877a961a02be" alt="ELIPSOIDE" width=450>

## Tipos de proyecciones

Con todo lo que hemos visto hasta el momento se interpreta la tierra como una esfera. Sin embargo, para algunos trabajos es necesario generar un plano horizontal, o sea intentar deformar la esfera de manera que mantenga algunas propiedades en un plano. Por ejemplo, una hoja. A esto se le llama proyecciones. Las podemos dividir en dos: las que mantienen alguna propiedad dentro del terreno (en función de las cualidades métricas) y las que utilizan alguna contrucción geométrica para su conformación (en función de las cualidades proyectivas).
Debemos tener en mente que toda proyección es valida para algunos lugares, pero deforma otros. Tal como lo vimos anteriormente con la página [The True Size](https://thetruesize.com/) en donde este sistema permitia tener alto detalle de la zona ecuatorial del mundo, pero se deformaba cuando nos acercabamos a los polos. 

### Proyecciones en función de las cualidades métricas

+ **Proyecciones conformes**: una proyección conforme mantiene los ángulos que se forman entre dos líneas en la superficie.
  
<p align="center">
<img  src = "https://github.com/user-attachments/assets/0d81d443-3dfc-4b97-9679-dca570cef6db" alt="conforme">
  
+ **Proyecciones equivalentes**: una proyección equivalente conserva la superficie del terreno.

<p align="center">
<img  src = "https://github.com/user-attachments/assets/e4462c82-0d2c-4d0f-925d-16ce50084a7a" alt="conforme">
  
+ **Proyecciones equidistantes**: en este tipo de proyección se mantiene la distancia entre dos puntos.

<p align="center">
<img  src = "https://github.com/user-attachments/assets/2285e583-cd33-4c97-b6ce-8773f0cffeb4" alt="conforme">

+ **Proyeccion afilácticas**: no conserva ninguna propiedad interna del mapa, pero mantiene una percepción del aspecto general de la tierra teniendo muy bajas distorsiones.

<p align="center">
<img  src = "https://github.com/user-attachments/assets/18b9e4d4-a14b-4fd5-9e55-b2a49ad8e104" alt="conforme">

### Proyecciones en función de las cualidades proyectivas

+ **Proyeccion planar o azimutal**: imagine que tenemos una hoja y la colocamos sobre un balón de fútbol de manera que solo haya un punto de toque en la esfera y la hoja se mantenga plana. Si vemos desde arriba lo que se observará es un nivel alto de detalle de la tierra en el punto donde se da el toque entre ambos objetos, pero que se ira deformando conforme nos alejemos a los bordes. Esto es básicamente una proyección planar. Se consigue asignando un plano de observación sobre la esfera que tenga un punto de orientación principal. Esto generará una proyección en donde el mayor nivel de detalle se encuentra en el punto y en las áreas más cercanas, deformandose conforme nos vamos alejando del punto focal.
+ **Proyección cónica**: se utiliza la figura de un cono para establcer la proyección. Básicamente consiste en ingresar la tierra dentro de un cono. Hay múltiples zonas de toque entre ambas formas. Esto es útil para establecer proyecciones en latitutes altas del mundo (los polos y zonas aledañas). El detalle se hace mayor conforme nos acercamos al vértice del cono y va deformandose si nos vamos acercando a su base.
+ **Proyección cilíndrica**: las proyecciones cilíndricas consisten en utilizar un cilindro e ingresar la esfera dentro de forma que quede suspendida en la mitad. Esta proyección es la más común y conocida. Esta guarda mucho nivel de detalle en la zona ecuatorial del mundo pero tiene deformaciones conforme nos acercamos a los polos. Es la misma proyección que podemos observar en la página [The True Size](https://thetruesize.com/). Esta proyección así mismo es la que se utiliza en el sistema UTM (Universal Transversal Mercator).

<p align="center">
  <img src = "https://github.com/user-attachments/assets/cb3ff661-012c-4e47-a118-bfc45eeca0a1" alt="Proyección">

## Coordenadas proyectadas

Las coordenadas proyectadas surgen de interaccionar todo lo que hemos visto hasta el momento. Una coordenada proyectada se basa inicialmente en una sistema de coordenadas geográfica al que se le asigna una proyección. Lo que permite establecer una nueva representacion de la tierra trabajada para tener una mejor resolución de la zona de interés. Existen múltiples tipos de coordendas proyectadas, para este curso tomaremos especial énfasis en las coodenadas UTM ya que corresponden al estandar general de trabajos de ingeniería del Perú.

### Sistema de coordendas UTM 

El sistema de coordendas UTM se basa en el elipsoide y datum WGS84 y desarrolla una proyección cilíndrica de la zona. Recuerdemos que el datum WGS84 hace referencia a las coordenadas geográficas.

Resultado de esta interacción se forman 60 zonas cuya longitud es 6° dentro del elipse de referencia. La unidad con la que se trabajan estos datos ya no son grados sino en su lugar son metros, este cambio de unidades es gracias a la proyección que ejecutamos, recuerden que al ejecutar una proyeccion estamos aplanando la esfera en una zona que es la que nos interesa. Estas zonas tienen una division marcada en el ecuador existiendo unas zonas norte y una sur.

Así mismo, se caracteriza por que las coordendas latitud y longitud cambian a coordenada Norte/Sur (mN o mS) y coordenada Este (mE) respectivamente. También desaparecen los paralelos y meridianos de referencia. 

Este sistema de coordenadas trae mucho detalle a la zona de trabajo seleccionada pero se deforma el resto del mundo por lo que antes de configurar o cambiar las coordenadas de un área geográfica seria bueno primero analizar en que zona se encuentra ubicada.

<p align="center">
  <img src = "https://github.com/user-attachments/assets/55460673-0dd2-4c0f-8392-7f7a1292ec56" alt="UTM" width=1200>

## ¿Qué es escala de trabajo?

El último concepto que abordaremos es la escala. La escala es una forma de representar nuestro mundo en un espacio pequeño. El mundo real se ve en una escala de 1:1 es decir que todo guarda el tamaño que realmente tiene. Si por alguna razon todo se encogiera a la mitad con excepcion de la persona que esta leyendo esto la escala en la que vivirías sería 1:2 y si se siguiera encogiendo, el número iria aumentado. En este escenario, cada vez que la escala se haga más grande la persona seria capaz cada ver más zonas.
De este ejemplo se resaltan dos cosas.
1. Cuando el número se hace más grande el área se hace cada vez más pequeña
2. Mientras más pequeña el área más elementos del mundo somos capacez de observar.

<p align="center">
  <img src="https://github.com/user-attachments/assets/45ef8092-b7aa-44d6-bca4-26324cc3e5c1" alt="escalas">

En la imagen pueden ver la misma zona pero en diferentes escalas y al igual que en nuestro ejemplo mientras más grande se hace el número podemos observar cada vez más detalles de la ciudad. Este elemento hay que tenerlo siempre presente por que nos permitirá establecer un tamaño tanto de impresión como de detalle del mapa que querramos crear. 
Asi pues para representar una casa no se usaran escalas muy grandes y para representar una ciudad no se usaran escalas pequeñas.

# Introducción al GIS con Qgis 

Habiendo definido todo lo anterior estamos listos para iniciar con el manejo de la plataforma QGIS. Empezaremos analizando su interfaz el sistema de instalación y luego crearemos nuestro primer mapa.

## Instalación de Qgis

* Ingresa a la siguiente página https://qgis.org/download/
* Dar clic a <img src="https://github.com/user-attachments/assets/ff91cc12-de8b-4d13-b86a-671c0a557bb7" alt="ELIPSOIDE" width=250> y hacemos click a Long Term Version
* Al finalizar la descarga ejecutamos el programa. 

## Interfaz de trabajo en Qgis

La interfaz de Qgis se analiza en base a paneles que pueden ubicarse a los costados y barras que se ubican en la parte superior por defecto. Más adelante veremos que todo ello se puede modificar. 

+ Barra Configuración: Aquí tendremos una serie de menús que nos permitiran modificar, operar y analizar una serie de elementos que vayamos generando y creando. Más adelante pondremos énfasis en una de estas opciones.
+ Barra de Utilidades: En la barra de utilidades encontraremos íconos que nos permiten ejecutar acciones dentro del visor. Cada complemento adicional que instalemos nos dará una nueva barra de utilidades.
+ Menú de capas: Aquí apareceran todos los elementos que ingresemos al Mapa al igual que el Gogle Erath Pro. Exploraremos sobre la creación de entidades y formatos de trabajo. 
+ Visor Principal: Es el analogo al visor de Google Earth Pro sin embargo este esta en blanco, con forme vayamois subiendo capas apareceran cada vez mas elementos.
+ Caja de herramientas: La caja de herramientas es parte del panel lateral este panel lateral puede ser adaptado modificado o eliminado de acuerdo a las configuraciones individuales de cada uno de ustedes. La caja de herramientas no da todas las opciones de procesamiento que nos ofrece el programa, las multiples herramientas que tenemos aqui nos van a permitir hacer una serie de trabajos y obtener mas informacion de los terrenos bajo análisis.
+ Navegador: El navegar es un elemtno que nos permite visualizar las carpetas que creamos. Es importante mantener el orden asi que procuren crear una carpeta por cara proyecto que tengan activo, asi mismo ordenar todos sus archivos para no tener ningun inconveniente luego.

<p align="center">
  <img src="https://github.com/user-attachments/assets/0dc22040-6b64-4513-9db1-acb0e41adc88" alt="ELIPSOIDE" width=1000>

____________________________________________________________________________________________________________________________________________

## Actividad N°1 Configuración Inicial del Programa

### Creación de carpetas
1. Debemos verificar que el panel de Navegación esta activo. Para ello haremos clic en cualquiera de los lugares en blanco en las barras de utilidad y hacemos clic derecho, deberá salir una ventana con múltiples opciones en las que debemos fijarnos que la opción  ![image](https://github.com/user-attachments/assets/972e8261-a218-4ee2-a3f0-658f42540769) este activa como en la imagen.

<p align="center">
  <img src="https://github.com/user-attachments/assets/b2346583-5ba5-41ef-a545-4bd3afec83c1">

2. Nos dirigimos al panel de Navegación y reconocemos que aparecen una serie de iconos con multiples elementos.
   
<p align="center">
  <img src="https://github.com/user-attachments/assets/613bfdb9-cd2a-4511-9f1a-5560842dc051">

En el panel se distinguen dos zonas, la primera es de carpetas, aquí crearemos nuestra carpeta de trabajo y la segunda es una ventana con datos. Todo lo que observamos son los datos y tipos de archivos que puede leer el Qgis. Estas van desde servidores, formatos complejos de empaquetamiento de datos y mapas base descargados, entre otros. Aquí tenemos que ubicar la opción favoritos y darle clic derecho la única opción que saldrá es "Añadir un directorio..." y debemos dar clic a esa opción.

<p align="center">
  <img src="https://github.com/user-attachments/assets/0b140b73-cc94-4cd8-b600-1688cc599dda">

 3. Al hacer clic nos saldrá una ventana estilo buscador en donde debemos colocar una carpeta. Dentro del disco C crearemos una nueva carpeta que se llame "clases_sig" y dentro de ella la carpeta que se llame "Primera_clase" seleccionaremos esta última carpeta. Si todo salio bien la carpeta deberá aparecer como una opción debajo de Favoritos, como se puede ver en la imagen.

<p align="center">
  <img src="https://github.com/user-attachments/assets/62ebee17-256f-4d99-a102-806f9d8c2e45">

### Instalacióin de complementos (Complemento QuickMapServices)
1. Nos dirigiremos a la barra de configuración y ubicamos la opción Complementos, al hacer clic saldrán dos opciones, haremos clic en la primera "Administrar e instalar complementos..."

<p align="center">
  <img src="https://github.com/user-attachments/assets/ce7f47c4-a035-4ba3-bb82-b5c9b22bee01">

2. Esto nos aperturará una nueva ventana. Los complementos son como aplicaciones de celular que nos permiten tener más opciones y desbloquear más funcionalidades. En la ventana que nos salió hay 5 opciones a la izquierda:
   + Todos: Nos muestran todos los complementos que estan disponibles para descargar e incluye los que ya tenga instalados en mi computadora. 
   + Instalado: Me muestra solo los complementos instalados en mi computadora.
   + No instalado: Nos muestra los componentes que estan por instalar en mi computadora.
   + Instalar a partir de ZIP: Es una opción que me permite instalar complementos en versiones antiguas. Tener cuidado de donde se descargan los archivos ya que pueden instalar virus.
   + Configuración: Opciones de configuración de los complementos.

   Nos dirigiremos a la ventana de todos y aparecerá un buscador, allí colocar "QuickMapServices", ubicamos el complemento con el mismo nombre y le damos clic. 

3. En esta nueva ventana haremos clic en instalar complemento y dejamos que se instale.
   
<p align="center">
  <img src="https://github.com/user-attachments/assets/10ac69cb-5fd2-4c26-9d51-69a2d29fa868">

4. Finalizada la descarga deberemos activar el complemento. Para ello regresaremos a la barra de configuración y ubicaremos la opción de "Web" allí encontraran la opción QuickMapServices, debemos desplegar sus opciones y ubicaremos la opción de configuración (Settings) y haremos clic allí.

 <p align="center">
  <img src="https://github.com/user-attachments/assets/d21d26c0-4d8c-4ade-9ee5-5f950f0161b0">

5. Se abrirá una nueva ventana y deberemos ubicar la opción More services y finalmente hacer clic en Get contributed pack. Esto se debe repetir en cada máquina en la que instalemos el complemento.

<p align="center">
  <img src="https://github.com/user-attachments/assets/2af95780-a9cb-4a4e-bbfd-9ae79d811f8c">

6. Una vez hecho ello, regresaremos a la barra de configuración en el menú web y desplegaremos nuevamente la opción QuickMapServices allí veremos que hay múltiples opciones de mapas desde Google hasta OpenStreetMaps, esto se conoce como mapa base y permitirá que visualicemos vistas satelitales al igual que en Google Earth Pro. Para este ejercicio haremos clic en google y seleccionaremos la opción Google Hybrid, eso nos generará un mapa satelital que se mostrará en el panel de Capas. Les invitamos a que exploren el resto de los mapas base que trae este complemento.

<p align="center">
  <img src="https://github.com/user-attachments/assets/2b1dd1c9-7f99-4ccb-92d9-17fae399ea77">

____________________________________________________________________________________________________________________________________________

## Formatos compatibles con Qgis
Existen múltiples datos que son compatibles con Qgis que incluye información recolectada desde fuentes como drones, gps, fotos aéreas, interpolados de malla, etc. 
En esta etapa analizaremos dos de ellas, los formatos vectoriales analizados bajo el formato tradicional Shape (.shp) y los formatos rasterizados que corresponden principalmente a imágenes en múltiples formatos aunque nos concentraremos en el formato TIFF (.tiff)

Formatos Vectoriales: Los formatos vectoriales nos permiten generar límites en la información, la cual es importante para, por ejemplo, analizar terrenos o predios privados. Este tipo de información se conoce como información discreta caracterizada por la presencia de un límite. En ese sentido, las entidades geográficas que hemos aprendido a crear hasta el momento son todas como información discreta y por lo tanto información vectorial.

Formato Rasterizado: Los datos raster son datos que no presentan límites definidos en ninguna de sus categorías. A este tipo de datos se les conoce como datos continuos. La característica principal de este tipo de datos es la composición en forma de píxeles, tal cual como una imagen del celular o de un televisor.  

<p align="center">
  <img src="https://github.com/user-attachments/assets/f509758a-4584-4c03-8fa6-8f21cd2bba0d">

Fuente: https://volaya.github.io/libro-sig/chapters/Tipos_datos.html


## Actividad N°2 Descarga y selección de datos de trabajo

En esta actividad descargaremos información de tipo vectorial y la trabajaremos para seleccionar algunas zonas sobre las que desarrollaremos un mapa. 

### Descarga de datos
1. Ingresar a la página https://www.geogpsperu.com/ esta página es de una empresa que se encarga de sistematizar la información de múltiples bases de datos y dejarla disponible para descargar
2. En los menús de la derecha, desplegar la página hasta que ubiquen un link que diga límite distrital y hacer clic allí

<p align="center">
  <img src="https://github.com/user-attachments/assets/aaa8e234-d29e-482c-b2ae-3d8ac670f3aa">

3. Ubicar la opción de INEI censo de 2023 límite departamental y hacer clic en el link anexo a la base de datos. Los llevará a un drive de google para descargar toda la carpeta como comprimido.
   
4. Descomprimir el archivo en la carpeta de trabajo creada en el ejercicio anterior.

### Subida de datos
1. Si han descomprimido la carpeta correctamente encontrarán múltiples elementos. Todos juntos hacen un solo formato shape si alguno llegara a faltar se perdería información o de plano ya no sería interpretable. Es por ello que descargamos el comprimido en lugar de archivos independientes.
   
2. En el panel de Navegador, nos dirigimos a la carpeta que hemos creado y la abrimos haciendo clic en la flecha del costado. Deberá aparecer la carpeta en donde descomprimimos y al abrirla encontraremos un elemento parecido al siguiente
![image](https://github.com/user-attachments/assets/5464c246-9167-41d0-847e-4998a3cb7eff).

Este archivo es un archivo shp. Notaran que de todos los archivos solo me aparece uno, es por que todos colaboran estre si para dar orígen al formato final.

3. Si hacemos doble clic el elemento que aparece podremos obtener la capa en un color aleatorio. No se preocupen si el color que les sale a su computadora es diferente al que encontramos en la imagen adjunta, las siguientes clases analizaremos como cambiar los colores.

<p align="center">
  <img src="https://github.com/user-attachments/assets/d30f3ce6-45ed-492a-a55e-e10206e04a7e">
 
#### Selección de datos

1. Utilizaremos la barra de selección en la barra de utilidades. ![image](https://github.com/user-attachments/assets/1a3398ae-3b61-44fc-b483-cc3b3c14a52f)

2. En caso la tengan desabilitada, hay que aperturarla siguiendo el mismo procedimiento como habilitamos el Navegador en el ejercicio 1. El nombre que deberán confirmar que este activo es: "Barra de Herramientas de Selección".
   
3. En el menú selección ubicaremos la siguiente opción ![image](https://github.com/user-attachments/assets/6d24b8b8-64c7-4747-a594-88655ca68a7d) Desplieguen la flecha del costado haciendo clic en la flecha apuntando hacia abajo y tendremos múltiples opciones, todas ellas nos permiten seleccionar de distintas formas pero siempre utilizando el cursor y el mouse. 

<p align="center">
  <img src="https://github.com/user-attachments/assets/36241240-eb4a-4dff-b4da-38655126e3d7">

* Seleccionar objeto(s) espacial(es) ![Captura de pantalla 2025-03-25 163628](https://github.com/user-attachments/assets/f00dc9fb-5b71-4a82-b41d-f7d911c3569d) Esto nos permite seleccionar elementos a través de un cuadrado que se genera cuando hago clic y desplacemos el mouse.
 
* Seleccionar objetos espaciales por poligonos ![Captura de pantalla 2025-03-25 163822](https://github.com/user-attachments/assets/8134539f-5bc5-4d41-9b96-ca3437850f85) Permite desarrollar selecciones a través de generar un polígono. Quedará seleccionado todo lo que quede dentro o tocando el polígono que creamos. Cualquier selección se marcará en color amarillo.

* Seleccionar objetos a mano alzada ![Captura de pantalla 2025-03-25 164201](https://github.com/user-attachments/assets/e87ea2a5-2cad-4077-9d5c-0a93def90e00) Esta opción nos permite generar un polígono de selección pero en comparación con el anterior, se desarrolla como si fuera un trazo de lápiz de forma libre así que no hay límites rectos. 

* Seleccionar objetos espaciales por radio  ![Captura de pantalla 2025-03-25 164534](https://github.com/user-attachments/assets/93d83942-adcf-4436-bc1f-07a3163695df)  Esta opción permite generar un círculo de selección, este se forma en dos etapas la primera es seleccionando un punto central y luego desplazar el mouse generando un área circular de selección. Se puede establecer el radio definido en metros en incluyendo un número en el recuadro de radio. 

### Selección por objeto de valor

La seleción por objeto de valor nos va a permitir utilizar los datos de las tablas de atributos de cualquier elemento para seleccionar cosas de forma simple y muy direccionada.
para obtener este elementos ubicaremos dentro del menú de selección el siguiente ícono ![image](https://github.com/user-attachments/assets/8bc3461d-cca7-4ee7-a160-94c211008418) al hacer un clic se desplegara un nuevo menu que contendra la informacion de los campos de la tabla de atributos.

**IMPORTANTE**: Un campo es una columna dentro de la tabla de atributos. 

Si trabajamos con la capa de limites departamentales debera salir un recuadro como el siguiente 

![image](https://github.com/user-attachments/assets/571eb009-ddc0-4dd5-a878-ac2678ce8fe0)

Fijense que el nombre de los elementos en el recuadro son los mismos a cabezales de las tablas de atributos 

![Captura de pantalla 2025-04-02 173531](https://github.com/user-attachments/assets/9ae8f70c-008a-46b9-b169-f062b8f086fc)

Para utilizar este elemento tenemos que buscar el nombre de lo que estmaos bucando y el campo de trabajo y dar clic en aceptar


___________________________________________________________________________________________
# Asignación

1. Descargar de la base de datos GEOGPS los límites provinciales y distritales
2. Escoger 2 departamentos y con ayuda de las herramientas de selección de Qgis aislar todas las provincias de los dos departamentos y presentarlas en capturas individuales.
3. Escoger 3 provincias y con la herramienta seleccionar de Qgis aislar todos los distritos usando la base de datos de limites provinciales presentarlas en el informe como     capturas.
   
## Formato de presentación del informe
Para esta tarea la presentación del informe sera cumpliendo con los siguientes apartados.

1. Objetivos
2. Marco teórico
3. Metodología
4. Resultados
5. Discusion
6. Conclusiones
7. Bibliografia (formato APA)

Cada item se evaluara en un puntaje de acuerdo con la siguiente tabla

<p align="center">
  <img src="https://github.com/user-attachments/assets/abb8fb0d-faef-4c23-a5a4-bbb9a552fe77" alt="ELIPSOIDE"> 

