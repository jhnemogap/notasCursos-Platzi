# Curso de React Router y Redux

**_Escuela de JavaScript - Platzi 2019_**

[Docs ReactJS - Multilingual](https://reactjs.org/)

---

---

# React Router

![React.svg](img-md/reactRouter-Redux-rroLogo.png)

Documentación:

- [Repositorio del paquete React Router](https://github.com/ReactTraining/react-router), desde este se puede ir a la documentación oficial del mismo.
- [React Router no es el único](https://es.reactjs.org/community/routing.html)
- Algunos enlaces en español para darse una idea rápida pero cuidado no están actualizados [2019-10-11]:
  - [Crear una app con React y React Router - 2017](https://platzi.com/blog/crear-una-app-con-react-y-react-router/)
  - [Usa React Router en tus aplicaciones de Reactjs - 2017](https://platzi.com/tutoriales/1199-react/2176-usa-react-router-en-tus-aplicaciones-de-reactjs/)
  - [Enrutando en React (React Router v4) - 2018](https://medium.com/@simonhoyos/enrutando-en-react-cd9e4ad6e3d3)
  - [React Router - Empezando con React Router](https://riptutorial.com/es/react-router)

## Qué es React Router

[React Router](https://github.com/ReactTraining/react-router) React Router es una popular y completa biblioteca de enrutado para React.js que mantiene la interfaz de usuario sincronizada con la URL. Admite la carga lenta de códigos, la correspondencia dinámica de rutas y el manejo de la transición de ubicación, y fue inspirado inicialmente por el enrutador de Ember.

Cuenta con 2 subdivisiones, una para la web (`react-router-dom`) y otra para desarrollo móvil (`react-router-native`).

Luego de la versión 4 en adelante, `react-router` cambia un poco su filosofía, haciendo diferenciación entre el enrutamiento estático que usaban anteriormente y el enrutamiento dinámico actual.

### Qué es enrutamiento estático

Este es el enrutamiento más común, si alguna vez hemos trabajado con rutas en algún otro lenguaje de programación o con algún otro framework, seguramente lo habremos hecho usando enrutamiento estático.

En este, las rutas son definidas al momento en que nuestra aplicación es inicializada. Es decir, antes que nuestra aplicación se renderice.

### Qué es enrutamiento dinámico

Este es el tipo de enrutamiento usado por `react-router`. A diferencia de el enrutamiento estático, este toma lugar en el momento en que nuestra aplicación se está renderizando. Esto gracias a que `react-router` hace uso de componentes para definir sus rutas.

Los componentes que se encargan de mostrar las diferentes rutas siempre renderizan. Algunas veces renderizan un componente y otras veces null, todo dependiendo de la locación.

## Componentes básicos de React Router

**React Router** nos provee todos los componentes necesarios para hacer que nuestra SPA (single page application) se mantenga en sincronía con nuestra locación actual.

`BrowserRouter`, `Route`, `Switch`, `Redirect`, y `Link`, son los componentes más básicos como obligatorios. Y son sólo algunos de los componentes que tenemos a nuestra disposición a la hora de trabajar con rutas en React.

Ahora que sabemos que React Router utiliza componentes, miremos algunos de ellos y que podemos hacer a través de algunos ejemplos.

### Component BrowserRouter

Es una envoltura para nuestra aplicación. Esta envoltura nos da acceso al API de historia de HTML5 para mantener nuestra interfaz gráfica en sincronía con la locación actual o URL. Debemos tener en cuenta que esta envoltura solo puede tener un hijo. Por lo general es `Switch`.

### Component Switch

Este componente, causa que solo se renderice el primer hijo `Route` o `Redirect` que coincida con la locación o URL actual. En el caso que no usemos `Switch` todas las rutas que cumplan con la condición se renderizarán.

### Component Route

Para definir las diferentes rutas de nuestra aplicación, podemos usar el componente `Route`. La función de este componente es elegir que renderizar según la locación actual. Este es el caso del que comentamos anteriormente, todos los componentes `Route` siempre renderizan, pero algunas veces renderizan un componente y otras veces retornan `null`.

```jsx
import React, { Component } from 'react';
import { BrowserRouter, Switch, Route } from 'react-router-dom';

export default class App extends Component {
  render() {
    return (
      <BrowserRouter>
        <Switch>
          <Route path='/' exact />
          <Route path='/index' exact />
          <Route path='/post/:id' />
        </Switch>
      </BrowserRouter>
    );
  }
}
```

En caso que la locación actual sea <www.dominio.com/index> se mostrara la segunda ruta en el ejemplo anterior, aunque en este caso no le estamos asignando ningún componente a renderizar cuando esto suceda.

Este componente recibe algunas propiedades como las siguientes, pero no las únicas:

- **`path`**: la ruta en la que se renderizará el componente en forma de cadena de texto
- **`exact`**: un booleano para definir si queremos que la ruta tiene o no que ser exacta para renderizar un componente. Ej: `/index !== /index/all`.
- **`strict`**: un booleano para definir si queremos que el último _slash_ sea tomado en cuenta para renderizar un componente. Ej: `/index !== /index/`.
- **`sensitive`**: un booleano para definir si queremos distinguir entre minúsculas y mayúsculas, y tomar esto en cuenta para renderizar un componente. Ej: `/index !== /Index`.
- **`component`**: recibe un componente a renderizar. Crea un nuevo elemento de React cada vez. Esto causa que el componente se monte y desmonte cada vez (no actualiza).
- **`render`**: recibe un método que retorna un componente. A diferencia de component no remonta el componente.
- **`children`**: funciona muy similar a render, pero con algunas adiciones.

Los tres métodos para renderizar el componente (propiedades de `Route`) nos permiten acceder a tres props adicionales. Estos 3 props contienen la _data_ del API de historia de HTML5 y estos son `match`, `location`, `history`.

Veamos un ejemplo [tomado de Medium por Simon Hoyos](https://medium.com/@simonhoyos/enrutando-en-react-cd9e4ad6e3d3).

```jsx
import React, { Component } from 'react';
import { BrowserRouter, Route, Switch, Redirect } from 'react-router-dom';
import NavBar from './NavBar/NavBar';
import Home from './Home/Home';
import Page1 from './Page1/Page1';
import Page2 from './Page2/Page2';
import PageError from './PageError/PageError';
import './App.css';

class App extends Component {
  render() {
    return (
      <BrowserRouter>
        <div>

          <NavBar />

          <Redirect
            from="/"
            to="/home"
          />

          <Switch>

            <Route
              path="/home"
              component={Home}
            />

            <Route
              exact
              path="/page1"
              render={() => <Page1 name="React Medellín" />}
            />

            <Route
              exact
              path="/page2"
              render={() => <Page2 />}
            />

            <Route component={PageError} />

          </Switch>

        </div>
      </BrowserRouter>
    );
  }
}

export default App;
```

Este ejemplo renderizará los componentes de la siguiente manera:

1. si la ruta es `/home` renderizará el componente `Home`.
2. si la ruta es exactamente `/page1` renderiza el componente `Page1`.
3. si la ruta ese exactamente `/page2` renderiza el componente `Page2`.
4. y si no es ninguna de las anteriores se renderizará el componente `PageError` para mostrar que ingresamos a una ruta no valida.

### Component Redirect

Podemos ver que en el ejemplo anterior usamos, además de los componentes que ya vimos, el componente `Redirect`. Este componente causa un re-direccionamiento a una ruta diferente a la actual. La nueva ruta a la que este nos dirige reemplaza la locación actual en la historia del navegador.

Redirect recibe las siguientes propiedades:

- **`from`**: una locación en forma de cadena de texto u objeto desde la cual se va a hacer el re-direccionamiento. Esta propiedad funciona de manera muy similar a la propiedad `path` de `Route`, cuando la locación coincide con `from` se ejecuta el `Redirect`.
- **`to`**: una locación en forma de cadena de texto u objeto hacía el cual se va a hacer el re-direccionamiento.
- **`push`**: un booleano que nos permite modificar el comportamiento de `Redirect`. Cuando este es verdadero en lugar de reemplazar la locación actual en la historia, este agrega una nueva locación.
- Al igual que `Route`, podemos usar las propiedades **`strict`** y **`exact`**.

En el ejemplo anterior si navegamos al `index` de la aplicación `/`, `Redirect` cambiara esa locación por `/home`. Y además renderizará el componente Route que coincida con esta ruta, en este caso renderiza `Home`.

### Component Link

Ya hemos configurado nuestras rutas, pero aún no tenemos forma de navegar por nuestra aplicación. Si queremos cambiar de un componente a otro nos tocaría navegar cambiando la URL de manera manual.

`Link` crea un hipervínculo que nos permite navegar por nuestra aplicación. Al contrario de `Redirect`, este agrega una nueva locación a la historia.

Recibe las siguientes propiedades:

- **`to`**: una locación en forma de cadena de text. Esta será la locación a la que navegaremos cuando le damos click a un hipervínculos.
- **`replace`**: un booleano que nos permite modificar el comportamiento de `Link`. Cuando este es verdadero en lugar de agregar una nueva locación a la historia, este reemplaza la locación actual.

```jsx
import React, { Component } from 'react';
import { Link } from 'react-router-dom';
import './NavBar.css';

class NavBar extends Component {
  render() {
    return (
      <div className="NavBar">
        <div className="link-container">
          <Link to="/page1" className="link">Página 1</Link>
        </div>
        <div className="link-container">
          <Link to="/page2" className="link">Página 2</Link>
        </div>
      </div>
    );
  }
}

export default NavBar;
```

---

---

## Instalación React Router

Si estás empezando la escuela de JavaScript desde este curso deberás crear una copia del repositorio de Platzi Video:

```bash
git clone https://github.com/platzi/PlatziVideo.git
```

Si ya tenias el repositorio del curso previo [Curso Práctico de React JS](https://platzi.com/clases/react-ejs/) o lo has clonado, crea una nueva rama para trabajar en ella a lo largo del curso, ejemplo:

```bash
git checkout -b feature/router-redux
```

Si el proyecto es clonado o no se ha ejecutado previamente, recomiendo probar que funciona adecuadamente, al igual que el previo Curso Práctico de React JS.

1. `npm install`
2. En una terminal ejecutar la _fake API_:
   - `json-server initialState.json`
   - O su variante local: `node_modules/.bin/json-server initialState.json`
3. En una segunda terminal el servidor de desarrollo:
   - `npm run start`

El resultado deberías ser muy similar al siguiente.

![Resultado Curso Práctico de React JS](img-md/practico-ReactJS_final.png)

Continuemos. Ya que nos encontramos dentro de la rama vamos a instalar _React Router_, la librería que nos va a permitir manejar rutas dentro de nuestra aplicación:

```bash
npm install --save react-router-dom

# o usando yarn
yarn add react-router-dom
```

Iremos viendo todo sobre el proyecto de Platzi Video.

## Crear nuestro archivo de Rutas

Dentro de nuestro proyecto vamos a crear un nuevo archivo llamado `./src/routes/App.js` donde vamos a ir añadiendo las rutas que necesitemos en la aplicación.

Las rutas que añadamos debemos definirlas con el componente `<Route/>` y estas deben estar encapsuladas dentro del componente `<BrowserRouter> </BrowserRouter>` del paquete de `react-router-dom`.

Para [definir una ruta con el componente `<Route />`](reactRouter-y-Redux.md#Component-Route) debemos pasar las `props` de:

- `path` para indicar la url.
- `exact` si queremos que funcione única y exactamente con la url que le digamos.
- `component` para indicarle el componente que va a renderizar.

```js
import React from 'react';
import { BrowserRouter, Route } from 'react-router-dom';
import Home from '../containers/Home';

const App = () => {
  return (
    <BrowserRouter>
      <Route exact path='/' component={Home} />
    </BrowserRouter>
  );
};

export default App;
```

Seguidamente es necesario modificar la dirección (`path`) en la importación del `Àpp.js` de `./containers/App` por `/routes/App.js` en el archivo `index.js`

```jsx
import App from './routes/App';
```

## Container Home

El contenedor previo `./src/containers/App.jsx` se renombra a `./src/containers/Home.jsx`, de está forma ahora si el `Home.jsx` se comporta como un contenedor esperando a que la aplicación lo enrute para ser renderizado. Y dentro de su código se reemplaza las tres coincidencias de la palabra `APP` por `Home`.

```jsx
// . . .
const Home = () => {
  // . . ..
    <div className='Home'>
      // . . ..
    </div>
  // . . ..
};
export default Home;
```

> **NOTA**: no olvidar ejecutar la fake API como se describió anteriormente.

## Container Login

Vamos a descargar el [proyecto del curso de Frontend de escuela de JavaScript](https://github.com/platzi/curso-frontend-escuelajs) para crear los componentes que necesitaremos.

---

> ¡Importante! configuración de `webpack.config.js`

Debemos modificar nuestra configuración del entorno de desarrollo local para que pueda funcionar con el uso de rutas, debemos ir al archivo `webpack.config.js` y añadir este fragmento de código antes de plugins:

```json
module.exports = {
  {/*...*/}
  devServer: {  
    historyApiFallback: true,  
  },
  {/*...*/}
};
```

> Luego del cambio se debe reiniciar la ejecución del servidor de desarrollo, para que tome los cambios de configuración.

---

Creamos un nuevo contenedor para el _login_ en `./src/containers/login.jsx`.

En principio no es muy pulido pues tiene presencia de componente mezclado directamente en un contenedor, pero para los fines prácticos del curso va bien.

```jsx
import React from 'react';

import googleIcon from '../assets/static/google-icon.png';
import twitterIcon from '../assets/static/twitter-icon.png';

import '../assets/styles/components/Login.scss';

const Login = () => {
  return (
    <section className='login'>
      <section className='login__container'>
        <h2>Inicia sesión</h2>
        <form className='login__container--form' id='form-login'>
          <input
            className='input'
            type='text'
            placeholder='Correo'
          />
          <input
            className='input'
            type='password'
            placeholder='Contraseña'
          />
          <button
            className='button'
            type='button'
          >
            Iniciar sesión
          </button>

          <div className='login__container--remember-me'>
            <label htmlFor='c-box'>
              Recordarme
              <input
                type='checkbox'
                id='c-box'
                value='first_checkbox'
              />
            </label>
            <a href='/recover-password'>Olvidé mi contraseña</a>
          </div>
        </form>
        <section className='login__container--social-media'>
          <div>
            <img src={googleIcon} alt='googleIcon' />
            Inicia sesión con Google
          </div>
          <div>
            <img src={twitterIcon} alt='twitterIcon' />
            Inicia sesión con Twitter
          </div>
        </section>
        <p className='login__container--register'>
          No tienes ninguna cuenta
          <a href='/register'>Regístrate</a>
        </p>
      </section>
    </section>
  );
};

export default Login;
```

Agregamos los estilos visuales en `./src/assets/styles/components/Login.scss`.

```scss
.login {
  background-image: linear-gradient(#21c08b, #8f57fd);
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: center;
  padding: 0px 30px;
  min-height: calc(100vh - 200px); /* El ancho será igual al tamaño de todo el height menos 200px (100px del header + 100px del footer) */
}

.login__container {
  background-color: rgba(255,255,255,0.1);
  border: 2px solid white;
  border-radius: 40px;
  box-shadow: 0 14px 28px rgba(0,0,0,0.25), 0 10px 10px rgba(0,0,0,0.22);
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  min-height: 700px;
  padding: 60px 68px 40px;
  width: 300px;
}

.login__container--form {
  display: flex;
  flex-direction: column;
}

.login__container--form label {
  font-size: 14px;
}

.login__container--remember-me {
  color: white;
  display: flex;
  justify-content: space-between;
  margin-top: 10px;
}

.login__container--remember-me a {
  color: white;
  font-size: 14px;
  text-decoration: none;
}

.login__container--remember-me a:hover {
  text-decoration: underline;
}

.login__container--social-media > div {
  align-items: center;
  display: flex;
  font-size: 14px;
  margin-bottom: 10px;
}

.login__container--social-media > div > img {
  margin-right: 10px;
  width: 30px;
}

.login__container--register {
  font-size: 14px;
}

.login__container--register a {
  color: white;
  font-weight: bold;
  font-size: 16px;
  text-decoration: none;
}

.login__container--register a:hover {
  text-decoration: underline;
}
```

Y para finalizar la presentación del _login_ agregamos las siguientes líneas al archivo `App.js` de la carpeta _routes_.

- Importamos el contenedor `Login`
- Luego del componente de ruta `{Home}` agregar el `Route` para `Login`.

```js
// . . .
import Login from '../containers/Login';
  // . . .
      <Route exact path='/login' component={Login} />
  // . . .
// . . .
```

Ya con todos estos cambios es posible ingresar manualmente la dirección <localhost:8080/login>; siendo posible ver el renderizado del contenedor Login.

## Container Register

Hacemos el mismo procedimiento para la vista del registro. Iniciando la creación de un archivo `./src/containers/Register.jsx` con el siguiente código.

```jsx
import React from 'react';
import '../assets/styles/components/Register.scss';

const Register = () => {
  return (
    <section className='register'>
      <section className='register__container'>
        <h2>Regístrate</h2>
        <form className='register__container--form'>
          <input className='input' type='text' placeholder='Nombre' />
          <input className='input' type='text' placeholder='Correo' />
          <input className='input' type='password' placeholder='Contraseña' />
          <button className='button' type='button'>Registrarme</button>
        </form>
        <a href='/login'>Iniciar sesión</a>
      </section>
    </section>
  );
};

export default Register;
```

Los estilos visuales en `./src/assets/styles/components/Register.scss`:

```scss
.register {
  background-image: linear-gradient(#21c08b, #8f57fd);
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: center;
  padding: 0px 30px;
  min-height: calc(100vh - 200px); /* El ancho será igual al tamaño de todo el height menos 200px (100px del header + 100px del footer) */
}

.register__container {
  background-color: rgba(255,255,255,0.1);
  border: 2px solid white;
  border-radius: 40px;
  box-shadow: 0 14px 28px rgba(0,0,0,0.25), 0 10px 10px rgba(0,0,0,0.22);
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  min-height: 600px;
  padding: 60px 68px 40px;
  width: 300px;
}

.register__container--form {
  display: flex;
  flex-direction: column;
}

.register__container a {
  color: white;
  font-size: 16px;
  text-align: center;
  text-decoration: none;
}

.register__container a:hover {
  text-decoration: underline;
}
```

Y finalmente añadiendo la nueva ruta en `App.js` que está en la carpeta de _routes_.

```js
// . . .
import Register from '../containers/Register';
// . . .
      <Route exact path='/register' component={Register} />
// . . .
```

## Container 404 Not Found

Es importante siempre tener una ruta que renderice un componente para las urls que no existan, debemos añadir esta ruta al final del `Switch` para que sea el caso por _default_.

Para este fin creamos un archivo en `./src/containers/NotFound.jsx` con una presentación simple.

```jsx
import React from 'react';

const NotFound = () => (
  <h1>Error 404 - Page Not Found</h1>
);

export default NotFound;
```

Y en archivo encargado de las rutas `Àpp.js` agregamos:

```js
import NotFound from '../containers/NotFound';
// . . .
        <Route component={NotFound} />
// . . .
```

## Usando Fragment para añadir más de un elemento

Si al componente presentacional anterior `<NotFound>` le agregamos un enlace para volver al inicio, podremos ver un error en el proyecto. Este inconveniente se solucionaba agregando un modo de encapsular como el `<div>` que no agrega valor pero evita el error.

En estos casos para no añadir elementos extra al DOM, podemos utilizar Fragment de 2 maneras:

- Añadiendo el componente `<React.Fragment> </React.Fragment>`
- O encapsulando elementos dentro de un simple `<> </>`

Siendo así, el componente `NotFound` con más de un elementos se vería así:

```jsx
import React from 'react';

const NotFound = () => (
  <>
    <h1>Error 404 - Page Not Found</h1>
    <h2>
      <a href='/'>Volver al principio</a>
    </h2>
  </>
);

export default NotFound;
```

## Usando el componente Switch de React Router

Si bien, al ejecutar las direcciones manualmente la aplicación nos traslada sin problemas a la vista adecuada. No es seguro dejar esto en las manos del destino, pues si existierá al menos dos rutas iguales se renderizaran las dos a la vez y otra ruta fallará. Igualmente se puede ver el efecto si existe una ruta por defecto para manejar enlaces no existentes.

Para evitar estos inconvenientes y que solamente se renderice la primera coincidencia se usa el componente de React Router `<Switch> </Switch>`.

Realicemos este cambio en el llamado a las rutas del archivo `Àpp.js`.

```js
import React from 'react';
import { BrowserRouter, Route, Switch } from 'react-router-dom';
import Home from '../containers/Home';
import Login from '../containers/Login';
import Register from '../containers/Register';

const App = () => {
  return (
    <BrowserRouter>
      <Switch>
        <Route exact path='/' component={Home} />
        <Route exact path='/login' component={Login} />
        <Route exact path='/register' component={Register} />
        <Route component={NotFound} />
      </Switch>
    </BrowserRouter>
  );
};

export default App;
```

## Componente: Layout

Para nuestra aplicación los componentes `Header` y `Footer` se podrían manejar de forma persistente pues son siempre los mismos en las diferentes vistas. Par esto creamos un componente que no cambie por cada enrutamiento.

En `/src/components/Layout.jsx`:

```jsx
import React from 'react';
import Header from './Header';
import Footer from './Footer';

const Layout = ({ children }) => {
  return (
    <div className='App'>
      <Header />
      {children}
      <Footer />
    </div>
  );
};

export default Layout;
```

Ahora, encapsulemos los containers con nuestro `Layout` modificando el archivo `App.js`.

```js
<BrowserRouter>
  <Layout>
    <Switch>
      <Route exact path='/' component={Home} />
      <Route exact path='/login' component={Login} />
      <Route exact path='/register' component={Register} />
      <Route component={NotFound} />
    </Switch>
  </Layout>
</BrowserRouter>
```

En este paso ya podemos ver los cambios, pero en el caso de la vista del `Home` este repite encabezado y pie de página. Aprovechando que debemos ir al contenedor `Home.jsx` y realicemos dos cambios.

1. Retiramos los componentes `Header` y `Footer`, de una vez las importaciones a los mismos.
2. Retiremos el llamado a los estilos generales y pasemoslos al enrutador `App.js`: `import '../assets/styles/App.scss';`

## Manejando enlaces y configuraciones - Link

El componente `<Link> </Link>` es similar a un elemento `<a></a>` ya que nos permite navegar dentro de la aplicación, pero sin la necesidad de tener que recargar la página. Para indicarle el destino simplemente debemos pasar el _prop_ `to='/mi-enlace'`.

Para poder usar este componente en cualquiera de los componentes o contenedores es necesario la importación desde el paquete del mismo, así:

```jsx
import { Link } from 'react-router-dom';
```

> NOTA: no olviden importar el componente `Link`.

### Component Link - component Header

```jsx
{/* ... */}
    <Link to='/'>
      <img className='header__img' src={logoHeader} alt='Platzi Video' />
    </Link>
    {/* ... */}
      <ul>
        <li>
          <Link to='/#'>Cuenta</Link>
        </li>
        <li>
          <Link to='/login'>Iniciar Sesión</Link>
        </li>
      </ul>
{/* ... */}
```

### Component Link - component Footer

```jsx
{/* ... */}

  <footer className='footer'>
    <Link to='/#'>Terminos de uso</Link>
    <Link to='/#'>Declaración de privacidad</Link>
    <Link to='/#'>Centro de ayuda</Link>
  </footer>

{/* ... */}
```

### Component Link - container Login

```jsx
{/* ... */}
        <div className='login__container--remember-me'>
            {/* ... */}
            <Link to='recover-password'>
              Olvidé mi contraseña
            </Link>
          </div>
        </form>
        {/* ... */}
        <p className='login__container--register'>
          No tienes ninguna cuenta
          <Link to='/register'>
            Regístrate
          </Link>
        </p>
{/* ... */}
```

### Component Link - container NotFound

```jsx
{/* ... */}
  <>
    <h1>Error 404 - Page Not Found</h1>
    <h2>
      <Link to='/'>Volver al principio</Link>
    </h2>
  </>
{/* ... */}
```

### Component Link - container Register

```jsx
{/* ... */}
  <Link to='/login'>Iniciar sesión</Link>
{/* ... */}
```

---

---

---

## Redux

![Logo de Redux](img-md/reactRouter-Redux-rdxLogo.png)

