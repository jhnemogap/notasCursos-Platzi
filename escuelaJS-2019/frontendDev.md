# Fronted Developer

## **_Escuela de JavaScript - Platzi 2019_**

--

## Tipos de errores en HTML, debugging y servicio de validación de etiquetas

[Markup Validation Service](https://validator.w3.org/#validate_by_uri)

## Arquitecturas CSS

Casos más usados:

- **OOCSS**: [An Introduction To Object Oriented CSS](https://www.smashingmagazine.com/2011/12/an-introduction-to-object-oriented-css-oocss/)
- **BEM**: [BEM Introduction](http://getbem.com/introduction/)
- **SMACSS**: [Scalable and Modular Architecture for CSS](http://smacss.com/)
- **ITCSS**: [Inverted Triangle CSS](https://www.xfive.co/blog/itcss-scalable-maintainable-css-architecture/)
- **Atomic Design**: [Atomic Design la intersección entre diseño y desarrollo](http://bradfrost.com/blog/post/atomic-web-design/)

## Pre-procesador

Más conocidos:

- SASS
- LESS
- STYLUS

height

## Instalación de SASS y configuración inicial

Instalación de SASS con NPM:

```bash
npm install -g sass
```

Si usas Windows puedes usar el gestor de paquetes Chocolatey Package Manager e instalar SASS con el siguiente comando:

```bash
choco install sass
```

Si usas Mac puedes usar Homebrew para instalar SASS con el siguiente comando:

```bash
    brew install sass/sass/sass
```

Ahora para realizar la conversión de un archivo .scss (sass) a el .css de toda la vida, se ejecuta el siguiente comando:

```bash
sass {Ruta-file-.scss (sass)} {Ruta-file-.css (css3)}
```

Pero, si se desea que la conversión sea automática se debe usar el parámetro `--watch` antes de la primera ruta:

```bash
sass --watch {Ruta-file-.scss (sass)} {Ruta-file-.css (css3)}
```

## Hablemos de variables, herencia, anidamiento, operadores y más

### Variables

Definimos la variable con `$nombreDeVariable`. Para usar nuestra variable por ejemplo en las etiquetas ancla:

```scss
$blanco : #fff;

a {
    color: $blanco
}
```

## Anidamiento

Para usar una regla de estilos dentro de otra:

```scss
.login__container-register {
font-size: 14px;
    a {
        color: $blanco;
        font-weight: bold;
        text-decoration: none;
    }
}
```

## Herencia

Definimos una regla de estilos:

```scss
.flex {
    display: flex;
    align-items: center;
}

.header {
    @extend .flex
    background-color: #000;
    height: 100px;
    width: 100%;
}
```

## Mixins

Se define el mixing con: `@mixin` nombre (_sin punto precediendo el nombre_)

```scss
@mixin flex {
    display: flex;
    align-items: center;
}

.header {
    @include flex;
    background-color: #000;
    height: 100px;
    width: 100%;
}
```
