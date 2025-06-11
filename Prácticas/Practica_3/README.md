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
  <img src="https://github.com/user-attachments/assets/31bb21e5-6a59-474c-8942-eec4fde14005" alt="aplicacion de zonas UTM" width=500>
</p>

5. Una vez selecionada la coordenada verificamos como en la zona de previsualización cambiará mostrando la zona de interés dentro de una zona roja. Verificamos que corresponda a la zona 19S y damos clic en aceptar con ello el Qgis esta configurado a este nuevo sistema de coordendas.
   
<p align="center">
  <img src="https://github.com/user-attachments/assets/4b49efec-ed79-43da-a9a2-4842448649e2" alt="aplicacion de zonas UTM" width=500>
</p>

_________________________________________________________________________________________________________________________________________________________________________________

# Cartografía y representacion de elementos en mapas

La cartografia es una actividad que consiste en la digitalización de los elementos que nosotros podemos observar desde un mapa base, algun mapa georreferenciado o coordenadas de la via real. Normalmente se utiliza para describir de mejor medida un lugar y poder obtenerdatos que de otra forma no seria posible. Un ejemplo de un tipo de cartografia correponden a los mapas catastrales de ciudades en donde cada una de las cuadras o lotes se transforman. 

![image](https://github.com/user-attachments/assets/e7a86321-d85f-4bbf-b4ee-f3720e3449ba)
Cartografía catastral

## Diferencia entre datos Raster y Vectores

Hay dos grupos de datos muy utilizados para aplicaciones en GIS y estos son los datos de tipo Raster y Vector. Cada uno de ellos tiene su popia utilidad definida con esto quiero decir que ninguno es mejor que otro sino que sus funciones son diferentes. 

* Los datos de tipo **RASTER** son datos continuos y no presentan límites fisicos concretos. Normalmente estan estructurados a trabes de una malla de datos lo que comunmente conocemos como pixeles. Los rasteer normalmente se trabajan en formato TIFF, GeoTIFF, ASCII, JPEG, etc. Como habran podido ver algunos de estos formatos son los mismos para fotografias. Y es común utilizar raster al hacer analisis usando algunos tipos de imágenes satelitales. 

* Los datos de tipo **VECTOR** son datos en donde se demuestra un límite difinido. Es decir existe una linea fisica de separa un elemento del otro. Estos datos son muy utilies para representar informacion discreta es decir que los limites nos indican algo. Por ejemplo una casa, una carretera, un rio, etc. A veces se utiliza informacion de tipo raster y se vuelve en vector para organizar mejor los datos y al mismo tiempo tener limites entre las cosas que observamos en una imagen Raster. Tal como se muestra en la imagen anexa. 

![raster_vector](https://github.com/user-attachments/assets/0ec22f03-8a4c-41c8-9c53-e05c7329a04d)
Diferencia entre elementos raster y vector

## Creación de elementos vectoriales

Los elementos vectoriales como vimos previamente se caracterizan por establcer limites deifinos en las elemtnos que dibujamos dentro de cada capa. En este sentido es facil reconocer su ubicación puntual, el area que comprenden o los transector o caminos que se recorre en cada geometria. Para aplicaciones donde los limites son importantes este tipo de cartografía es crucial. Algunos de los usos más representativos de este tipo de archivos se encuetra en los levantamientos catastrales de ciudades, en limites de areas naturales protegidas, delimitaciones de áreas agrícolas, ubicacion de puntos de muestreo, discriminacion de carreteras o rios.

Existen principalmente 3 tipos de elementos vectoriales que se diferencian entre sí por su uso. Sin embargo estos no son exclueyentes por lo que un mismo objeto en la realidad puede tener multiples formas de representación. Es decir, podemos utilizar tanto poligonos, puntos o lineas para representar un mismo lugar. A continuación se describen los principales usos y caracteristicas de cada elemento vectorial.

+ **Puntos**: Se utiliza cuando lo que nos interesa resaltar es la posición especifica de algún lugar o elemento que querramos representar. La información que podemos obtener de una cartografia de tipo puntos son sus coordenadas.
+ **Líneas**: Se utiliza cuando lo que nos interesa reconocer es la distancia que se recorre de un punto a otro. Normalmente se utiliza para elementos lineales como carreteras, rios, rutas, etc. En este tipo de datos podemos calcular su longitud. 
+ **Polígonos**: Se usan cuando se necesita establecer un límite dentro de un objeto que tiene un área definida. La información que se puede obtener de este tipo de cartografias se puede obtener tanto el el área como el perímetro

Existen multiples formatos de guardado y compresion de archivos vectoriales. El que se abordará en esta guia son los archivos shape o .shp. Los datos Shape funciona de forma colectiva lo que quiere decir que se necesitan de algunos archivos adicionales para que puedan ser exportadas o enviadas de un usuario a otro. Esto se abordara a mayor detalle en la actividad N°2. 

![image](https://github.com/user-attachments/assets/415edeab-7ce6-4d9c-b51b-d12064c8d589)

______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

### Actividad N°2: Creación de capas vectoriales tipo shape

1. Crearemos una nueva carpeta en nuestro buscador con el nombre de "Elementos_vectoriales" y procederemos a aperturar el Qgis
2. Para crear capas vectoriales dentro de Qgis debemos hacer clic en nueva capa de archivo shape ![image](https://github.com/user-attachments/assets/610030b9-345f-472a-b640-4d1bb9787e6d) que se encuentra ubicado en la barra de herramientas.
3. Esto habilitará una nueva ventana que cuenta con tres zonas de configuración. 

+ **Zona de configuración general de nueva capa**: Aqui podremos ubicar un nombre y un lugar de guardado haciendo clic en este icono ![image](https://github.com/user-attachments/assets/67ac6630-49d9-4e9f-9671-b90c3e2037f0) se aperturará un buscador y alli podremos incluir la carpeta de destino donde queremos que se guarde nuestra nueva capa. La segunda opción corresponde a la codificación en donde se encuentra por defecto de encriptación de la capa. En la mayoria de los casos la codificación deberia salir UTF-8. Si esto no se diera puede quedarse por defecto con el que se encuentre. La diferencia que se encuentra en que tipos de caracteres se puden escribir. Es decir es como el tipo de letra en un word. En tipo de geometría se puede establecer la geometría al que queremos configurar para nuestra capa. Existen cuadro opciones (puntos, líneas, poligonos y multipunto) se abordará cada una más adelante. Como siguiente opción de configuracion se tiene la herramientas dimensiones adicionales, aquí podemos establecer valores como alturas, etc en caso querramos configurar una capa 3D.Y finalmente en el recuadro inferior se encuentra el sistema de coordenadas este debe configurarse cada vez que se cree una nueva capa debido a que tendrá su propio sistema de coordenadas que puede ser el mismo o diferente al que configuramos anteriormente en el Qgis.
+ **Zona de configuración de tabla de atributos**: Aqui podremos crear los campos de recolección de datos para las capas. Esta información es el nucleo principal de cualquier capa. Por que nos permiten representar datos relevantes teniendo en cuenta un segmento espacial. La tabla de atributos asemeja un libro de excel pero tiene sus particularidades. Se abordará en la siguiente práctica la importancia de un manejo correcto de una tabla de atributos. Pero es importante reconocer a este punto que una capa no es solamente un dibujo sino que viene anexa con informacion que mas adelante utilizaremos para obtener productos o nuevos análisis. 
+ **Previsualización de nuevos campos**: Aqui se visualizan el nombre y la forma de codificación de cada uno de los campos que creemos, la logitud en caracteres que puede entrar en cada celda y en algunos casos los decimales (precisión) que haya para cada campo. 

![edicion_capas](https://github.com/user-attachments/assets/641cd129-f1c4-4f49-a2b7-8d1ce6b1c7be)

4. Crearemos tres capas una para puntos y se debera repetir el ejercicio para poligonos y lineas (lo unico que debera cambiar es el tipo de geometria)

   * En nombre de archivo ubicaremos la carpeta que creamos en el punto 1, y asignaremos un nombre de acuerdo a la cartografia que deseamos es decir como haremos una capa de puntos tendremos que asignarle el nombre de puntos, a la etapa de líneas se le asignan líneas y a polígonos se le pondrá polígonos
   * En codificación del archivo intentaremos que se mantenga en UTF-8
   * Para tipo de archivo desplegaremos la lista y asignaremos el valor de punto tener en cuenta que hay dos tipos multipuntos y punto para este ejercicio solamente nos concentraremos en el valor de punto
   * Tenemos que asegurarnos que las coordenadas de trabajo estén configuradas en 19S por lo tanto modificar modificar las coordenadas de acuerdo a lo visto en la actividad N°1.
   * De momento no se asignará ningún valor para la tabla de atributos con esto hemos finalizado la modificación de datos simplemente darle a aceptar.

Se debera repetir estos pasos para las capas de poligosnos y lineas recodar que solo se esta cambiando el tipo de dato el resto de valores, para este ejercicio, quedan iguales. Sin embargo, tener cuidado con las coordenadas de trabajo. 

5. Al momento en que le damos aceptar se genera una nueva A capa en el menú de capas de Cullis el resultado luego de haber creado las 3 capas Deberá hacer algo parecido a esto

 ![image](https://github.com/user-attachments/assets/ed7b1991-2bbe-4492-870c-7018a4d234a8)

Si los colores de los iconos de cada capa son diferentes a los mostrados en la imagen no se preocupen, estos se asignan de forma aleatoria por lo tanto es poco probable que tengan exactamente los mismos que se muestran en el ejemplo. 

6. Verificaremos si los parametros de las capas haciendo clic derecho sobre alguna de ellas dirigiendonos al menu propiedades

![image](https://github.com/user-attachments/assets/7a24deda-613e-49e5-b5ba-a2e62884a3c4)
  
7. Esto aperturará una nueva ventana con multiples opciones nos diriremos a la que dice informacion y verificaremos que el sistema de coordenadas este configurado en 19s. 

![Captura de pantalla 2025-06-11 141822](https://github.com/user-attachments/assets/2995ebc9-59d2-4f5f-9d92-90e0bf428e11)

8. Dentro de esta misma ventana encontraremos un hipevinculo en la subdivicion que dice general. Si hacemos clic nos llevara a la carpeta donde hemos guardado nuestra capa.  Notaremos que al ingresar se encontraran multiples archivos con el todos estos archivos componene una capa si se quisiera expotar se tendría que comprimir todos los archivos y enviarlos debidoa que si llegara a faltar alguno la capa no se podria aperturar. Estos son los archivos sidecar.
   
![Captura de pantalla 2025-06-11 141822](https://github.com/user-attachments/assets/bd3a1a33-b8bf-4142-9d36-558b3fca5414)

______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

### Actividad N°3: Creacion de elementos dentro de las capas vectoriales







