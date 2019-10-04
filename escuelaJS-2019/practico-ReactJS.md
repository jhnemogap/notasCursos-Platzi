# Curso Práctico de React JS

## **_Escuela de JavaScript - Platzi 2019_**

---

---

Visiten esta página de la que no soy el autor pero cumple el mismo objetivo: _**[Curso Práctico de React JS by augdiaugus](https://augdiaugus.gitbook.io/recoleccion-de-notas-publicas/escuela-de-javascript/curso-practico-de-react-js)**_ Este blog usa en gran manera la [documentación de React en español](https://es.reactjs.org/docs/getting-started.html), solo colocaré la info mínima requerida para una consulta rápida de configuración y estado del arte.

---

---

## React

![React.svg](https://upload.wikimedia.org/wikipedia/commons/thumb/4/47/React.svg/245px-React.svg.png)

[Documentación de React.js en español](https://es.reactjs.org/)

**React** \(también llamada **React.js** o ReactJS\) es una biblioteca Javascript de código abierto diseñada para crear [interfaces de usuario](https://es.wikipedia.org/wiki/Interfaz_de_usuario) con el objetivo de facilitar el desarrollo de [aplicaciones en una sola página](https://es.wikipedia.org/wiki/Single-page_application). Es mantenido por [Facebook](https://es.wikipedia.org/wiki/Facebook) y la comunidad de [software libre](https://es.wikipedia.org/wiki/Software_libre), han participado en el proyecto más de mil desarrolladores diferentes [1](https://es.wikipedia.org/wiki/React#cite_note-infoworld-1)​.

Cada pequeña parte de nuestra página web la conoceremos como "Componente". Cada componente se encargará de una función en específico. Además, podremos reutilizar nuestros componentes siempre que lo necesitemos. Al unir todos nuestros componentes tendremos una página web que nos permite cambiar, actualizar o eliminar elementos de forma muy sencilla.

React intenta ayudar a los desarrolladores a construir aplicaciones que usan datos que cambien todo el tiempo. Su objetivo es ser sencillo, declarativo y fácil de combinar. React sólo maneja la [interfaz de usuario](https://es.wikipedia.org/wiki/Interfaz_de_usuario) en una aplicación; React es la **Vista** en un contexto en el que se use el patrón [MVC](https://es.wikipedia.org/wiki/Modelo%E2%80%93vista%E2%80%93controlador) (Modelo-Vista-Controlador) o [MVVM](https://es.wikipedia.org/wiki/Modelo%E2%80%93vista%E2%80%93modelo_de_vista) (Modelo-vista-modelo de vista). También puede ser utilizado con las extensiones de React-based que se encargan de las partes no-UI (que no forman parte de la interfaz de usuario) de una [aplicación web](https://es.wikipedia.org/wiki/Aplicaci%C3%B3n_web).

Según el servicio de análisis Javascript (en inglés "javascript analytics service"), Libscore, React actualmente está siendo utilizado en las páginas principales de Imgur, Bleacher Informe, [Feedly](https://es.wikipedia.org/wiki/Feedly), [Airbnb](https://es.wikipedia.org/wiki/Airbnb), SeatGeek, HelloSign, y otras.[2](https://es.wikipedia.org/wiki/React#cite_note-2)​

### Historia

React fue creada por Jordan Walke y publicada en mayo de 2013, un ingeniero de software en Facebook, inspirado por los problemas que tenía la compañía con el mantenimiento del código de los anuncios dentro de su plataforma. Enfocado en la experiencia del usuario y la eficiencia para sus programadores, influenciado por XHP (un marco de componentes de [HTML](https://es.wikipedia.org/wiki/HTML) para [PHP](https://es.wikipedia.org/wiki/PHP)), nace el prototipo ReactJS.

---

## DOM, Virtual DOM y React DOM

El DOM es el código HTML que se transforma en páginas web.

Cada vez que cambiamos alguna parte del DOM, también estamos actualizando el HTML con el que interactúan nuestros usuarios. El problema es que todas las operaciones, comparaciones y actualizaciones en el DOM son muy costosas.

El Virtual DOM es una herramienta que usan tecnologías como React y Vue para mejorar el rendimiento (_performance_) y velocidad de nuestras aplicaciones.

Es una copia exacta del DOM, pero mucho más ligera, ya que los cambios no actualizan el verdadero HTML de nuestras páginas web. Gracias al Virtual DOM podemos hacer operaciones y comparaciones de forma sumamente rápida.

Recuerda que los cambios en el Virtual DOM no afectan el HTML que ven los usuarios, así que debemos estar sincronizando constantemente las copias con el DOM. Pero no te preocupes, React DOM lo hace por nosotros.

### Qué es el DOM virtual

El DOM virtual (_VDOM_) es un concepto de programación donde una representación ideal o "virtual" de la IU se mantiene en memoria y en sincronía con el DOM "real", mediante una biblioteca como ReactDOM. Este proceso se conoce como [reconciliación](https://es.reactjs.org/docs/reconciliation.html).

Este enfoque hace posible la API declarativa de React: le dices a React en qué estado quieres que esté la IU, y se hará cargo de llevar el DOM a ese estado. Esto abstrae la manipulación de atributos, manejo de eventos y actualización manual del DOM que de otra manera tendrías que usar para construir tu aplicación.

Ya que "DOM virtual" es más un patrón que una tecnología específica, las personas a veces le dan significados diferentes. En el mundo de React, el término "DOM virtual" es normalmente asociado con [elementos de React](https://es.reactjs.org/docs/rendering-elements.html) ya que son objetos representando la interfaz de usuario. Sin embargo, React también usa objetos internos llamados _"fibers"_ para mantener información adicional acerca del árbol de componentes. Éstos pueden ser también considerados como parte de la implementación de "DOM virtual" de React.

### Es el Shadow DOM lo mismo que el DOM virtual

No, son diferentes. El Shadow DOM es una tecnología de los navegadores diseñada principalmente para limitar el alcance de variables y CSS en componentes web. El DOM virtual es un concepto que implementan bibliotecas en JavaScript por encima de las APIs de los navegadores.

### Qué es "_React Fiber_"

_Fiber_ es el nuevo motor de reconciliación en React 16. Su principal objetivo es permitir el renderizado incremental del DOM virtual. [Leer más](https://github.com/acdlite/react-fiber-architecture).

---

---

## Create React App

[Create React App](https://github.com/facebookincubator/create-react-app) es un ambiente cómodo para **aprender React**, y es la mejor manera de comenzar a construir **una nueva** [**aplicación de página única**](https://es.reactjs.org/docs/glossary.html#single-page-application) usando React.

**Create React App** configura tu ambiente de desarrollo de forma que puedas usar las últimas características de Javascript, brindando una buena experiencia de desarrollo, y optimizando tu aplicación para producción. Necesitarás tener Node &gt;= 8.10 y npm &gt;= 5.6 instalados en tu máquina. Para crear un proyecto de sitio web usando la plantilla por defecto de _`create-react-app`_, ejecutar:

```bash
npx create-react-app my-app

cd my-app

# Iniciar el servidor de desarrollo
npm start
```

> Nota: En la primera línea **`npx`** no es un error de escritura: Es una [herramienta de ejecución de paquetes que viene con npm 5.2+](https://medium.com/@maybekatz/introducing-npx-an-npm-package-runner-55f7d4bd282b).

_Create React App_ no se encarga de la lógica de `backend` o de bases de datos; tan solo crea un flujo de construcción para `frontend`, de manera que lo puedes usar con cualquier `backend`. Para ello internamente usa [Babel](https://babeljs.io/) y [webpack](https://webpack.js.org/), pero no necesitas saber nada de estas herramientas para usar Create React App.

Cuando estés listo para desplegar a producción, ejecuta `npm run build` lo cual crea una compilación optimizada de tu aplicación en el directorio `build`. Puedes aprender más acerca de **Create React App** [en su archivo README](https://github.com/facebookincubator/create-react-app#create-react-app--) y en la [Guía del Usuario](https://facebook.github.io/create-react-app/).

---

## Components React _Stateful_ y _Stateless_

Tomado de [Stateful and Stateless Components in React](https://programmingwithmosh.com/javascript/stateful-stateless-components-react/)

Revisaremos qué componentes con estado y sin estado se encuentran en React, cómo notar la diferencia y el complejo proceso de decidir si los componentes tienen estado o no.

### Revisión del estado

Primero, repasemos qué estado es.

En un componente, el estado son datos que importamos, generalmente para mostrar al usuario, que están sujetos a cambios. Podría cambiar porque la base de datos de la que estamos obteniendo puede actualizarse, el usuario la modificó, ¡hay muchas razones por las que los datos cambian!

```jsx
import React, { Component } from 'react';

class Stateful extends Component {
  constructor(props) {
    super(props);

    this.state = { hello: 'hello world' };
  }

  render() {
    return (
      <h1>{this.state.hello}</h1>
    );
  }
}

export default Stateful;
```

Otro ejemplo:

```jsx
import React, {Component} from 'react'

class Pigeons extends Component {
  constructor() {
    super()
    this.state = {
      pigeons: []
    }
  }

  render() {
    return (
      <div>
        <p>Look at all the pigeons spotted today!</p>
        <ul>
          {this.state.pigeons.map(pigeonURL => {
            return <li><img src={pigeonURL} /></li>
          })}
        </ul>
      </div>
    )
  }
}
```

Por lo general, también tendríamos un `componenteDidMount()` que tomaría nuestros datos de una base de datos, pero el ejemplo anterior debería darle una idea básica: tenemos estado y podemos representar cosas desde el estado.

### Componentes con estado y sin estado

Los componentes con estado y sin estado tienen muchos nombres diferentes. También son conocidos como:

- Componentes de contenedor vs presentación
- Componentes inteligentes vs tontos

La diferencia literal es que uno tiene estado y el otro no. Eso significa que los componentes con estado realizan un seguimiento de los **datos** cambiantes, mientras que los componentes sin estado imprimen lo que se les da a través de accesorios, o siempre representan lo mismo.

Componente con estado / contenedor / inteligente:

```jsx
class Main extends Component {
 constructor() {
   super()
   this.state = {
     books: []
   }
 }
 render() {
   <BooksList books={this.state.books} />
 }
}
```

Sin estado / Presentación / Componente tonto:

```jsx
const BooksList = ({books}) => {
 return (
   <ul>
     {books.map(book => {
       return <li>book</li>
     })}
   </ul>
 )
}
```

Observe que el componente sin estado (_stateless component_) se escribe como una función. Tan bueno como es el estado, siempre debe tratar de hacer que sus componentes sean lo más simples y sin estado posible, de modo que los diferentes componentes se puedan reutilizar como piezas de Lego, incluso si no tiene planes inmediatos para reutilizar un componente. ¡Los con estado _stateful_ deberían sentirse afortunados de ser así!

## Componentes Visuales

Conocidos en inglés como _Presentational Components_. Este tipo de componentes solo deben centrase y enfocar sus esfuerzos en como debe renderizarse la UI. Este tipo de componentes puede componerse de otros elementos visuales y suele incluir estilos y clases. Todos los datos implicados en su render se deben recibir a través de _props_, por lo que deben ser independientes de llamadas a servicios externos. Este tipo de componentes suelen ser de tipo _Stateless_ ya que no necesitan estado, y deben de gestionar las acciones pasándoselas a componentes padre a través de sus _props_.

**_Ejemplo:_**

```jsx
class Item extends React.Component {  
    render () {  
        return (  
            <li><a href='#'>{ this.props.valor }</a></li>  
        );  
    }  
}
```

---

## JSX: JavaScript + HTML

Estamos acostumbrados a escribir código HTML en archivos .html y la lógica de JavaScript en archivos `.js`. React usa JSX: una sintaxis que nos permite escribir la estructura HTML y la lógica en JavaScript desde un mismo lugar: **nuestros componentes**.

JSX produce "elementos" de React. Exploraremos como renderizarlos en el DOM en la  [siguiente sección](https://es.reactjs.org/docs/rendering-elements.html). A continuación puedes encontrar lo básico de JSX que será necesario para empezar.

### Por qué JSX

React acepta el hecho de que la lógica de renderizado está intrínsecamente unida a la lógica de la interfaz de usuario: cómo se manejan los eventos, cómo cambia el estado con el tiempo y cómo se preparan los datos para su visualización.

En lugar de separar artificialmente  _tecnologías_  poniendo el esquema y la lógica en archivos separados, React  [separa  _intereses_](https://es.wikipedia.org/wiki/Separaci%C3%B3n_de_intereses)  con unidades ligeramente acopladas llamadas "componentes" que contienen ambas. Volveremos a los componentes en  [otra sección](https://es.reactjs.org/docs/components-and-props.html).

**React  [no requiere](https://es.reactjs.org/docs/react-without-jsx.html)  usar JSX**, **pero** la mayoría de la gente lo encuentra útil como ayuda visual cuando trabajan con interfaz de usuario dentro del código Javascript. Esto también permite que React muestre mensajes de error o advertencia más útiles.

**_Ejemplo principal_**:

- Crear una carpeta llamada `components` dentro de `src`.
- Crear un nuevo componente en un archivo de extensión `.jsx` (_HolaMundo.jsx_).
- Codear el nuevo componente:

  ```jsx
  import React from 'react';

  const HolaMundo = () => {
      const Hello = '¡Hola Mundo!';
      const isTrue = true;
      return(
          <div className="HolMundo">
              <h1>{Hello}</h1>
              <h2>Curso esencial de React</h2>
              {isTrue ? <h4>Esto es verdadero</h4> : <h5>Soy falso</h5>}
              {isTrue && <h4>Soy verdadero x2</h4>}
              <img src="https://cdn.auth0.com/blog/react-js/react.png" alt="logo React.js"/>
          </div>
      );
  };

  export default HolaMundo;
  ```

- En el `index.js` importar el componente y modificar así:

  ```js
  import HolaMundo from "./components/HolaMundo";
  . . .
  ReactDOM.render(<HolaMundo />, document.getElementById('root'));
  ```

- Correr el servidor de desarrollo local: `npm run start`

**NOTA 1:**
> dentro de React JS se usa clases de CSS por lo que al usar código HTML en cambio de `class` se cambia a `className`, esto por que la palabra `class` es reservada del lenguaje de programación.

**NOTA 2:**
> toda etiqueta de HTML que se de apertura debe cerrarse. Aun cuando parece obvio, esta nota es sobre todo para etiquetas como `<input />` o `<img />`.

**NOTA 3:**
> No pongas comillas rodeando llaves cuando insertes una expresión JavaScript en un atributo. Debes utilizar comillas (para los valores de los strings) o llaves (para las expresiones), pero no ambas en el mismo atributo.

### JSX representa objetos

Babel compila JSX a llamadas de  `React.createElement()`.

Estos dos ejemplos son idénticos:

```jsx
const element = (
  <h1 className="greeting">
    Hello, world!
  </h1>
);
```

```jsx
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);
```

`React.createElement()`  realiza algunas comprobaciones para ayudarte a escribir código libre de errores, pero, en esencia crea un objeto como este:

```jsx
// Nota: Esta estructura está simplificada
const element = {
  type: 'h1',
  props: {
    className: 'greeting',
    children: 'Hello, world!'
  }
};
```

Estos objetos son llamados "Elementos de React". Puedes pensar en ellos como descripciones de lo que quieres ver en pantalla. React lee estos objetos y los usa para construir el DOM y mantenerlo actualizado.

Vamos a explorar el renderizado de los elementos de React al DOM en la siguiente sección.

> **Tip:**
> Recomendamos usar la  [Definición del lenguaje en "Babel"](https://babeljs.io/docs/editors)  en tu editor de elección para que tanto el código en ES6 como el código en JSX sea resaltado apropiadamente. Este sitio web utiliza el esquema de color  [Oceanic Next](https://labs.voronianski.com/oceanic-next-color-scheme/), el cual es compatible con esto.

---

## _Props_: Comunicación entre Componentes

Las _Props_ son la forma de enviar y recibir información en nuestros componentes. Son la forma de comunicar cada componente con el resto de la aplicación. Son muy parecidas a los parámetros y argumentos de las funciones en cualquier lenguaje de programación.

```jsx
// Button.jsx -> _component_
import React from 'react';

const Button = (props) => {
  return (
    <div>
      <button type="button">{props.text}</button>
    </div>
  );
};

export default Button;
```

```jsx
// index.jsx
import React from 'react';
import Button from './components/Button';

ReactDOM.render(
  <Button text="¡Hola!"/>, document.getElementById('root'),
);
```

Para conocer más sobre **[Componentes y propiedades - React.js](https://es.reactjs.org/docs/components-and-props.html)**

---

## _State_ y _Events_

React nos permite responder a las interacciones de los usuarios con propiedades como onClick, onChange, onKeyPress, onFocus, onScroll, entre otras.

Estas propiedades reciben el nombre de la función que ejecuta el código que responde a las interacciones de los usuarios. Seguramente, esta función usará la función this.setState para actualizar el estado de nuestro componente.

```jsx
import React from "react";

class Button extends React.Component {
  state = { count: 0 }

  handleClick = () => (
     this.setState({ count: this.state.count + 1 })
  );

  render() {
    const { count } = this.state;

    return (
      <div>
        <h1>Manzanas: {count}</h1>
        <button type="button" onClick={this.handleClick}>
          Sumar
        </button>
      </div>
    );
  }
}

export default Button;
```

¡Recuerda que los nombres de estos eventos deben seguir la nomenclatura _camelCase_!, primera palabra en minúsculas, iniciales de las siguientes palabras en mayúsculas y el resto también en minúsculas.

No olvides revisar una documentación excelente sobre **[Estado y ciclo de vida - React.js](https://es.reactjs.org/docs/state-and-lifecycle.html)**

---

---

## Instalación y configuración de entorno

- Crear la carpeta del proyecto, obvio pero es mejor recordarlo `mkdir PlatziVideo` (e ingresar en la carpeta `cd PlatziVideo`).

- Todo desarrollador profesional lo primero que debe hacer es iniciar su repositorio local, en este caso con **[GIT](https://github.com/Nemo1Co/notasCursos-Platzi/blob/master/fundamentos-programacion/git-github.md)** y eventualmente en su repositorio online.

- **[Inicializar un proyecto de Node.js](https://docs.npmjs.com/cli/init#description)** generando un archivo `package.json` sin tener que hacer preguntas:

```bash
npm init -y
```

- Seguidamente instalar lo esencial para el proyecto con React.js, que sería:

```bash
// La bandera --save es usada por defecto si no se coloca
npm install --save react react-dom

npm install react react-dom
```

### ![Babel.js - (compilador)](https://upload.wikimedia.org/wikipedia/commons/thumb/0/02/Babel_Logo.svg/250px-Babel_Logo.svg.png)

**Babel** es un compilador de JavaScript gratuito y de código abierto que se utiliza principalmente para convertir el [código ECMAScript 2015+](https://en.wikipedia.org/wiki/ECMAScript#6th_Edition_-_ECMAScript_2015 "ECMAScript") (ES6 +) en una versión de JavaScript compatible con versiones anteriores que pueden ejecutar los [motores JavaScript](https://en.wikipedia.org/wiki/JavaScript_engine "JavaScript engine") más antiguos . Babel es una herramienta popular para usar las funciones más nuevas del lenguaje de programación JavaScript. [[3]](https://en.wikipedia.org/wiki/Babel_(compiler)#cite_note-3)

_En resumen_, Babel es una herramienta muy popular para escribir JavaScript moderno y transformarlo en código que pueda entender cualquier navegador.

Instalación de Babel y otras herramientas para que funcione con React, con la bandera `save-dev` le indicará al proyecto que estas dependencias son sólo para desarrollo:

```bash
npm install --save-dev @babel/core @babel/preset-env @babel/preset-react babel-loader
```

- `@babel/core`: las herramientas para convertir el JavaScript moderno
- `babel-loader`: se encarga de trabajar con _webpack_
- `@babel/preset-env`: ayudar a entender y transformar JS ES5+ y ES6+
- `@babel/preset-react`: ayudar a entender y transformar JSX y React.js

Configuración de Babel (`.babelrc` en la raíz del directorio): Luego configuramos `.babelrc` para implementar el uso de **`@babel/preset-env`** que es para usar javascript moderno y **`@babel/preset-react`** que es para usarlo junto con React.

```json
{
  "presets": [
    "@babel/preset-env",
    "@babel/preset-react"
  ],
}
```

### ![Webpack](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c1/Webpack.png/100px-Webpack.png)

**Webpack** (estilizado **webpack** ) es un [código abierto](https://en.wikipedia.org/wiki/Open-source_software "Software de código abierto") [de JavaScript](https://en.wikipedia.org/wiki/JavaScript "JavaScript") módulo bundler. [[2]](https://en.wikipedia.org/wiki/Webpack#cite_note-2) [[3]](https://en.wikipedia.org/wiki/Webpack#cite_note-3) [[4]](https://en.wikipedia.org/wiki/Webpack#cite_note-4) [[5]](https://en.wikipedia.org/wiki/Webpack#cite_note-5) [[6]](https://en.wikipedia.org/wiki/Webpack#cite_note-6) Es un paquete de módulos principalmente para JavaScript, pero puede transformar activos front-end como HTML, CSS e imágenes si se incluyen los complementos correspondientes. [[7]](https://en.wikipedia.org/wiki/Webpack#cite_note-7) Webpack toma módulos con dependencias y genera activos estáticos que representan esos módulos. [[8]](https://en.wikipedia.org/wiki/Webpack#cite_note-8)

#### Dependencias a usar

```json
"devDependencies": {
  "html-loader": "^0.5.5",
    "html-webpack-plugin": "^3.2.0",
    "webpack-cli": "^3.3.9"
  }
```

Vamos a configurar **webpack** con el archivo `webpack.config.js` en la raíz de nuestro proyecto.

```js
const path = require("path");
const HtmlWebpackPlugin = require("html-webpack-plugin");

module.exports = {
  entry: "./src/index.js",
  output: {
    path: path.resolve(__dirname, "dist"),
    filename: "bundle.js"
  },
  resolve: {
    extensions: [".js", ".jsx"]
  },
  module: {
    rules: [
      {
        test: /\.(js|jsx)$/,
        exclude: /node_module/,
        use: {
          loader: "babel-loader"
        }
      },
      {
        test: /\.html$/,
        use: [
          {
            loader: "html-loader"
          }
        ]
      }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: './public/index.html',
          filename: './index.html'
      })
  ]
};
```

Configuramos en nuestro `package.json` el siguiente *script*:

```json
"scripts": {
  "test": "echo \"Error: no test specified\" && exit 1",
    "build": "webpack --mode production"
  }
 ```

Corremos nuestro copilador con `npm run build` para que se aloje el la carpeta `dist`.

#### webpack-dev-server

Use [webpack](https://webpack.js.org/) con un servidor de desarrollo que proporcione recarga en vivo. Esto debe usarse **solo** para el **desarrollo** .

Utiliza [webpack-dev-middleware](https://github.com/webpack/webpack-dev-middleware) debajo del capó, que proporciona acceso rápido en memoria a los activos del paquete web.

##### Empezando

Primero lo primero, instale el módulo:

npm install webpack-dev-server --save-dev

_Nota: Si bien puede instalar y ejecutar webpack-dev-server a nivel mundial, recomendamos instalarlo localmente. webpack-dev-server siempre usará una instalación local sobre una global._

###### Uso

Hay dos métodos principales recomendados para usar el módulo:

###### Con la CLI

La forma más fácil de usarlo es con la CLI. En el directorio donde `webpack.config.js`está, ejecute:

node_modules / .bin / webpack-dev-server

_**Nota** : Muchas opciones de CLI están disponibles con `webpack-dev-server`. Explore este [enlace](https://webpack.js.org/configuration/dev-server/) ._

###### Con scripts NPM

Los scripts package.json de NPM son un medio conveniente y útil para ejecutar binarios instalados localmente sin tener que preocuparse por sus rutas completas. Simplemente defina un script como tal:

```js
" scripts " : { " start: dev " : " webpack-dev-server " }
```

Y ejecute lo siguiente en su terminal / consola:

npm run start: dev

NPM hará referencia automática al binario `node_modules`para usted y ejecutará el archivo o comando.

###### El resultado

Cualquiera de los métodos iniciará una instancia del servidor y comenzará a escuchar las conexiones desde `localhost`el puerto `8080`.

webpack-dev-server está configurado de manera predeterminada para admitir la recarga en vivo de archivos mientras edita sus activos mientras el servidor se está ejecutando.

Consulte [**la documentación**](https://webpack.js.org/configuration/dev-server/#devserver) para obtener más casos de uso y opciones.


### sass-loader

Carga un archivo Sass / SCSS y lo compila en CSS.

#### Empezando

Para comenzar, deberá instalar `sass-loader`:

```bash
npm install sass-loader nodo-sass webpack --save-dev
```

El sass-loader requiere que instales [Node Sass](https://github.com/sass/node-sass) o [Dart Sass](https://github.com/sass/dart-sass) por tu cuenta (puedes encontrar más documentación a continuación). Esto le permite controlar las versiones de todas sus dependencias y elegir qué implementación de Sass usar.

- [node sass](https://github.com/sass/node-sass)
- [dat sass](http://sass-lang.com/dart-sass)

Encadene el sass-loader con el [css-loader](https://github.com/webpack-contrib/css-loader) y el [style-loader](https://github.com/webpack-contrib/style-loader) para aplicar inmediatamente todos los estilos al DOM o al [mini-css-extract-plugin](https://github.com/webpack-contrib/mini-css-extract-plugin) para extraerlo en un archivo separado.

Luego agregue el cargador a su `webpack`configuración. Por ejemplo:

**file.js**

```js
import style from './style.scss';
```

**file.scss**

```css
$body-color: red;

body {
  color: $body-color;
}
```

**webpack.config.js**

```js
module.exports = {
  module: {
    rules: [
      {
        test: /\.s[ac]ss$/i,
        use: [
          // Creates `style` nodes from JS strings
          'style-loader',
          // Translates CSS into CommonJS
          'css-loader',
          // Compiles Sass to CSS
          'sass-loader',
        ],
      },
    ],
  },
};
```

Y corre a `webpack`través de tu método preferido.

## Platzi Video

-> +++++++++++++++++++++++++++++++++++++++++++

- ***Directorio de trabajo***:
  - **LICENSE**
  - **README . md** (_no tan opcional_)
  - **.nvmrc** (_determina el entorno de Node.js_)
  - **.babelrc**
  - **package.json** (_archivo de configuración y reconocimiento_)
  - **package-lock.json** (_maneja el versionado de las dependencias_)
  - **.gitignore**
  - Carpeta **public**:
    - **index.html**
  - Carpeta **src**:
    - **index.js**
    - Carpeta **component**:
      - **files.**jsx****

Luego en el `index.html` agregamos para este ejemplo un esquema mínimo:

```html
<!DOCTYPE html>
<html lang="es">
  <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Platzi Video</title>
</head>
<body>
  <main id="app"></main>
</body>
</html>
```
