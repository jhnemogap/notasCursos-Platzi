><link rel="stylesheet" type="text/css" media="all" href="styles.css">

# Curso de Desarrollo Web Online

## Introducción al desarrollo web

El desarrollo web tiene que ver con todo lo que percibimos a través del navegador: páginas, aplicaciones y sitios web como Facebook, Instagram y Twitter.

<em>Para comprender cómo funciona internet necesitamos conocer tres grandes conceptos:</em>

- **Clients** _(clientes)_: son los dispositivos a través de los cuales accedemos a los sitios web: un computador desktop, un teléfono, una laptop, etc.
- **Internet**: es toda la red formada por servidores y clientes que proveen y consumen contenidos web y se comunican entre sí a nivel global.
- **Server** _(servidor)_: es un computador, ubicado en alguna parte de la red, que está prendido todo el tiempo, en el que se alojan o almacenan sitios web y sus recursos y al cual se accede a través de nombres de dominio (.com, .net, .pe, etc.). También se les conoce como hosting.


#### Profesiones dentro del Desarrollo Web:

* **Frontend**: son los encargados de cuidar toda la apariencia y experiencia de usuario. Su misión es pasar todo el diseño gráfico de un sitio o aplicación web, a código, y proveer toda la interactividad a los clientes. Esta rama se puede subdividir en algunas especializaciones como: Arquitecto Frontend, Desarrollador JavaScript (frontend), etc.
* **Backend**: resguardan los datos y la seguridad de las aplicaciones y sitios web. Su misión es crear y mantener toda la parte del sitio web que sucede en los servidores. Pueden especializarse aún más en: SysAdmis, DevOps, Desarrollador JavaScript (backend), entre otros.

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
  + Sass
  + Stylus
  + Less
  + Bootstrap
  + Fountation
8. Post CSS
<br>
<br> Línea Final alternativa 2019 ...
9. De jQuery a JavaScript
9. Fundamentos de JavaScript
10. Webpack
11. ReactJS
12. Redux
13. React Router

---
---
---

# <span style="font-size: 2.0em">HTML5</span>

## Etiquetas
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

#### Otras etiquetas que operan a dar semántica más especifica:
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

<br>

---
---
---

# CSS3

## Formas de agregar estilos a HTML

Hay tres opciones para incluir estilos que definan la apariencia de tu html:

1. __Estilos en línea__: se definen directamente en el elemento html que quieres estilizar, se agregan con el atributo style.
1. __Estilos con el tag Style__: regularmente este tag se incluye dentro de la etiqueta head del html.
3. __Estilos enlazados desde un archivo css externo__: utilizando la etiqueta link que nos permite enlazar recursos externos.

A __CSS__, se le llama ___hojas de estilos en cascada___ porque los estilos que se definen para una página, se van aplicando de arriba hacia abajo, y de lo más general a lo más particular, teniendo prioridad lo más particular. Esto es, los estilos que prevalecen son los que han sido definidos en _línea_, luego los que fueron definidos mediante la etiqueta _style_ en la cabeza o cuerpo del html, y por último los estilos definidos en archivos externos enlazados con la etiqueta _link_. Esta prioridad se puede alterar al usar el modificador `!important` en la definición de algún estilo en particular, aunque esto no es recomendado.


### Reglas, selectores, declaraciones, propiedades y valores

```CSS
/*Todo esto es una regla*/
body { /*Selector. Ya sea de etiqueta expresa HTML, clase o id*/

  /*Ésta es una declaración*/
  /*El primero es la propiedad de ese selector, y todo lo segundo después del ':' es el valor(es) para esa propiedad*/
  background-color: red;
}
```

[Selectors CSS3 - MDN web docs. EN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Selectors)

[Selectores CSS3 - MDN web docs. ES](https://developer.mozilla.org/es/docs/Web/CSS/Introducci%C3%B3n/Selectors)

---

### Los estilos incluidos por el navegador
Los navegadores incluyen estilos predeterminados para cada elemento html. Esto significa que aún cuando no hayas definido o asignado ningún estilo a tus etiquetas, éstas tendrán una apariencia particular que es muy similar en todos los navegadores, aunque no necesariamente idéntica.

---
