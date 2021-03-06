# Análisis de la primera visualización de datos realizada con Datawrapper

![cantidad de veces que se desea un feliz viernes en Twitter](/trabajos/images/datawrapper2.png)

## Procedimiento

1- Se clonan los datos del archivo "feliz.csv" a través del comando git clone en la terminal


2- Utilizamos el Open Refine para manipular el archivo y limpiarlo, elaborando un nuevo conjunto que permita la elaboración de un gráfico en Datawrapper

2.1- Abrimos Open Refine y escogemos el archivo "feliz.csv" para crear un nuevo proyecto

2.2- Indicar que, en este caso, las comas del archivo sirven para indicar las distintas columnas y sus datos

2.3- Se escribe el nombre de las columnas separando cada uno de estos términos con comas, de esta forma: "borrar, fecha, tendencia, enlace, borrar 2, cantidad"

2.4- Evitamos que las comillas (") se utilicen para incluir celdas que contengan separadores de columna. Esto se hace quitando la selección que, en un principio, aparecera como para ejecutarse

2.5- Finalmente, creamos el proyecto, que se quedará con un total de 5981 filas y 6 columnas

2.6- Hay que eliminar todas las columnas "borrar" y "borrar 2", nos quedamos con 4

2.7- Se da formato de fecha a la columna "fecha", de número a la columna "Cantidad" y de texto al resto

2.8- Con una faceta de línea temporal en la columna fechas, se eliminan los datos de 1970 con la función "star rows" y luego "remove matching rows"

2.9- Con la función "Cluster", se renombran las celdas de la columna "fecha" para que solo indiquen el mes y el año

2.10- Para reducir la muestra de datos (al ser el primer gráfico se pretendía usar datawrapper con una cantidad reducida) se eliminan también los datos del año 2021 con el mismo método de "star rows" y "remove matching rows", ayudado además con una faceta de línea temporal 

2.11- Se eliminan los símbolos de almohadilla de la columna "tendencia" mediante una simple transformación de texto o función "replace" en la que se sustituye el valor "#" por "". También se podría haber utilizado la función "cluster", pero era un proceso más lento y con iguales resultados

2.12- Con una faceta de texto en la columna "tendencia", se van eliminando las filas que no estén relacionadas con el tema. En un primer momento las que no tienen el término "feliz", como las que tratan del rey Felipe, luego las que se dirigían al futbolista Joao Félix o en las que ponía la palabra "felis". Posteriormente se eliminan también las de Navidad y todo lo que no se refiera a días de la semana. De esta forma, nos quedan 2019 filas

2.13- Se utiliza de nuevo el cluster para homogeneizar la columna "tendencia" en 7 categorías distintas (una por cada día de la semana)

2.14- Se eliminan todas las filas donde no aparezca un dato numérico en la columna "cantidad" (no pueden servirnos para el gráfico a no ser que les demos un valor de "1" en vez de "0", siendo esta última la decisión que se tomó)

2.15- Aquí se llega a un momento crucial en la elaboración de este primer gráfico, ya que tenemos 7 tendencias distintas, una por cada día de la semana, con una serie de valores numéricos con los que ya se podría elaborar un gráfico con cualquiera de ellas. Como en clase aún no habíamos explicado cómo sumar los valores y agrupar las filas con una misma tendencia, se escogió tomar solo los datos de "FelizViernes" al ver que Datawrapper solo permite hasta 60 filas a la hora de elaborar un gráfico de columnas (el que yo tenía en mente). El motivo fue que esta tendencia era la que contenía el mayor número de filas sin sobrepasar ese límite. Había, por ejemplo, una sola fila relacionada con la tendencia "FelizMiercoles" y 216 con la tendencia "FelizLunes".

2.16- Finalmente, con solo las filas de "FelizViernes" seleccionadas a través de una faceta de texto, se exporta el nuevo archivo en formato CSV, y ya tenemos listo el material definitivo con el que podremos elaborar el gráfico


3- Me gustaría señalar que todos los pasos explicitados en el punto número 2 solo son un resumen de lo que se hizo, evitando mencionar los errores cometidos y sus correcciones posteriores no solo para evitar alargar de más este texto, sino también con el propósito de mostrar el procedimiento más eficaz a la hora de obtener el archivo final y el progreso de mis conocimientos con la herramienta Open Refine


4- Vamos a la página web datawrapper.de y nos creamos una cuenta, si queremos, para tener nuestro propio "Dashboard" donde almacenaremos todos los gráficos y visualizaciones que creemos

4.1- Creamos un nuevo proyecto en datawrapper pulsando en la opción "crear gráfico"

4.2- En el primer apartado donde se cargan los datos, cargamos el archivo creado previamente con Open Refine al que denominamos "felizviernes.csv"

4.3- En el apartado "Verificar y describir", pulsamos sobre todas las columnas para asegurarnos de que datawrapper ha interpretado bien el formato de los datos de cada una de estas (fechas, números, textos, etc)

4.4- También especificamos que la columna de los enlaces no formará parte de la visualización creada

4.5- El último paso en este apartado es que, para que las cantidades sean más comprensibles, se dividirán todas las cifras de la columna "cantidad" entre 1000 y se pondrá una "m" al final de cada número, para dar a entender que el número que se está ofreciendo viene en unidades de mil.

4.6- Pasamos al apartado "Visualizar" y seleccionamos que queremos un gráfico de columnas (ideal para este tipo de conjuntos con valores a lo largo de un periodo de tiempo)

4.7- Se selecciona la opción de que aparezcan las líneas de la cuadrícula y las etiquetas de los ejes, ofreciendo para esto último una serie de referencias personalizadas para que el gráfico se pueda ver mejor (5m ,10m ,15m, 20m, 25m)

4.8- Por otra parte, en el eje horizontal se modifica el formato de las fechas para que aparezca el nombre completo del mes en vez de los números originales

4.9- En el subapartado "Anotar" es donde escribimos el título y la descripción del gráfico, así como su fuente y su autor. Su posición se puede modificar también de forma manual

4.10- En el apartado de diseño no podemos hacer mucho, salvo modificar un poco la tipografía utilizada. También se cambia el color y se pasa a un tono verde oscuro, reduciendo al mínimo el espacio entre columnas (0%)

4.11- Ya solo nos queda publicar y descargar el gráfico en formato png. En mi caso, también se duplicó el gráfico para poder investigar otro tipo de tratamientos con los mismos datos.

## Justificación final

Este gráfico es el primer proyecto que he realizado con Datawrapper, en el que además he tratado en Open Refine una base de datos no recolectados por mí mismo (desconociendo 
en consecuencia su naturaleza y características concretas). Por lo tanto, ya desde un principio se decidió elaborar un gráfico con una cantidad notablemente reducida de 
filas, para lo que iba a ser necesario utilizar las funciones más básicas del Open Refine (las facetas y el cluster, especialmente). Consiste, de este modo, en una 
visualización por columnas de la cantidad de veces que se desea un feliz viernes en el año 2020, entre los meses de marzo y septiembre (no había datos de otros meses en el 
mismo año). Este formato es ideal, en el sentido de que permite comparar las cantidades (representadas en el eje vertical) en distintos momentos de un periodo (estipulados 
en el eje horizontal). Un gráfico de líneas también habría podido servir, pero consideré que este último sirve más para mostrar una evolución en el tiempo, la cual se puede 
explicar posteriormente con una serie de razonamientos, algo que no creí útil en mi caso al no saber los motivos de una diferencia tan notable entre los meses (no creo que 
marzo sea, para nada, el mes con los mejores viernes del año). Aún así, en homenaje a este resultado se ha usado el color verde en el gráfico, para darle un toque más 
"primaveral". Al tratarse de un gráfico con datos poco comunes, el título se hacía complicado, por lo que se ha aplicado un criterio más artístico en el que este solo llame 
la atención y luego, en la descripción justo de debajo, se explique un poco más concienzudamente la naturaleza de la información que se está visualizando, he ahí la 
utilización de elementos gráficos más distendidos como los calendarios. Se agradece que aparezcan del mismo modo el autor y la fuente. Lo segundo es algo que escaseaba en 
muchas infografías que encontré para llevar a cabo prácticas anteriores. También se han utilizado hipervínculos en esta información, situada en la parte inferior de la 
imagen, para que quien quiera pueda acceder a la fuente de los datos y así comprobar que sean correctos (algo que demuestra la honestidad de los mismos), en esta ocasión en 
el perfil de Github de "Pontedatos". Por último, desde un punto de vista negativo, es una pena que no haya datos para más meses, haciendo que el gráfico quede un tanto irregular y, 
sobre todo, incompleto, aunque todo ello se puede atribuir a los datos obtenidos con el archivo "feliz.csv". La excesiva simplicidad también es algo que podría corregirse, al tratarse Datawrapper de una herramienta que, bien entendida y utilizada, permite hacer gráficos más completos. Un ejemplo de cómo se podría haber enriquecido un poco más este trabajo, hubiera sido añadiendo datos, en las mismas fechas y en el mismo formato numérico, de otros días de la semana, para que quedaran varias columnas, obviamente con colores diferentes, en un mismo mes, y así poder comparar si marzo, teniendo "los viernes más felices", también es el mes con "los jueves más felices", o ese honor corresponde a otro mes. La tipografía también es algo mejorable, pero esto no se puede manejar debidamente con datawrapper, sino que habría que hacerlo con otra página web o programa de forma posterior (como Canva).
 


# Análisis de la segunda visualización de datos realizada con Datawrapper

![cantidad de veces que se desea una feliz feliz navidad en los últimos meses de 2020](/trabajos/images/datawrapper1.png)

## Procedimiento 

1- Se clonan los datos del archivo "feliz.csv" a través del comando git clone en la terminal


2- Utilizamos el Open Refine para manipular el archivo y limpiarlo, elaborando un nuevo conjunto que permita la elaboración de un gráfico en Datawrapper

2.1- Abrimos Open Refine y escogemos el archivo "feliz.csv" para crear un nuevo proyecto

2.2- Indicar que, en este caso, las comas del archivo sirven para indicar las distintas columnas y sus datos

2.3- Se escribe el nombre de las columnas separando cada uno de estos términos con comas, de esta forma: "borrar, fecha, tendencia, enlace, borrar 2, cantidad"

2.4- Evitamos que las comillas (") se utilicen para incluir celdas que contengan separadores de columna. Esto se hace quitando la selección que, en un principio, aparecera como para ejecutarse

2.5- Finalmente, creamos el proyecto, que se quedará con un total de 5981 filas y 6 columnas

2.6- Hay que eliminar todas las columnas "borrar" y "borrar 2", nos quedamos con 4

2.7- Se da formato de fecha a la columna "fecha", de número a la columna "Cantidad" y de texto al resto

2.8- Con una faceta de línea temporal en la columna fechas, se eliminan los datos de 1970 con la función "star rows" y luego "remove matching rows"

2.9- Después, en la columna "tendencia" se utiliza un filtro de texto para que aparezcan solo las filas que contengan la palabra "navidad", se utiliza la función invert para que en esta ocasión se vean todas menos estas y se borran.

2.10- Ahora tenemos 136 filas, en las que aplicaremos una faceta de texto para ver cuantas tendencias distintas tenemos: en total 7, de las cuales eliminaremos "PcComponentesFelizNavidad" y "FelizNavidadJordi", ya que no siguen la línea que pretendemos, en un contexto más genérico que el comercial o el exclusivamente personal.

2.11- Borramos todas las filas que no contengan algún valor en la columna "cantidad", con lo que nos quedan 97, y nos encontramos con que muchas de estas responden al mismo día.

2.12- Sumamos todos los valores pertinentes para tener una sola fila por día en la columna fecha, la cual tendra en la columna "cantidad" el valor igual a la suma de todas las filas coetáneas.

2.13- Con el cluster, homogeneizamos la columna "tendencia", ya que en realidad no necesitaremos más de una etiqueta en datawrapper

2.14- Además, quitaremos de las celdas de la columna fecha la parte que hace la referencia a la hora, minutos y segundos. Esto fue algo complejo que se hizo con el cluster, aumentando el ratio de similitud para que fuera capaz de agrupar las celdas según el día.

2.15- De esta forma, nos quedaremos con un total de 23 filas, una por cada día en un periodo que recorre desde finales de octubre de 2020 a finales de diciembre, sin llegar a las fechas navideñas.

2.16- Exportamos el archivo en formato CSV y lo preparamos para datawrapper


3-Al tratarse del segundo proyecto en el que se usa Open Refine, se puede obsrvar una optimización de los pasos que han conllevado un más rápido acondicionamiento de los datos, aunque su cantidad y tipología sea mayor.


4- Vamos a la página web datawrapper.de y nos creamos una cuenta, si queremos, para tener nuestro propio "Dashboard" donde almacenaremos todos los gráficos y visualizaciones que creemos

4.1- Creamos un nuevo proyecto en datawrapper pulsando en la opción "crear gráfico"

4.2- En el primer apartado donde se cargan los datos, cargamos el archivo creado previamente con Open Refine al que denominamos "feliznavidad.csv"

4.3- En el apartado "Verificar y describir", pulsamos sobre todas las columnas para asegurarnos de que datawrapper ha interpretado bien el formato de los datos de cada una de estas (fechas, números, textos, etc)

4.4- También especificamos que la columna de los enlaces no formará parte de la visualización creada

4.5- Seleccionamos en el apartado de "visualización" que queremos elaborar un gráfico de líneas para que nos muestre la evolución en el tiempo de la cantidad que se desea una feliz navidad en Twitter en las fechas establecidas

4.6- También seleccionamos la opción de "rellenar área" para hacer más visible esta evolución, y le damos tanto a la línea como al área un tono rojizo que recuerde al traje de Papa Noel (posterior a la publicidad de Coca Cola, claro está).

4.7- Como las cifras manejadas son más altas que en el gráfico anterior, esta vez dividiremos las cifras directamente en el subapartado de mejorar, donde le daremos un formato que divida todos según la unidad estipulada en las referencias personalizadas, donde especificaremos que nos interesa dividirlo en millones

4.8- Agrandamos el grosor de la línea, reducimos la opacidad del área y establecemos una interpolación de carácter lineal (para que los cambios no se vean como curvas sino como a través de vértices)

4.9- Ponemos título y cambiamos el tema del diseño para que aparezca una tipografía distinta a la utilizada en el gráfico anterior

4.10- También estipulamos que se vea el valor total de la última fecha

4.11- Especificamos el creador y la fuente de los datos

4.12- Publicamos en el dashboard y descargamos en png (antes no lo he mencionado, pero hay que vigilar de no descargarlo en una escala superior a 1 si queremos subirlo a github, porque de ser así la imagen será demasiado grande, en mi opinión).



## Justificación final


En este gráfico hemos procurado resolver algunos de los aspectos a mejorar en el primero, sobre todo en el tema de la simplicidad del gráfico, que esta vez cuenta con unos 
datos ligeramente más complejos de manejar por sus cantidades mayores y la mayor cantidad de fechas que, por lo tanto, apuntaban a un mejor resultado en la visualización a 
partir de un gráfico de líneas. Del mismo modo, también se ha intentado buscar un resultado distinto en el resto de elementos: en el título no hemos puesto una descripción 
justo debajo, al considerar que tan solo con lo que se ha escrito ya se entendía la naturaleza del gráfico. La tipografía es distinta al utilizar uno de los pocos temas en 
el diseño que permite la página de Datawrapper, con una letra menos gruesa pero más elegante, que conjuga, en mi opinión, con la sutileza de un gráfico de líneas que, en el 
caso de haber optado por columnas, hubiera quedado solapada por el grosor de estas. Otra notable diferencia es la escasez de elementos situacionales en el eje horizontal, 
donde solo aparece el nombre de los meses, buscando reforzar ese tono de evolución más fluida, la cual no quedaría tan reforzada si subdividiéramos explícitamente dicho eje. 
Para evitar que quede demasiado "abstracto", hemos seleccionado la opción de las descripciones emergentes, que harán que podamos saber la fecha concreta del punto que 
queramos solo colocando el cursor encima de este. El problema (y el principal pero de este gráfico) es que, al exportarlo en formato png, no se puede comprobar. Queda por lo tanto patente la necesidad de averiguar una forma en la que poder mostrar el gráfico en este archivo de markdown que sí permita esa función.
Aparte de esto, solo me queda decir que por la falta de tiempo no he podido realizar un tercer gráfico con una base de datos distinta a la de feliz.csv, pero me quedo con la 
curiosidad de probar el resultado con conjuntos ofrecidos por la propia página de datawrapper cuando vas a cargar los datos de un determinado archivo CSV. Me ha resultado 
más interesado el programa de Open Refine que el de Datawrapper, puesto que me parece que el potencial de este último es bastante menor en cuanto al aspecto exterior del 
gráfico (no así con la capacidad de datos que puede manejar, aunque es una lástima lo del límite de filas)
