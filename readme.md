<h1>Taller - Elaboración de mapas con CartoDB<h1> 

<p>Enlaces e información complementaria recopilados para el taller sobre elaboración de mapas interactivos del grupo de Periodismo de Datos MediaLab Prado (feb. 2013, http://medialab-prado.es/article/periodismo_datos_mapas_interactivos).<p>

<p>Los archivos incluidos (index.html, CSS) contienen los elementos necesarios para publicar un mapa elaborado con CartoDB en una plantilla de información (pc, iPad y móvil compatible). Plantilla elaborada por <a href="https://twitter.com/saleiva">@saleiva</a>. </p>

<p>Más plantillas de CartoDB: https://github.com/CartoDB/cartodb-publishing-templates</p>


<h3>Taller</h3>
<p>El primer ejercicio del taller es una introducción al periodismo de datos con mapas. Se muestra cómo recopilar datos, importarlos a CartoDB y combinar varias tablas para la elaboración de un mapa dinámico del paro en España.</p>

<p>- Los datos de las provincias españolas están disponibles en:</p> 
<p>http://2read.cartodb.com/tables/spain_provinces/public/</p>

<p>- Datos del paro (4º trimestre de 2012):</p> 
<p>http://2read.cartodb.com/tables/paro_spain_2012iv/public/</p>

<p>La primera tabla contiene la información geográfica sobre las provincias de España en un archivo shapefile comprimido. Para importarla, sólo es necesario arrastrar el archivo .zip (sin descomprimir) al panel de usuario de CartoDB. El archivo con los datos del paro se importa de la misma forma. </p>
<p>Para unir las dos tablas, y poder elaborar un mapa de <a href="http://www.ncgia.ucsb.edu/cctp/units/unit47/html/mas_form.html">cloropetas</a>, utilizamos la función "merge tables". Desde la tabla con la información geográfica, elegimos la tabla y la información que queremos combinar y seleccionamos la columna que utilizaremos como referencia. Es necesario que estas columnas sean idénticas para que no se produzcan errores en la combinación de la información (incluidas tildes u otros signos ortográficos). Asignamos un nombre a la nueva tabla.</p>  

![Alt text](img/1.png "merge tables")

<p>Más información:</p>
- [CartoDB tour](http://cartodb.com/tour)
- [Getting started with CartoDB](http://developers.cartodb.com/documentation/using-cartodb.html)
- [CartoCSS reference](http://mapbox.com/carto/api/2.1.0/)


<h3>Edición</h3>
<p>Los datos que queremos representar están en la columna "paro_2012iv". Con frecuencia, como ocurre en este caso, es necesario transformar la columna de "string" a "numbers" para poder utilizarla como referencia.</p>

![Alt text](img/2.png "edit columns")

<p>En la vista de "map view", elegimos el mapa de base y editamos el estilo a través del menú "visualization wizard". La segunda opción calcula los intervalos según los datos que se quieren representar y permite elaborar de forma automática un mapa de cloropetas. </p>

![Alt text](img/3.png "visualization wizard")

<p>El mapa se puede publicar a través de la función "share". </p>


<h3>Edición avanzada</h3>
<p>Utilizamos la siguiente tabla:</p> 
<p>http://2read.cartodb.com/tables/madrid_mercados_puntos/public/</p>

<p>La tabla incluye los datos de tres archivos con registros de mercados, galerías de alimentación e hipermercados en Madrid. Los he unido utilizando esta función a través del menú SQL: </p> 
<code>SELECT 'abastos' as new_table, the_geom, denominaci, direccion FROM abastos<br>UNION SELECT 'galerias' as new_table, the_geom, direccion, nombre from galimenta<br>UNION SELECT 'hipermercados' as new_table, the_geom, direccion, eti FROM hipermercados</code>

<h4>Añadimos una imagen al infowindow</h4>
<p>Creamos una columna nueva y pegamos la url de la imagen que queremos utilizar. En el menú de "infowindow", seleccionamos el estilo "image header" y arrastramos al primer lugar la columna con la información de la imagen. </p>

![Alt text](img/4.png "image infowindow cartocss")

<h4>Edición del cógido CartoCSS</h4>
<p>Editamos manualmente el código para diferenciar los puntos de la tabla según la etiqueta que tengan: "abastos", "galerías", "hipermercados".
<p>Código CartoCSS: https://gist.github.com/cmdelaserna/1b44e2be33b176422d20</p>
<p>Mapa: http://cdb.io/Wza1lw</p>

<h4>Cómo crear un polígono y representar su altura</h4>
<p>La función "add feature", disponible en la vista de "map view", permite pintar un polígono, un punto o una línea sobre el mapa. Para este ejercicio creamos un polígono. En la vista de tabla vemos que se ha añadido un registro que contiene la geometría del polígono. Añadimos un campo que sea "height", e indicamos un valor. Para representar la altura del edificio según este valor, añadimos al CartoCSS: 
<code>building-height:[altura]</code>
![Alt text](img/6.png "building-height cartocss")

<h4>Elaboración de un mapa de intensidad</h4>
<p>Editamos el código CartoCSS para definir un mapa de intensidad de mercados y puntos de venta de alimentos en Madrid.</p>
<p>Código CartoCSS: https://gist.github.com/cmdelaserna/4726629</p>
<p>Mapa de mercados y galerías de alimentación en Madrid: http://cdb.io/VGx3Ko</p>
![Alt text](img/5.png "intensity map")

<h4>Cómo importar datos de OpenStreetMap</h4>
<p>http://www.slideshare.net/andrewxhill/using-cartodb-to-analyze-openstreetmap-data</p>
