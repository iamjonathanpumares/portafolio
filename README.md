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

	<nombre_etiqueta [atributo="valor"]>Contenido</nombre_etiqueta>

Las etiquetas o elementos de HTML siempre tiene una apertura y un cierre como es el caso de la etiqueta **body** (por mencionar alguna) que define el cuerpo de nuestro documento.: 

	<body></body> 

Hay casos en los que la etiqueta tiene un cierre diferente como es el caso de la etiqueta **img**, y al mismo tiempo nos fijamos que dentro de la etiqueta define un atributo **src** y su valor es la ruta donde se encuentra la imagen:

	<img src="images/avatar.jpg" />

Adentro de las etiquetas podemos poner contenido que es visible para el usuario como por ejemplo, si queremos poner un titulo usamos la etiqueta **h1**:

	<h1>Titulo</h1> 

y notesé que dentro de las etiquetas ponemos el contenido.

Las nuevas etiquetas de HTML 5 como header, nav, section, article, aside, footer nos dan más peso semantico, lo que quiere decir es que con tal solo ver el nombre de la etiqueta sabemos de que se trata. El elemento header se refiere al encabezado de nuestra página, el elemento nav se refiere a la navegación de nuestra página como lo puede ser un menú y así es como las etiquetas en HTML 5 tienen más significado.