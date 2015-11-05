# Iniciando en el Desarrollo Web

## ¿Qué es HTML?

HyperText Markup Language
(Lenguaje de Marcado de Hipertexto, se compone de etiquetas también llamados elementos que van construyendo la estructura de nuestra página) 

HTML != Lenguaje de programación (No tiene estructuras, no tiene variables, no tiene funciones)

El navegador solamente entiende código HTML, CSS, JavaScript.

## Las tres tecnologías usadas en el Frontend

HTML (Estructura o contenido de la página)
CSS (Estilos, colores, tipos de letra, acomodar elementos)
JavaScript (Interacción, páginas dinamicas)

## Sintaxis

La sintaxis de los elementos HTML es la siguiente:

~~~
<nombre_etiqueta [atributo="valor"]>Contenido</nombre_etiqueta>
~~~

Las etiquetas o elementos de HTML siempre tiene una apertura y un cierre como es el caso de la etiqueta **body** (por mencionar alguna) que define el cuerpo de nuestro documento.: 

~~~
<body></body>
~~~ 

Hay casos en los que la etiqueta tiene un cierre diferente como es el caso de la etiqueta **img**, y al mismo tiempo nos fijamos que dentro de la etiqueta define un atributo **src** y su valor es la ruta donde se encuentra la imagen:

~~~
<img src="images/avatar.jpg" />
~~~

Adentro de las etiquetas podemos poner contenido que es visible para el usuario como por ejemplo, si queremos poner un titulo usamos la etiqueta **h1**:

~~~
<h1>Titulo</h1>
~~~ 

y notesé que dentro de las etiquetas ponemos el contenido.

Las nuevas etiquetas de HTML 5 como header, nav, section, article, aside, footer nos dan más peso semantico, lo que quiere decir es que con tal solo ver el nombre de la etiqueta sabemos de que se trata. El elemento header se refiere al encabezado de nuestra página, el elemento nav se refiere a la navegación de nuestra página como lo puede ser un menú y así es como las etiquetas en HTML 5 tienen más significado.

## ¿Qué es CSS?

Cascading Style Sheets (Hoja de Estilos en Cascada)

### Empezando con CSS

Hay tres maneras de incluir estilos a nuestra página web

* Estilos inline (Estilos en línea, aplican estilos dentro de las etiquetas HTML por medio del atributo **style**)

~~~
<p style="font-size: 20px;">Mi texto</p>
~~~

* Estilos por medio de la etiqueta style (Esta etiqueta es insertada en la cabecera del documento HTML y dentro van los estilos)

~~~
<!DOCTYPE html>
<html>
<head>
	<title>Título del documento</title>
	<style>
		p
		{
			font-size: 20px;
		}
	</style>
</head>
<body>
	<p>Mi texto</p>
</body>
</html>
~~~

* Estilos por medio de un archivo externo (Recomendada)

~~~
<!DOCTYPE html>
<html>
<head>
	<title>Título del documento</title>
	<link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
	<p>Mi texto</p>
</body>
</html>
~~~

### Tipos de selectores

Se le llaman selectores porque estamos seleccionando cuáles elementos HTML serán afectados por las reglas CSS

#### Selectores de elemento

Son aplicados a las etiquetas de nuestro documento HTML

~~~
p
{
	font-size: 20px;
}
~~~

En este caso estamos diciendo: Encuentrame todos las etiquetas `<p></p>` dentro de mi documento HTML y ponle un tamaño de fuente de 20px.

####Selectores de id

Son aplicados solamente a un elemento de nuestro documento HTML por medio del atributo **id**

**HTML**

~~~
<!DOCTYPE html>
<html>
<head>
	<title>Título del documento</title>
</head>
<body>
	<p id="id_parrafo">Mi texto</p>
</body>
</html>
~~~

**CSS**

~~~
#id_parrafo
{
	font-size: 20px;
}
~~~

####Selectores de clase

Los podemos aplicar a cualquier elemento de nuestra página por medio del atributo **class**

**HTML**

~~~
<!DOCTYPE html>
<html>
<head>
	<title>Título del documento</title>
</head>
<body>
	<p class="parrafo">Mi texto</p>
	<p class="parrafo">Mi texto</p>
	<p>Mi texto</p>
</body>
</html>
~~~

**CSS**

~~~
.parrafo
{
	font-size: 20px;
}
~~~

En este caso estamos diciendo: A todos los elementos HTML con la clase parrafo ponles un tamaño de fuente de 20px.

#### Selectores de atributo

Son aplicados a todos los elementos HTML que tengan un atributo en especifico.

**HTML**

~~~
<!DOCTYPE html>
<html>
<head>
	<title>Título del documento</title>
</head>
<body>
	<form>
		<input type="text" name="nombre">
		<input type="text" name="apellidos">
		<input type="submit" value="Enviar">
	</form>
</body>
</html>
~~~

**CSS**

~~~
[type="text"]
{
	width: 150px;
}
~~~

En este ejemplo estamos diciendo: A todos los elementos HTML con el atributo type="text" ponles un ancho de 150px. En este caso estamos especificando el atributo con su valor, pero igualmente podríamos especificar solamente su atributo o aún más especifico especificando tanto el elemento con su atributo y con/sin su valor.

**CSS**

~~~
/* Especificando solamente el atributo */
[href]
{
	width: 150px;
}

/* Especificando tanto el elemento como su atributo */
a[href]
{
	width: 150px;
}
~~~

### Diseña para todos los navegadores con Normalize

Cada navegador (ya sea Chrome, Mozilla Firefox, Safari, etc.) le aplica estilos propios a cada uno de los elementos HTML de manera diferente, esto hace que surja un conflicto a la hora de maquetar nuestra página web ya que vemos que se ve ligeramente diferente en un navegador u otro. Para eso tenemos una herramienta llamada **Normalize** que no es más que una hoja de estilos que estandariza los estilos para que todos nuestros elementos HTML se vean de igual manera en todos los navegadores poniendo así unos estilos por defecto.

Para eso tenemos que descargarlo desde el siguientae enlace [normalize.css](https://necolas.github.io/normalize.css/)

Damos click al bóton "Download" y nos abre un archivo .css como tal, damos click derecho, "Guardar como" y lo guardamos en la ubicación donde estemos trabajando nuestras hojas de estilos.

El último paso es agregarlo a nuestro documento HTML por medio de la etiqueta **link**

~~~
<!DOCTYPE html>
<html>
<head>
	<title>Título del documento</title>
	<link rel="stylesheet" type="text/css" href="normalize.css">
</head>
<body>

</body>
</html>
~~~

> Nota: Aqui damos por hecho de que el archivo normalize.css se encuentra en la misma ubicación que el documento HTML.

### Modula tu código CSS con Suit

A la hora de aplicar estilos a nuestro documento HTML tenemos que decidir que tipos de selectores vamos a utilizar, si selectores de elemento, selectores de id, selectores de clases, etc. Lo recomendado es siempre que utilices selectores de clases, y para eso tenemos que aprender a nombrar nuestras clases. Existe una convención llamada **SUIT CSS** la cual nos recomienda 5 reglas para nombrar nuestras clases.

1. Vamos a tener en nuestras clases componentes, nuestro header es un componente, nuestro section es un componente, nuestro footer es otro componente, nosotros podemos ir separando en componentes cada uno de nuestros elementos HTML de tal manera que sea fácil identificarlos. Las clases de los componentes empiezan en mayúsculas y cada palabra que lleva también.

~~~
.MyComponent
{
	/* ... */
}
~~~

> Un componente es una pequeña parte de nuestra aplicación que podemos abstraer y tenerla independiente que pueden tener tanto su parte HTML, como CSS y JavaScript y todo esto va a hacer un pequeño conjunto de nuestra aplicación.

2. Los componentes pueden tener modificadores y estos se dividen con dos guiones "--". Se usan para tener una variación de estilo respecto al componente principal añadiendo a este una clase.

~~~
/* Estilos base del componente Button */
.Button
{
	/* ... */
}

/* Variación de estilos con respecto al componente Button */
.Button--default
{
	/* ... */
}

<button class="Button Button--default">...</button>
~~~

3. Las partes de un componente tendrán la división de un guión "-". Y estas clases son descendentes como el contenido que tendrá el componente.

~~~
<article class="Tweet">
	<header class="Tweet-header">
		<img class="Tweet-avatar" src="{{src}}">
		...
	</header>
	<div class="Tweet-bodyText">
		...
	</div>
</article>
~~~

4. Es normal que quieras tener algo de dinamismo en los elementos. Para lograrlo, se suele agregar una clase con esta acción. Para eso existen los estados; estos empezarán con ".is-" y la descripción del estado.

~~~
.Tweet
{
	/* ...*/
}

.Tweet.is-expanded
{
	/* ...*/
}

<article class="Tweet is-expanded"></article>
~~~

5. Como bonus, y sin ser parte de un componente, están las utilidades. Estas serán clases generales que te ayudarán en todo el proyecto. Las utilidades comienzan con ".u-" y luego su descripción. Manéjalas con precaución para que los componentes no sean dependientes de ellas. Por ejemplo, puedes crear un contenedor donde irá el componente con utilidades: ".u-wrapper"

### Escribir nuestras reglas de CSS

Hasta ahorita no hemos visto como tal cual es la sintaxis para escribir nuestras reglas de CSS, es decir, los estilos que tendrán nuestros elementos. Para ello, ya sea el selector que vayamos a utilizar (de elemento, de id, de clase, etc.) abrimos llaves para después de haber declarado nuestro selector y dentro de las llaves aplicamos los estilos para el selector de la siguiente manera:

~~~
/* Selector de clase */
.selector
{
	propiedad: valor;
	propiedad: valor;
}
~~~

### Modelo de caja

Cada elemento HTML se comporta como una caja rectangular.

Los elementos HTML (cajas rectangulares) se componen de 6 partes:

* Contenido (content): Se trata del contenido HTML del elemento (las palabras de un párrafo, una imagen, el texto de una lista de elementos, etc.)

* Relleno (padding): espacio libre opcional entre el contenido y el borde, se podría decir que es el margen interior del elemento.

* Borde (border): línea que encierra completamente el contenido y su relleno.

* Imagen de fondo (background image): imagen que se muestra por detrás del contenido y el espacio de relleno.

* Color de fondo (background color): color que se muestra por detrás del contenido y el espacio de relleno.

* Margen (margin): separación opcional existente entre la caja y el resto de cajas adyacentes.

### Unidades de medida

Las unidades de medida CSS se utilizan para definir la anchura, altura y los márgenes de los elementos HTML y para establecer el tamaño de letra del texto.

Las unidades de medida se clasifican en dos grupos: Las relativas y absolutas. Las unidades relativas definen su valor en relación con otra medida, por lo que para obtener su valor real, se tiene que realizar una operación con el valor indicado. Las unidades absolutas definen su valor de manera explicita, es decir, el valor indicado.

[Unidades de medida](https://platzi.com/blog/unidades-de-medida-en-css/)

#### Unidades relativas

* em, relativa con respecto al tamaño de letra del elemento actual.

* rem, relativa con respecto al tamaño de letra del elemento raíz (html).

* px, (píxeles) relativa con respecto al tamaño de resolución de la pantalla en la que se visualiza el documento HTML.

* %, (porcentaje) relativa con respecto a los tamaños de su elemento padre.

* vw (viewportheigth), ancho del viewport 

* vh (viewportwidth), alto del viewport

#### Unidades absolutas

* in, pulgadas.

* cm, centimetros.

* mm, milimetros.

* pt, puntos.

* pc, picas.

### Tipos de elementos

El estándar HTML clasifica a todos sus elementos en dos grupos: elementos en línea y elementos de bloque.

Los elementos en bloque siempre empiezan en una nueva línea y ocupan todo el ancho disponible del navegador. Los elementos en línea no necesariamente comienzan en una nueva línea y sólo ocupan el ancho de su contenido.

Por sus características, los elementos de bloque no pueden insertarse dentro de elementos en línea y tan sólo pueden aparecer dentro de otros elementos de bloque. En cambio un elemento en línea puede aparecer tanto en un elemento en bloque como de otro elemento en línea.

### Propiedad display

Es una propiedad de CSS que define la manera en la que se visualiza nuestro elemento en la pantalla. Podemos aplicarlo a cualquier elemento de nuestro documento HTML.

#### Valores de la propiedad display 

* inline-block (Los elementos que tengan esta valor se visualizan uno al lado de otro, es decir, ocupan el ancho de su contenido)

* block (Los elementos que tengan esta valor se visualizan uno encima de otro, es decir, ocupan todo el ancho de la página)

* none (Este valor hace que los elementos no se muestren en la pantalla ni en el DOM)

* table (Este valor hace que los elementos se comporten como una etiqueta `<table>`, sus elementos hijos tienen otras propiedades para que se comporten como celdas o columnas)

Display flex

### Propiedad position

Es una propiedad de CSS que nos da la capacidad de ubicar o posicionar nuestros elementos HTML en cualquier lugar de la pantalla.

#### Valores de la propiedad position

* static, este es el valor por defecto de todos los elementos HTML, respetando el modelo de caja y acomodando nuestros elementos de acuerdo a su tipo (en línea o de bloque).

* relative, al asignar este valor a la propiedad position, tenemos cuatro posibilidades (propiedades) de posicionar nuestros elementos, top, rigth, bottom, left, respetando y partiendo desde el lugar en el que fueron puestos en el documento HTML.

* absolute, de igual manera tiene las cuatro posibilidades mencionadas (top, rigth, bottom y left), pero al asignar este valor, el elemento pierde su lugar en el se ubicaba en el documento HTML y se van acomodando los demás elementos en su lugar, y se ubica en el elemento padre más cercano con position: relative.

* fixed, se comportan de manera similar al valor absolute, la única diferencia es que su posición del elemento en la pantalla se mantiene fija por lo que al hacer un scroll el elemento nos persigue en toda la página.

Responsive Design

Que nuestras aplicaciones web se puedan visualizar en todos los dispositivos disponible

### Viewport

Área visible del navegador












