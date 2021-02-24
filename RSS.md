# RSS
## ¿Que es RSS?
El RSS es un formato basado en XML que permite encontrar aquella información que mejor se
adapta a lo que el usuario desea, pero también ofrecerla de forma rápida y actualizada. 

Existen tres tipos de formato RSS y sus siglas adquieren un significado diferente según la
especificación usada:
- Rich Site Summary (RSS 0.91)
- RDF Site Summary (RSS 0.9 y 1.0)
- Really Simple Syndication (RSS 2.0) 

Los archivos RSS son un nuevo método para obtener y ofrecer información gracias a que
contienen metadatos sobre las fuentes de información. Este formato es de gran utilidad para
sitios Web que actualicen sus contenidos con frecuencia, ya que permite compartir la
información y verla en otros sitios de forma inmediata.

Para resumir, RSS es una técnica para difundir de forma eficaz los contenidos de un sitio Web,
pero también es un lenguaje derivado del XML para construir archivos que guardan el contenido que 
queremos difundir.

Ventajas:
- Los usuarios no necesitan comprobar si la información ha sido actualizada en los sitios de interés.
- Es texto plano, por lo que es ligero y rapido para ser transmitido.
- Mediante sidicacion, podemos filtrar la información que nos interesa de cada sitio web.

## ¿Como crear nuestro propio RSS?

### Primero:
Debemos especificar que el archivo es un xml, la codificación de caracteres, y que será un feed de RSS. Para ello al inicio de nuestro archivo escribiremos:

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<rss version="2.0">

</rss>
```
### Segundo:
Información de nuestro canal
El feed de RSS tiene que explicitar información del canal (channel) es decir, de nuestra web o podcast, en este caso. Entre las informaciones que podemos están el título (title) del canal, el link, y una descripción (description). Ya comenzamos a anidar las cajitas:
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<rss version="2.0">

<channel>

<title>Github del profe</title>
<link>https://github.com/raracil1/M4_LEN_MARCAS</link>
<description>Enlace de interés con aputes.</description>

</channel>

</rss>
```
Las etiquetas se abren y se cierran: <title>…</title>. Todo lo que escribamos entre esas etiquetas será entendido como un título.

### Tercero:
Agregamos los ítems
Cada uno de los elementos que se irán actualizando se llama ítem y los incluimos con la etiqueta <item></item>. Cada ‘cajita’ item vuelve a tener adentro más información como:

- Título: <title>…</title>
- Descripción: <description>…</description>
- Archivo: <enclosure>. Esta etiqueta tiene atributos que características que debemos poner dentro de la etiqueta (ya veremos un ejemplo):
- url (ubicación)
- type (tipo)
- lenght (duración, en segundos)
- Categorías: <category>…</category>
- Autoría :<author>…</author>
- URL: <link>…</link>
- Fecha de publicación: <pubDate>…</pubDate>

Nuestro XML quedaría de la siguiente manera:
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<rss version="2.0">

<channel>

<title>Github del profe</title>
<link>https://github.com/raracil1/M4_LEN_MARCAS</link>
<description>Enlace de interés con aputes.</description>
<item>
<title>Canals de continguts: RSS</title>
<link>https://wiket.esteveterradas.cat/index.php/Canals_de_continguts:_RSS</link>
<description>Ejercicio RSS</description>
<author>Leandro Zabala</author>
</item>
</channel>

</rss>
```
### Cuarto:
Por último, enlazar el archivo del fee (archivo.rss)d a nuestra página web. Es decir, debemos escribir en el cabezal de nuestra página web la dirección de nuestro rss. 

Ejemplo:
```xml
<head>

<link rel="alternate" type="application/rss+xml" title=Mi primer RSS» href="archivo.rss" />

</head>
```
Después simplemente tendremos que ir agregando ítems a medida que vayamos publicando. 
Es recomendable colocar el más nuevo como primer item para que queden ordenados cronológicamente.



## EJERCICIOS

- Crea un archivo RSS de contenidos Web (con 5 articulos). Agregarlo a una pagina web (html) y probar en distintos navegadores.
- Realizar los 3 ejercicios de la wiki (1 , 2 y proyecto): https://wiket.esteveterradas.cat/index.php/Canals_de_continguts:_RSS
