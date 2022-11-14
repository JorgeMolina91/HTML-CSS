# Notas del curso de FronEnd de Platzi

 
**Motores de Renderizado**

Es básicamente pasar los archivos que escrinimos (HTML y CSS) y traducirlos a pixeles.

|  Navegador  |    Motor    |
| ----------- | ----------- | 
|   Chrome    |    Blink    |
|    Edge     |  Edge HTML  |
|   Safari    |    Webkit   |
|   Firefox   |    Gecko    |

Los 5 pasos de los motores:

1. Pasa los archivos de HTML a objetos (El DOM). Esto para que el navegador pueda entenderlo.
2. Calcula el estilo correspondiente a cada nodo en el DOM.
3. Calcula las dimensiones de cada nodo y va a empezar a estructurar la página web.
4. Pinta las diferentes cajas (porque en HTML y CSS todo son cajas)
5. Toma las capas y las convierte en una imagen, para finalmente mostrar esta imagen en la pantalla.

## HMTL Semántico

El HTML semántico consiste en que cada elemento tenga su propia etiqueta que lo defina correctamente. Sin utilizar etiquetas muy generales, como `<div>` o `<span>`.

**¿Cuáles son las etiquetas semánticas?**

Las etiquetas semánticas para definir una interfaz de una página web son:

- `<header>`: define el encabezado de la página (no confundir con `<head>`).
- `<nav>`: define una barra de navegación que incluye enlaces.
- `<section>`: define una sección de la página.
- `<footer>`: define un pie de página o de sección.
- `<article>`: define un artículo, el cual puede tener su propio encabezado, navegación, sección o pie de página.

Ahora que ya conoces las etiquetas semánticas, evita el uso excesivo de `<div>`.

## Etiquetas de HTML más usadas

**Etiquetas de layout o diseño de la página**

Las etiquetas más usadas para layout o diseño de página son aquellas que utilizamos para construir una página semántica:

- `<header>`
- `<nav>`
- `<section>`
- `<article>`
- `<aside>`
- `<footer>`

**Etiquetas de enlace**

La etiqueta de enlace `<a>` o “anchor” define un vínculo o enlace hacia una URL. Se utiliza con el atributo href con el valor del enlace.

`<a href="https://platzi.com/cursos/frontend-developer/">
    Curso Frontend
</a>`

**Etiquetas para textos**

Las etiquetas más usadas para definir textos son:

- `<h1>, <h2>, <h3>, <h4>, <h5>, <h6>`: define diferentes tipos de títulos con diferente orden de importancia, donde 1 tiene mayor relevancia. Solo debe existir una etiqueta `<h1>` por página web.
- `<p>`: define un párrafo.
- `<span>`: define un contenedor genérico de tipo inline. Igual que `<div>` no tiene valor semántico y debes evitar su uso innecesario.

> Block: Ocupa todo el ancho de la página
> 
> Inline: Ocupa solo el espacio del elemento. Cuando hay más de uno, se pone uno al lado del otro.
>
> Inline-Block: Es una mezcla de los dos anteriores... Es básicamente para poder controlar el ancho, altos y margenes



**Etiquetas para multimedia**

Las etiquetas más usadas para definir elementos multimedia son:

- `<img>`: define una imagen. Es necesario especificar los atributos src con la URL de la imagen; y alt que representa un texto alternativo en caso de que la imagen no cargue correctamente.
- `<svg>`: define un svg.
> Son un formato de imagenes basado en vectores
- `<iframe>`: define un contenedor para una página web dentro de otra página web.
- `<video>`: define un contenedor de video.

**Etiquetas para formularios**

Las etiquetas más usadas para definir formularios son:

- `<form>`: define un formulario.
- `<input>`: define un elemento de entrada del formulario. Es necesario especificar el tipo con el atributo type. Existen varios tipos de input, revísalos en su documentación.
- `<label>` define un título para la etiqueta `<input>`. Es utilizado para acciones de accesibilidad.
- `<button>`: define un botón. Es usado para la interactividad de la página.

**Etiquetas para listas**

Las etiquetas más usadas para definir formularios son:

- `<ul>`: define una lista desordenada. (unordered list)
- `<ol>`: define una lista ordenada. (ordered list)
- `<li>`: define un elemento dentro de una lista. (list item)

`<ul>
    <li>Soy un elemento</li>
    <li>Soy otro elemento</li>
    <li>Soy hijo de ul</li>
</ul>`


## Tipos de selectores CSS

**De tipo**
`div{
}`


**De clase**
`.card{
}`
`.card1{
}`
`.card2{
}`
Puede existir más de un valor dentro del atributo class separados por espacios.
`<div class="card card1"> Soy una carta </div>`
`<div class="card card2"> Soy una carta </div>`


**De id**
`#id-container{
}`
Solo puede existir un id por elemento y debe ser único


**De atributo**
`<a href="https://platzi.com"> Ir a Platzi </a>`
Para seleccionar los elementos, se empieza por el nombre de la etiqueta, seguido de corchetes [] que contiene el atributo y valor especificado.

`a[href=""https://platzi.com"] {
    /* Todas las etiquetas <a> con una propiedad href con valor "https://platzi.com" */
}`


### Cuáles son los selectores combinadores

**Combinador de descendientes**
Selecciona todos los elementos del selector de la derecha que sean hijos del selector de la izquierda, independientemente de la profundidad. Estos selectores están separados por un espacio.
`padre hijos {
    /* Todos los hijos del padre */
}`
`div p{
    /* Todos los hijos <p> de <div>*/
}`
`.container img{
    /* Todos los hijos <img> de la clase "container"*/
}`


**Combinador de hijo directo**
Selecciona todos los elementos del selector de la derecha que son hijos directos del selector de la izquierda. Estos selectores están separados por >
`padre > hijos_directos {
    /* Todos los hijos directos del padre */
}`
`div > p{
    /* Todos los hijos directos <p> de <div>*/
}`
`.container > img{
    /* Todos los hijos directos <img> de la clase "container"*/
}`

**Combinador de elemento adyacente**
Selecciona todos los elementos del selector de la derecha que están adyacente (debajo de) al selector de la izquierda. Estos selectores están separados por +
`elemento + adyacente {
    /* Elementos adyacentes */
}`
`div + p{
    /* Todos los `<p>` adyacentes a `<div>`*/
}`
`.container + img{
    /* Todos los `<img>` adyacentes a la clase "container"*/
}`
Adyacente significa que comparten el mismo padre y está situado inmediatamente hacia abajo de otro elemento. Por ejemplo, en el siguiente código, `<div>` está adyacente a `<h1>` y `<p>` está adyacente a `<div>`. Sin embargo, `<h1>` no está adyacente a `<div>` y `<div>` no está adyacente a `<p>`.

`<h1>`Soy un título `</h1>`
`<div>`Soy un div`</div>`
`<p>`Soy un párrafo`</p>`


**Combinador general de hermanos**
Selecciona todos los elementos del selector de la derecha que son hermanos del selector de la izquierda. Estos selectores están separados por ~
`elemento ~ hermanos {
    /* Elementos hermanos */
}`
`div ~ p{
    /* Todos los `<p>` hermanos de `<div>`*/
}`
`.container ~ img{
    /* Todos los `<img>` hermanos de la clase "container"*/
}`
Hermanos significa que comparten el mismo padre y están situados hacia abajo de otro elemento. Por ejemplo, en el siguiente código, `<div>` y `<p>` son hermanos de `<h1>`, pero `<h1>` no es hermano de `<div>` y `<p>`

`<h1>`Soy un título `</h1>`
`<div>`Soy un div`</div>`
`<p>`Soy un párrafo`</p>`


### Tipos de selectores: pseudoclases y pseudoelementos

**Pseudoclases**

Se definen como estados de algún elemento (con el mouse encima, visitado, activo, etc.)

`selector : pseudoclase { 
    propiedad: valor;
}`

:link
Representa el estado de un elemento que no ha sido visitado - Que no se le ha dado click encima


:visited
Representa el estado de un elemento que ya ha sido visitado - Que ya se le dio click encima


:hover
Representa el estado en el cual el cursor está encima del elemento. - Pasa el curso por encima solamente... Sin dar click ni nada


:active
Representa el estado en el que el cursor interactua con el elemento - Cuando se está dando click.. No antes no despues, sino el momento en que se esta dando click encima del elemeto


:not()
Representa el estado en el cual no coinciden los selectores que se indiquen.
<!-- Selecciona cualquier elemento que NO sea un párrafo -->
`:not(p) {
  color: blue;
}`


:nth-child()
Representa el estado en el cual coinciden los hijos del elemento según el valor indicado.

Valores de palabras clave:

nth-child(odd) o nth-child(2n+1)
Representa los elementos impares: 1, 3, 5, etc.

nth-child(even) o nth-child(2n)
Representa los elementos pares: 2, 4, 6, etc.

:nth-child(7)
Representa el séptimo elemento.

:nth-child(5n)
Representa los elementos 5, 10, 15, etc.

:nth-child(3n+4)
Representa los elementos 4, 7, 10, 13, etc.

:nth-child(-n+3)
Representa los primeros tres elementos entre un grupo de hermanos.

p:nth-child(n)
Representa cada elemento `<p>` entre un grupo de hermanos. Esto es lo mismo que un simple selector p.

p:nth-child(1) o p:nth-child(0n+1)
Representa cada `<p>` que es el primer elemento entre un grupo de hermanos. 
Esto es lo mismo que el selector :first-child.

**Pseudoelemento**

Un pseudoelemento define el estilo de una parte específica de un elemento.

::before
Sirve para agregar un contenido antes del elemento. El contenido es agregado mediante la propiedad content de CSS.
<!--Añade un corazón antes de los enlaces--> 
`a::before {
  content: "♥";
}`


::after
Sirve para agregar un contenido después del elemento. El contenido es agregado mediante la propiedad content de CSS.
<!--Añdade una flecha después de los enlaces-->
`a::after {
  content: "→";
}`


::first-letter
Sirve para añadir estilos a a la primera letra del texto de cualquier elemento.
<!--Selecciona la primera letra de <p>-->
`p::first-letter {
  font-size: 130%;
}`


## Cascada y especificidad en CSS

**Cascada**
La cascada es el concepto que determina qué estilos se colocan sobre otros, priorizando a aquellos que se encuentren más abajo del código. Recordarás que CSS es la abreviación de Cascade Style Sheets, que traducido es hojas de estilos en Cascada.
`<h1>`Titulo`</h1>`
`h1 {
    color: red;
}`
`h1 {
    color: blue;
}`
En este caso, prevalecerá la propiedad 'blue' porque, como se mencionó, siempre va a prevalecer el último estilo que se la haya dado al elemento

**Especificidad**
La especificidad es el medio por el que los navegadores deciden qué valores de propiedades CSS son los más relevantes para un elemento y, por tanto, se aplicarán. La especificidad se basa en las reglas de concordancia que se componen de diferentes tipos de selectores CSS.
La cantidad de especificidad que tiene un selector se mide utilizando cuatro valores diferentes (o componentes), que se pueden considerar como miles, cientos, decenas y unos

#### Miles
Puntúa uno en esta columna si la declaración está dentro de un atributo style, también conocido como estilos en línea. Estas declaraciones no tienen selectores, por lo que su especificidad es siempre 1000.

#### Cientos
Puntúa uno en esta columna por cada selector de ID contenido dentro del selector general.

#### Decenas
Puntúa uno en esta columna por cada selector de clase, selector de atributos o pseudoclase que contenga el selector general.

#### Unos
Puntúa uno en esta columna por cada selector de elemento o pseudo-elemento contenido dentro del selector general.

#### !important 
cambia la forma en que la cascada funciona normalmente, por lo que puede hacer que la depuración de los problemas de CSS sea realmente difícil de resolver, especialmente en una hoja de estilos grande.
**No lo uses si puedes evitarlo**
La única manera de anular esta declaración !important sería incluir otra declaración !important en una declaración con la misma especificidad más adelante en el orden de las fuentes, o una con mayor especificidad.


## Tipos de display más usados: block, inline e inline-block

**Block**
Estos elementos ocupan toda la pantalla, por lo que si quieres agregar otro elemento, este se agregará automáticamente abajo. No importa que tengas poco contenido, el elemento sí o sí va a ocupar toda la pantalla. 
Con estos elementos es posible manipular el ancho y el alto del elemento

**Inline**
 Estos elementos son los que su caja mide exactamente lo mismo que su contenido. Estos elementos los podemos usar en textos y en lugar de que se agreguen en una nueva línea se agregaran justo al ladito del texto. ❗ Tienen como desventaja que no podemos ponerles márgenes top ni bottom (solo hacia los lados), ni tampoco podemos cambiar su ancho ni su alto.

**Inline-block**
Esto mezcla lo mejor de ambos mundos. Con este display podemos tener tanto los beneficios de inline como de block, es decir, podemos tener elementos que no ocupen todo el ancho de la pantalla, sino que ocupen solamente lo que su contenido ocupa, pero también vamos a poder darle márgenes y podremos cambiar su tamaño 🤠.


### Tipos de display más usados: flexbox y CSS grid

**Qué es flexbox**
Flexbox consiste en el ordenamiento de elementos hijos en un solo eje, por defecto horizontalmente. El elemento padre o contenedor deberá contener la propiedad display con el valor flex. A partir de aquí, ya puedes ordenar los hijos según sea necesario.

**Qué es grid**
Grid consiste en el ordenamiento de elementos hijos en dos ejes, como si fuera una cuadrícula o tabla. El elemento padre o contenedor deberá contener la propiedad display con el valor grid y debes definir las medidas de las columnas y de las filas. A partir de aquí, ya puedes ordenar los hijos según sea necesario.


## Modelo de caja
Hay 4 medidas a tener en cuenta:
**Content**
Es lo que mide el contenido como tal de un elemento en cuanto a alto y ancho


**Padding**
Es el espacio entre la caja y el contenido de la caja, es decir, es un espacio interno... La diferencia con Margin, es que este espacio es para que el contenido 'respire' dentro de su caja contenedora, el margin es espacio con otras cajas. 

Se puede establecer el padding en cada posición en una sola línea de las siguientes maneras:
padding: [arriba] [derecha] [abajo] [izquierda], siguiendo el sentido horario.
padding: [arriba] [abajo] [derecha e izquierda], siguiendo el eje principal.
padding: [arriba y abajo] [derecha e izquierda], siguiendo los ejes del elemento.

También estableciendo de manera individual los valores de cada posición:
`div {
    padding-top: 10px;
    padding-bottom: 15px;
    padding-left: 20px;
    padding-right: 10px;
}`

**Border**
Es el delineado que le podemos dar a una caja, y un borde puede ser tan grueso como quieras. Simplemente debemos ponerle el grosor, el tipo de borde y el color del borde.

`div {
    border: [color] [style] [width];
}`
`div {
    border-color: red;
    border-style: solid;
    border-width: 1px;
}`


**Margin**
El margin consiste en el espacio entre el borde y otro elemento HTML. Si imaginamos una caja, es el espacio entre tu caja y otra caja.

Puedes establecer el margin en cada posición en una sola línea de las siguientes maneras:
margin: [arriba] [derecha] [abajo] [izquierda], siguiendo el sentido horario.
margin: [arriba] [abajo] [derecha e izquierda], siguiendo el eje principal.
margin: [arriba y abajo] [derecha e izquierda], siguiendo los ejes del elemento.

También estableciendo de manera individual los valores de cada posición:
`div {
    margin-top: 10px;
    margin-bottom: 15px;
    margin-left: 20px;
    margin-right: 10px;
}`


**Qué es el tamaño total del elemento**
Qué es el tamaño total del elemento
El tamaño total del elemento está determinado por la suma de los valores de las propiedades border padding y widtho height, dependiendo del eje. La propiedad margin no está incluida en este cálculo.
Por ejemplo, definimos los siguientes estilos:

`div{
  width: 150px;
  height: 150px;
  padding: 20px;
  border: 10px solid gray;
  margin: 30px;
}`

El tamaño total del elemento será de 210px en ambos ejes, donde la suma fue: 150 (altura/anchura) + 20 x 2 (padding ambos lados) + 10 x 2 (borde ambos lados). Si evaluamos este elemento en las herramientas del desarrollador mostrará su tamaño como 210x210.

**Propiedad box-sizing**
Esta propiedad deja fijos el alto y el ancho, y va modificando las medidas dependiendo del tamaño del elemento, el padding, el margin y el border que tenga, es decir, que si le damos al elemento un alto de 200PX y un ancho de 200px, pero ademas le agregamos un padding de 20px, el elemento ya no será de 200px, sino que se le restarán esos 20px, y ahora medirá 180px... Lo que quiere decir que deja fija la medida de alto y ancho y modifica los valores dependiendo de los valores de margin, padding y border que se le den al elemento.


## Colapso de Margenes
El colapso de márgenes sucede cuando dos elementos ***bloque*** adyacentes tienen un determinado valor de margin, entonces estos márgenes se solapan (mezclan) en un solo valor, el mayor de ambos.

En flexbox y grid no ocurre el colapso de márgenes. Cuida los márgenes que colocas en los elementos de tipo bloque.

## Posicionamiento
El posicionamiento en CSS consiste en cómo un elemento se situará, con respecto a su elemento padre y al flujo normal del documento. El flujo normal del documento es el orden de los elementos establecidos en el HTML.
La posición del elemento se la define con la propiedad position, mediante los siguientes valores:
- static
- relative
- absolute
- sticky

**Propiedades de posición**
Además de la propiedad position, existen cuatro propiedades del elemento de acuerdo a su posición con respecto a su padre, estas son: top (arriba), bottom (debajo), left (izquierda) y right (derecha).

`div {
    top: 10px;
    bottom: 15px;
    left: 20px;
    right: 10px;
}`

### Static
 es el valor por defecto de todo elemento HTML, consiste en respetar el flujo normal del documento donde las propiedades de posición no pueden ser establecidas.
 ### Relative
Elementos posicionados relativamente son desplazados una cantidad dada de su posición normal en el documento, pero sin que su desplazamiento afecte a otros elementos.
### Absolute
Los elementos posicionados relativamente se mantienen en el flujo normal del documento. Por el contrario, un elemento posicionado absolutamente es removido del flujo de esta manera, los demás elementos se posicionan como si el mismo no existiera. El elemento posicionado absolutamente se posiciona relativamente a su ancestro posicionado más cercano (es decir, el ancestro más cercano que no es static). Si no hay ningún ancestro posicionado se ubica relativo al bloque contenedor (en-US) inicial. En el ejemplo siguiente, la caja "Two" no tiene un ancestro posicionado, por lo tanto se posiciona relativo al `<body>` del documento.
### Fixed
El posicionamiento fijo es similar al posicionamiento absoluto, con la excepción de que el bloque contenedor del elemento es el viewport. Esto puede usarse para crear un elemento flotante que se mantiene en la misma posición independientemente del desplazamiento. Se debe tener cuidado con los espacios de los otros elementos porque, al quedarse fija, puede que se superponga a elementos cercanos.
### Sticky
El posicionamiento sticky se mueve hasta donde llega su contenedor. Si no tiene contenedor se muevo con el viewport. Se usa para crear un elemento flotante que se mantiene en la misma posición independientemente del desplazamiento. Este elemento ocupa espacio, por lo que no se va a tener inconvenientes con que se superponga a otros elementos cercanos.

**Z-index y el contexto de apilamiento**
El contexto de apilamiento consiste en la superposición de capas o elementos a lo largo del eje Z del navegador. Esto es importante para evitar que un elemento esté ocultando a otro.

### Qué son los planos y ejes
El navegador está constituido de tres planos y ejes: el ancho o X; el alto o Y; y el de profundidad o Z.
El eje X positivo está hacia la derecha; el eje Y positivo está hacia abajo; y el eje Z positivo está hacia el usuario.
### Qué es la propiedad z-index
El contexto de apilamiento se configura con la propiedad z-index.
Por defecto, todos los elementos tienen un valor auto, es decir, el orden está definido por la estructura del HTML. Los primeros elementos estarán detrás y los últimos estarán de frente.
Si se establece un valor positivo, este elemento se sitúa por delante de los demás. Si se establece un valor negativo, se sitúa por detrás.
Si un elemento tiene un z-index mayor a otro, estará por delante. Sin embargo, si un elemento que tiene un z-index menor a otros, sus hijos nunca estarán por encima, aunque su z-index sea mayor.


## Propiedades y valores de CSS más usados
Las propiedades CSS más usadas son las siguientes, separadas en secciones comunes, algunas ya las conocemos:
**layout**
Display
**modelo de caja**
Margin
Padding
Border -> La propiedad que establece bordes redondeados es: border-radius.
**tamaños**
Width
Height
**texto**
Font-size -> establece un tamaño de fuente
Font-weight -> establece el resaltado del texto, con valores de 100 a 900 en intervalos de 100; donde 100 es delgada y 900 es negrita.
Font-family -> establece el tipo de fuente.
Text-align -> establece la posición del texto: right, left, center y justify.
Color -> establece el color del texto.
**de fondo**
Background
Background-color

