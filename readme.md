<h1>Workshop - Grupo de Periodismo de Datos del Medialab Prado<h1>

<p>Los archivos incluidos en este repositorio (index.html, CSS) contienen todos los elementos necesarios para publicar un mapa elaborado con CartoDB en una plantilla de información. La plantilla ha sido elaborada por [@saleiva](https://github.com/CartoDB/cartodb-publishing-templates). 

<p>Plantillas de CartoDB:</p>
<p>https://github.com/CartoDB/cartodb-publishing-templates</p>

![Alt text](img/5.png "intensity map")



<h3>Workshop</h3>
<p>El primer ejercicio consiste en importar datos a CartoDB y combinarlos en una única tabla para la elaboración de un mapa del paro en España.</p>

<p>Los datos de las provincias españolas están disponibles en:</p> 
<p>http://2read.cartodb.com/tables/spain_provinces/public/</p>

<p>Datos del paro (4º trimestre de 2012):</p> 

<p>http://2read.cartodb.com/tables/paro_spain_2012iv/public/</p>

<p>Para unir las dos tablas, utilizamos la función "merge tables" del panel de CartoDB. Elegimos la tabla que queremos combinar y seleccionamos la columna que utilizaremos como referencia ("provincia" y "provincias") más las que queremos importar. Asignamos un nombre a la nueva tabla.  

![Alt text](img/1.png "merge tables")



<h3>Elaboración del mapa del paro</h3>
<p>Los datos están en la columna "paro_2012iv". Transformamos la columna de "string" a "numbers" (para poder utilizarla como referencia para elaborar el mapa).</p>

![Alt text](img/2.png "edit columns")

<p>En la vista de "map view", elegimos el mapa de base y editamos el estilo del mapa a través del menú "visualization wizard". </p>

![Alt text](img/3.png "visualization wizard")

<p>El mapa se puede publicar a través de la función "share". </p>


<h3>Edición avanzada</h3>
<p>Utilizamos la tabla siguiente:</p> 
<p>http://2read.cartodb.com/tables/madrid_mercados_puntos/public/</p>

<p>La tabla incluye los datos de tres archivos. Los he unido utilizando esta función: </p> 
<code>SELECT 'abastos' as new_table, the_geom, denominaci, direccion FROM abastos<br>UNION SELECT 'galerias' as new_table, the_geom, direccion, nombre from galimenta<br>UNION SELECT 'hipermercados' as new_table, the_geom, direccion, eti FROM hipermercados</code>

<p>Añade una imagen al infowindow</p>

![Alt text](img/4.png "image infowindow cartocss")

<p>Edita los estilos (diferenciar puntos)</p>

<p>Crear un polígono, puntos o líneas + cartocss building-height</p>
![Alt text](img/6.png "building-height cartocss")

<p>Importa datos de OpenStreetMap</p>
<p>http://www.slideshare.net/andrewxhill/using-cartodb-to-analyze-openstreetmap-data</p>
