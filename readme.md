<h1>Workshop - Grupo de Periodismo de Datos del Medialab Prado<h1>
<h2>Enlaces y recursos adicionales</h2>

<p>Los archivos incluidos en este repositorio (index.html, CSS) contienen todos los elementos necesarios para publicar un mapa elaborado con CartoDB en una plantilla de información. La plantilla ha sido elaborada por [@saleiva](https://github.com/CartoDB/cartodb-publishing-templates). 
<p>![Alt text](img/img5.png "screenshot 4")</p>

<p>Plantillas de CartDB:</p>
<p>[https://github.com/CartoDB/cartodb-publishing-templates](https://github.com/CartoDB/cartodb-publishing-templates)</p>



<h3>Workshop</h3>
<p>El primer ejercicio consiste en importar datos a CartoDB y combinarlos en una única tabla para la elaboración de un mapa del paro en España.</p>

<p>Los Datos de las provincias españolas están disponibles en:</p> 
<p>[http://2read.cartodb.com/tables/spain_provinces/public/](http://2read.cartodb.com/tables/spain_provinces/public/)</p>

<p>Datos del paro (4º trimestre de 2012):</p> [http://2read.cartodb.com/tables/paro_spain_2012iv/public/](http://2read.cartodb.com/tables/paro_spain_2012iv/public/)</p>

<p>Para unir las dos tablas, utilizamos la función "merge tables" del panel de CartoDB. Elegimos la tabla que queremos combinar y seleccionamos la columna que utilizaremos como referencia ("provincia" y "provincias") más las que queremos importar. Asignamos un nombre a la nueva tabla.  

<p>![Alt text](img/img1.png "screenshot 1")</p>



<h3>Elaboración del mapa del paro</h3>
<p>Los datos están en la columna "paro_2012iv". Transformamos la columna de "string" a "numbers" (para poder utilizarla como referencia para elaborar el mapa).</p>

<p>![Alt text](img/img2.png "screenshot 2")</p>

<p>En la vista de "map view", elegimos el mapa de base y editamos el estilo del mapa a través del menú "visualization wizard". </p>

<p>![Alt text](img/img3.png "screenshot 3")</p>

<p>El mapa se puede publicar a través de la función "share". </p>


<h3>Edición avanzada</h3>
<p>Utilizamos la tabla siguiente:</p> 
<p>[http://2read.cartodb.com/tables/madrid_mercados_puntos/public/](http://2read.cartodb.com/tables/madrid_mercados_puntos/public/)</p>

<p>Query utilizada para unir las tres tablas originales:</p> 
<p><code>SELECT 'abastos' as new_table, the_geom, denominaci, direccion FROM abastos UNION SELECT 'galerias' as new_table, the_geom, direccion, nombre from galimenta UNION select 'hipermercados' as new_table, the_geom, direccion, eti FROM hipermercados</code></p>

<p>Añade una imagen al infowindow</p>

<p>![Alt text](img/img4.png "screenshot 4")</p>

<p>Edita los estilos (diferenciar puntos)</p>

<p>Crear un polígono, puntos o líneas + cartocss building-height</p>
![Alt text](img/img6.png "screenshot 5")

<p>Importa datos de CartoCSS</p>
