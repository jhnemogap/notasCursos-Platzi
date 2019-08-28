# Curso de Desarrollo Web Online

## **_Carrera Arquitectura Frontend - Platzi 2019_**

## Introducción al desarrollo web

El desarrollo web tiene que ver con todo lo que percibimos a través del navegador: páginas, aplicaciones y sitios web como Facebook, Instagram y Twitter.

_**Para comprender cómo funciona internet necesitamos conocer tres grandes conceptos:**_

- **Clients** _(clientes)_: son los dispositivos a través de los cuales accedemos a los sitios web: un computador desktop, un teléfono, una laptop, etc.
- **Internet**: es toda la red formada por servidores y clientes que proveen y consumen contenidos web y se comunican entre sí a nivel global.
- **Server** _(servidor)_: es un computador, ubicado en alguna parte de la red, que está prendido todo el tiempo, en el que se alojan o almacenan sitios web y sus recursos y al cual se accede a través de nombres de dominio (.com, .net, .pe, etc.). También se les conoce como hosting.

_**Profesiones dentro del Desarrollo Web:**_

- **Frontend**: son los encargados de cuidar toda la apariencia y experiencia de usuario. Su misión es pasar todo el diseño gráfico de un sitio o aplicación web, a código, y proveer toda la acción interactiva hacia los clientes. Esta rama se puede subdividir en algunas especializaciones como: Arquitecto Frontend, Desarrollador JavaScript (frontend), etc.
- **Backend**: resguardan los datos y la seguridad de las aplicaciones y sitios web. Su misión es crear y mantener toda la parte del sitio web que sucede en los servidores. Pueden especializarse aún más en: SysAdmis, DevOps, Desarrollador JavaScript (backend), entre otros.

Las tres tecnologías básicas que debe conocer y manejar un Frontend son:

1. **HTML**: es el lenguaje de marcado para hacer websites.
2. **CSS**: hojas de estilos cascada, el diseño hecho código.
3. **JavaScript**: es el único lenguaje que funciona actualmente dentro de los navegadores de manera nativa.

---

> Plan de estudios para ser un gran desarrollador web en Platzi.com, **Curso: Arquitectura Fronted**

1. Desarrollo Web Online
2. Git y Github
3. Responsive Design
4. CSS Grid Layout
5. HTML y CSS
6. Animaciones
7. Temas previos a Post CSS
   - Sass
   - Stylus
   - Less
   - Bootstrap
   - Fountation
8. Post CSS
9. De jQuery a JavaScript
10. Fundamentos de JavaScript
11. Webpack
12. ReactJS
13. Redux
14. React Router

---
---
---

## HTML5

### Etiquetas

Las etiquetas son la representación básica de la información en un documento html. Sirven para crear y organizar el contenido.

La sintaxis general de una etiqueta es:

```JavaScript
<nombre> contenido </nombre>
```

Hay ciertas etiquetas que tienen una sintaxis diferente, ya que se cierran en sí mismas; es decir, no tienen etiqueta de cierre:

```JavaScript
<nombre />
```

Algunas de las etiquetas más conocidas, usadas y generales son:

- Etiquetas de cabecera (**head**)
  - _doctype_: indica al navegador el tipo de documento que se está mostrando.
  - _html_: es la etiqueta que envuelve todo el documento
  - _head_: es la cabecera del documento y contiene sub etiquetas que describen al documento o incluyen recursos adicionales.
- Etiquetas del cuerpo del documento (**body**):
  - _article_: diferencia partes del contenido que pueden vivir por sí mismas.
  - _nav_: para hacer menús de navegación.
  - _aside_: contenido menos relevante, como publicidad, etc.
  - _section_: sirve para diferenciar las secciones principales del contenido.
  - _header_: cabecera del documento.
  - _footer_: pie de página del documento.
  - _table_: tablas de contenidos, similar a la estructura de las hojas de calculo.
  - _ul_ y _ol_: listas de ítems.
  - _div_: cualquier división para organizar el contenido.

#### Otras etiquetas que operan a dar semántica más especifica

- **h1** - **h6**: títulos de nuestro sitio web.
- **p**: define el texto de un párrafo.
- **small**: aplica una apariencia de texto reducido en tamaño. En HTML5 `<small>`, este elemento es reutilizado para representar comentarios laterales y letra pequeña, incluyendo derechos de autor y texto legal, independientemente de su estilo de presentación.
- **strong**: aplica al texto un formato de negritas.
- **a**: corresponde a un ancla o enlace a una url interna o externa del documento.
- **img**: con esta etiqueta podemos enlazar imágenes en el documento.
- **figure**: le da un contexto semántico a las imágenes.

### Atributos HTML

Los atributos son valores agregados a las etiquetas (tags) html que extienden su habilidad o funcionalidad con información específica.

A continuación, un ejemplo de los atributos más comunes y usados en algunas etiquetas:

Para __img__:

- __src__: específica la ruta de la imagen que será mostrada a través de esta etiqueta. La ruta puede ser absoluta (cunado especifica una dirección exacta, incluyendo el prefijo http(s) ) o relativa (cuando la referencia a la ubicación de la imagen parte de la ubicación del archivo actual).
- __alt__: indica un texto alternativo que será mostrado en lugar de la imagen cuando ésta no pueda ser mostrada.
- __width__: ancho de la imagen en pixeles.
- __height__: alto de la imagen en pixeles.

Para link, en la cabecera head del documento:

- __rel__: indica la relación del recurso con el contenido.
- __type__: indica el tipo de recurso / formato.
- __href__: indica la ubicación (url) del recurso enlazado.

Para __meta__, también en la cabecera head del documento:

- __charset__: indica la tabla de caracteres (utf-8 para caracteres latinos) usada en el documento.

Para __a__:

- __href__: la ubicación o ruta a la que enlaza esta etiqueta de ancla. En el caso de querer enlazar a elementos que se encuentran dentro del mismo documento, este atributo debe indicar el valor del atributo `id` de ese elemento destino del enlace.
- __target__: es el atributo que le indica a los enlaces como abrir esa página, ya sea en la misma pestaña o en otra. Por defecto, abre en la misma pestaña, mas con `"_blank"` se abrirá en una nueva pestaña.

---

### Formularios HTML

Los Formularios en html son unidades de información que nos permiten recolectar información para enviarlos al propietario del website o a un servicio externo. Esta formado por dos partes o contextos: una parte donde se hace el ingreso y modelación de esos datos (en el frontend), y otra parte que se encarga de enviar, procesar y almacenar esos datos (en el backend).

Los formularios se crean con la etiqueta **form**. El atributo principal de un formulario es action, ya que contiene la ruta a la que serán enviados los datos recolectados.

Hay diversos elementos html que permiten la captura o recolección de datos, aunque generalmente se usan los elementos creados con la etiqueta `input`. Los inputs también sirven para crear botones, aunque existe una etiqueta especial para ésto llamada `button`... El atributo principal de los inputs es `type`, que indica el tipo de comportamiento o dato que se espera recibir.

Los elementos creados con la etiqueta `label` muestran un texto que se puede asociar con un input para darle mayor significado al campo, principalmente cuando no se usa el atributo `placeholder`.

---

### Navegación entre secciones

Es tan fácil como agregar un identificador único para una etiqueta concreta por medio del atributo `id="Lo-que-sea"` y luego por medio de una etiqueta de enlace con valor del atributo `href` apuntar al identificador deseado, ej:

```JavaScript
<a href="#lo-que-sea"></a>
```

---
---
---

## CSS3

### Formas de agregar estilos a HTML

Hay tres opciones para incluir estilos que definan la apariencia de tu html:

1. __Estilos en línea__: se definen directamente en el elemento html que quieres estilizar, se agregan con el atributo style.
2. __Estilos con el tag Style__: regularmente este tag se incluye dentro de la etiqueta head del html.
3. __Estilos enlazados desde un archivo css externo__: utilizando la etiqueta link que nos permite enlazar recursos externos.

A __CSS__, se le llama ___hojas de estilos en cascada___ porque los estilos que se definen para una página, se van aplicando de arriba hacia abajo, y de lo más general a lo más particular, teniendo prioridad lo más particular. Esto es, los estilos que prevalecen son los que han sido definidos en _línea_, luego los que fueron definidos mediante la etiqueta _style_ en la cabeza o cuerpo del html, y por último los estilos definidos en archivos externos enlazados con la etiqueta _link_.

Esa prioridad de los estilos css se puede alterar al usar el modificador `!important` en a definición de algún estilo en particular, aunque esto no es recomendado.

### Reglas, selectores, declaraciones, propiedades y valores

```css
/* Todo esto es una regla */
body { /* Selector. Ya sea de etiqueta expresa HTML, clase o id */
  /* Todo dentro de los corchetes es la declaración */
  /* El primero es la propiedad de ese selector, y todo lo segundo después del ':' es el valor(es) para esa propiedad */
  background-color: red;
}
```

Existen diferentes tipos de selectores, como ejemplo:

- Etiqueta simple: `header`, `p`, `nav`, `ol`, etc.
- Descendente: `section article ol li a`
- Por id, que son únicos: `#portafolio`
- Clases: `.ancho-general`
- Otros más sofisticados o complementarios que se veán luego.

[Selectors CSS3 - MDN web docs. EN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Selectors)

[Selectores CSS3 - MDN web docs. ES](https://developer.mozilla.org/es/docs/Web/CSS/Introducci%C3%B3n/Selectors)

### Los estilos incluidos por el navegador

Los navegadores incluyen estilos predeterminados para cada elemento html. Esto significa que aún cuando no hayas definido o asignado ningún estilo a tus etiquetas, éstas tendrán una apariencia particular que es muy similar en todos los navegadores, aunque no necesariamente idéntica.

---
---

## Agregando Clases a los componentes escritos en HTML

Para aplicar estilos a los componentes html, lo más común y recomendable es hacerlo a través de clases que se asignan al elemento html mediante el atributo class.

Un elemento html puede tener varias clases, se deben indicar en el mismo atributo `class` _pero separadas por un **espacio en blanco**_.

```css
/* Code CSS3 */
.container-general {
  width: 80%;
}

.backColor-red {
  background-color: red;
}
```

```html
<!-- Code HTML5 -->
<p class="container-general backColor-red">
  loremsum y todas las cosas lindas de la vida :V
</p>
```

Al escoger los nombres de clases, se debe tener en cuenta que se puedan aplicar a muchos elementos o a elementos particulares, así que la claridad y precisión en su identificación facilitará dar un contexto y mantenimiento en el futuro.

Algunos de los estándares más usados para la identificación de clases son:

- [OOCSS](https://www.keycdn.com/blog/oocss)
- [BEM](http://getbem.com/naming/)
- [Component CSS](https://www.sitepoint.com/introducing-ccss-component-css/)

## Colores en CSS

Los colores en CSS pueden ser representados de al menos tres formas diferentes:

- Representados con palabras claves para cada color, como: `red`, `green`, `blue`, `pink`, `yellow`, `black`, etc.
- Usando la composición de tres colores (rojo, verde y azul): para esto podemos usar notación hexadecimal o las funciones `rgb()` y `rgba()`
- Usando la composición mediante valores de Matiz, Saturación y Luminosidad con: `hls()` y `hlsa()`

```css
.box-colored-1 {
  color: white;
  background-color: rgba(10, 30, 80, 0.8);
  border-color: hsl(60, 65%, 20%);
}
```

> NOTA - __los valores hexadecimales__. cada color está representado por 6 dígitos, que representan 3 pares de hexadecimales FF - FF - FF (rojo, verde y azul), en el que cada par puede tomar valores hexadecimales entre 00 y FF. Cada uno equivale a valores decimales entre 0 y 255, donde 0 es la ausencia de ese color y 255 la mayor cantidad disponible. De esta manera cada color se forma por la combinación de diferentes proporciones de rojo, verde y azul.

> - #000000 es equivalente a Negro
> - #FF0000 es equivalente a Rojo
> - #00FF00 es equivalente a Verde
> - #0000FF es equivalente a Azul
> - #FFFFFF es equivalente a Blanco

## Unidades de medida

Hay varias unidades de medida con las que se puede trabajar en CSS: _**`px`**_, `%`, `em`, `rem`, `pt`, `fr`, `vw`, `vh`

Las medidas más comunes y utilizadas son los píxeles. Un píxel es la menor unidad homogénea en color que forma parte de una imagen digital. Es la unidad más práctica y fácil de utilizar y manipular; por esta razón en este curso será la que se utilice mayormente (`px`).

## Inspector de elementos

Para ver y depurar el código de una página html, los navegadores webs incluyen una herramienta llamada Inspector de elementos, o simplemente inspector. Éste abre una ventana con secciones que contiene una serie de espacios con información técnica muy detallada sobre todo lo que sucede en el DOM, incluídos los estilos que tienen aplicados cada uno de los elementos del html.

La mayoría de los navegadores incluye algún tipo de Inspector, en el curso usamos Google Chrome, pero la misma herramienta (o similar) la encuentras en Firefox, Opera, Edge, etc.

Utilizando el Inspector podemos hacer modificaciones (temporales) manualmente en el html de cualquier sitio web, consultar sus estilos y recursos enlazados, hacer pruebas en tiempo real con JavaSsript, monitor de variables o eventos entre muchas otras tareas útiles para cualquier desarrollador.
