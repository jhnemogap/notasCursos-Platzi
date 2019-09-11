# Prework: Buenas Prácticas y Entorno de Desarrollo

## ___Escuela de JavaScript 2019 - Platzi___

---

## Configurando la terminal o consola de comandos

Páginas web de los instaladores:

1. [Hyper Terminal](https://hyper.is/)
2. [Zsh](https://github.com/robbyrussell/oh-my-zsh/wiki/Installing-ZSH)
3. [oh my zsh](https://ohmyz.sh/)

[Lleva tu terminal al siguiente nivel - Platzi](https://platzi.com/blog/lleva-tu-terminal-al-siguiente-nivel/) by demian

***Ubuntu, Debian & derivatives (Windows 10 WSL | Native Linux kernel with Windows 10 build 1903***
Por la facilidad de homogenizar en linux, se puede instalar la terminal **Hyper**, pero sin dudas en la terminal normal con instalar **Zsh** y **oh my zsh** va ir de perlas el resto de la escuela JS. M. Windows si debe instalar **Hyper**.

- Descargar e instalar:
  - [Hyper Terminal](https://hyper.is)
- Instalar Zsh, usando en manejador de paquetes del sistema (`apt`, `apt-get`, `pacman`, etc.):
  - `sudo apt install zsh`
- To set zsh as your default shell, run this command:
  - `sudo chsh -s $(which zsh)`
- Log out and login back again to use your new default shell.
- Test that it worked with `echo $SHELL`. Expected result: `/bin/zsh` or similar.

***MacOS***
También se tiene terminal adecuada por defecto. Para más detalles mirar los videos del curso de Platzi . . . no conozco MacOS. Si alguien probo la instalación en MacOS y quiere darnos su listado de paso genial.

- Try `zsh --version` before installing it from Homebrew. If not:
  - `brew install zsh zsh-completions`
- To set zsh as your default shell, execute any of the following:
  - `chsh -s $(which zsh)`
  - `chsh -s /bin/zsh`
- Log out and login back again to use your new default shell.
- Test that it worked with `echo $SHELL`. Expected result: `/bin/zsh` or similar.
- Assuming you have Homebrew installed. If not, most versions of macOS ship zsh by default, but it's normally an older version. Alternatively, you may also use [MacPorts](https://www.macports.org/):
  - `sudo port install zsh zsh-completions`

**Basic Installation _Oh My Zsh_ in All O.S.**
Oh My Zsh is installed by running one of the following commands in your terminal. You can install this via the command-line with either `curl` or `wget`.

via curl:

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

via wget:

```bash
sh -c "$(wget -O- https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

[Configuración de este framework para Zsh](https://github.com/robbyrussell/oh-my-zsh#using-oh-my-zsh)

---

## Manejo archivos y directorios desde la terminal

__Comandos básico en la terminal - _tipo Unix___

- __clear__: limpia la pantalla de la terminal. También se puede usar `Ctrl + l`.
- __history__: Muestra el histórico de todos los comandos que hemos ejecutado. Para ejecutar un comando previo del historial existen dos formas básicas:
  1. Usar las fechas de navegación del teclado _arriba_ y _abajo_ para buscar comandos previos.
  2. Conociendo el número de ejecución en el archivo __history__, se ejecuta con un signo de admiración y el numero: __`!134`__

### Listar archivos

- __ls__: permite listar los archivos y directorios que se encuentren dentro de la carpeta en la que estamos ubicados, podemos pasar distintos parámetros a este comando, ejemplo `ls -la`:
  - __a__: ver los archivos ocultos.
  - __l__: lista los contenidos mostrando sus permisos y propiedades. Algunos comandos sólo operan acompañados, ej:
    - __lt__: lista los contenidos según su fecha de modificación.
    - __lh__: indica el tamaño del elemento en una presentación más "humana" - fácil.

### Navegar entre carpetas

- __pwd__: retorna la ruta absoluta en la cual nos encontramos.
- __cd__: nos sitúa en la carpeta que le indiquemos, existe tres casos especiales por defecto:
  - __.__: refiere a la carpeta en la cual se está ubicados.
  - __..__: se refiere a la carpeta padre de la actual ubicación.
  - __~__: se ubica en la carpeta home de la computadora

### Creación, modificación y eliminación de archivos o carpetas

- __mkdir__: crea una carpeta con el nombre indicado, ej: `mkdir docsPlatzi`
- __touch__: crea un archivo vacío con el nombre que le indiquemos. Ej: `touch file.txt`
- __mv__: permite mover archivos entre distintas carpetas, se debe indicar el nombre del archivo y la ruta de destino.
- __rm__: elimina únicamente un archivo, añadiendo el parámetro `-rf` puede eliminar directorios también.
- __rmdir__: elimina directorios pero sólo si está vacío.
- __nano__ o __vim__: es un editor dentro de la consola, permite abrir cualquier archivo y modificarlo.

### Visualizar y abrir archivos en terminal

- __cat__: permite visualizar un archivo completo en la terminal.
  - para copiar: `cat file.txt > file-copy.txt`
- __more__ (en M.W. puede ser __less__): muestra por partes un archivo dentro de la terminal.
- __tail__: muestra las últimas 10 líneas de cada archivo, se puede modificar pasándo el parámetro con el número de líneas _-15_ y luego el archivo.
- __open__ (en M.W. puede ser __explorer__): abre un archivo con el programa que tengamos por defecto, puede o no ser de texto plano (fotos, videos, texto, etc.).

---
---

## NodeJS

Tomado de [Cómo instalar NodeJS](https://platzi.com/clases/1650-prework/21971-como-instalar-node-1/)

### Revisión de Node en nuestro sistema

En la mayoría de sistemas basados en Unix ya viene instalado por defecto Node, para asegurarnos de que esté instalado debemos irnos a nuestra terminal de comandos y ejecutar:

```bash
$ node -v
> v12.4.0
```

Debería mostrar la versión de node que tenemos instalados en el sistema, como el ejemplo anterior, pero si la respuesta que obtenemos es como la siguiente, significa que se debe instalar:

```bash
node -v command not found: node
```

### Descargar e instalar

[Downloads node js](https://nodejs.org/en/download/)

- ***GNU/Linux***: binario, fuente de código, o como nos gusta a muchos package manager.
- ***M. Windows***: descargar y lo típico, siguiente, siguiente, ..., finalizar.
- ***MacOS***: se sugiere desde el package manager [homebrew](https://brew.sh/index). Una vez se tiene instalado _homebrew_ solo se ejecuta en la terminal: `$ brew install node`

### Cómo ejecutar NodeJS

Una vez se tenga instalado Node en el sistema podemos hacer uso de él. Al escribir `node` en la terminal se abrirá un shell interactivo donde escribir código en JavaScript. Esta herramienta es esencial en el desarrollo porque es aquí donde probar funcionalidades antes de insertarlas en un proyecto.

Sólo para verificar que funciona se ejecutará en la terminal lo siguiente:

```javascript
$ node

> console.log('Hola mundo')
Hola mundo
>
```

### Cómo utilizar npm

**npm** es el manejador de paquetes de _NodeJS_. Con él podemos instalar dependencias a nuestro proyecto o instalar programas globalmente en nuestro sistema. A lo largo de este curso y de toda la Escuela de JavaScript npm será quien nos permita correr los proyectos e instalar nuestras dependencias.

---
---

## Instalación y configuración de Visual Studio Code

### La instalación

Hay varios editores de código estupendos, pero la escuela de javascript _Platzi_ a decidido que VSCode sería el editor de todos los cursos de ésta. Para instalar el editor vamos a [Download VSCode](https://code.visualstudio.com/#alt-downloads)

### La configuración base

Se agregan algunas extensiones que le darán mayor capacidad al editor. Estos son los primeros de varios que se irán agregando en el transcurso de la escuela de javascript o de los intereses personales:

- __Git Blame__: va a mostrar el autor de la línea de código en la que estemos trabajando.
- __ESLint__: es una herramienta de análisis de código estático para identificar patrones problemáticos encontrados en el código JavaScript. Se debe instalar y configurar _eslint_ para que siga el estilo de código que le indiquemos.
- __Color Highlight__: resalta el color que estemos escribiendo.
- __SASS__: es un pre-procesador de CSS.

Para la extensión ***ESLint***: se realiza una configuración extra para que trabaje con los requisitos de los cursos de React. Entonces:

1. En la terminal elegida bash, hyper, etc. (ya sea embebida en VSCode o externa):
2. Instalación de global de ESLint: `$ npm install -g eslint`
3. Inicializar la configuración de ESLint: `$ npx eslint --init`
   - Existen tres opciones, la que se recomienda es la que indica: verificación de sintaxis, encontrar problemas y forzar un estilo de código.
   - Luego se generan preguntas por cada modo de esta opción, donde para la escuela de JS:
     1. ¿Qué tipo de módulos a usar?: `JavaScript modules (import/export)`
     2. ¿Cuál marco de trabajo?: `React`
        - ¿Donde correrá el código?: `Browser`
     3. ¿Cuál será la guía de estilos?: `Airbnb`
        - ¿Qué tipo de archivo de configuración?: `JSON`

NOTA: el primer signo de precio en los comandos (`$`) es para denotar que se esta en una consola tipo UNIX. Y no debe ser copiado en los comandos. Si estás en Linux es muy probable que muchos comandos deban ser ejecutados como usuario administrador.

---
---

## Google Chrome para desarrollo web

Se usará el navegador Chrome. Ni idea que más decir, si llega a este punto y no sabes por qué Chrome y que es eso de Inspeccionar -> revisa el curso de Programación Básica o Fundamentos de JavaScript de PLatzi.

### Del lado _frontend_

Ahora si, lo más importante es instalar dos extensiones al navegador web desde [chrome web store](https://chrome.google.com/webstore/category/extensions?hl=es):

- React Developer Tools
- Redux DevTools

### Del lado _Backend_

- Igual desde la web store de chrome instalar: __JSON Viewer__
- Y para instalar en local en la computadora: [Postman](https://www.getpostman.com/downloads/)

---
---

## README .md y sintaxis de markdown

El README .md es el archivo en el cual hacemos la descripción del proyecto, ya sea open source o privados es importante tener un buen **README**. Este archivo se escribe con formato markdown.

### Cómo escribir un buen README

No hay un estándar sobre cómo escribir un buen *README*, cada proyecto es diferente y depende de cada uno. Pero hay ciertas partes que sí o sí debería contener un buen README.

1. **Nombre**: Especificamos cómo se llama nuestro proyecto.
2. **Descripción**: es donde diremos para qué exactamente es el proyecto, qué problemas resuelve y cualquier información relevante.
3. **Instalación**: muestra los pasos específicos para instalar el proyecto. Por lo general se muestra un pedazo del código necesario para la instalación.
4. **Cómo usar**: describe rápidamente casos de uso en los cuales se puede usar el proyecto, además de mostrar funcionalidades.
5. **Cómo contribuir**: si es un proyecto open source se describe acá la forma en la que deberían crearse las contribuciones.
6. **Licencia**: muestra la licencia que tiene el proyecto.

Y el ejemplo . . . pues este mismo archivo :joy: Sí, que esperas mira el código de etiquetado de este documento y veras el uso básico de MarkDown.

### **Markdown**

**Es un formato de escritura que permite la generación de contenido fácil y rápido, permite generar una salida (por lo general) en formato HTML sin necesidad de aprender a profundidad HTML. Es ampliamente utilizado por su facilidad de generar texto enriquecido.**

#### Encabezados

Lo utilizamos para resaltar una parte importante, títulos, subtítulos, etc. Se utiliza el símbolo `#` para demarcar el inicio de un encabezado. No olvides dejar cambios de líneas libres antes y después.

```markdown
# Encabezado nivel 1
## Encabezado nivel 2
### Encabezado nivel 3
#### Encabezado nivel 4
##### Encabezado nivel 5
###### Encabezado nivel 6
```

#### Párrafos

En formato Markdown escribirlos no es tan distinto a escribir en un texto plano, automáticamente se reconoce que es un párrafo. Eso si deja espacios entre párrafos y títulos, y para generar un párrafo nuevo simplemente deja un cambio de línea vacío. En markdown mil cambios de línea vacíos es igual a uno.

#### Itálicas y negritas

Hay partes en las que necesitaremos hacer énfasis en ciertas palabras, lo común es que utilicemos _itálicas_ y __negritas__ para resaltarlas, en Markdown debemos hacer lo siguiente:

```markdown
**Esto es una negrita**
_Esto es una itálica_
**_Esto es una negrita con itálica_**
```

Así se ve:
**Esto es una negrita**
_Esto es una itálica_
**_Esto es una negrita con itálica_**

Puede llegar a existir variaciones según cada editor / presentación de markdown. Pero la idea básica es usar un solo asterisco `*` o línea baja `_` antes y después para las itálicas. Las negritas con `**` o `__`, y para la combinación puede ser desde `***`, `___`, `_**`, `**_`, `*__` o `__*`.

#### Citas

Se utilizan para mostrar referencias a otros autores y se puede hasta citas anidadas, sería:

```markdown
> Esto es una cita normal, por Yo su merced

Esto párrafo normal

> Segunda cita
> > Cita anidada
```

Y así se ve:
> Esto es una cita normal por Yo su merced

Esto párrafo normal

> Segunda cita
> > Cita anidada

#### Listas

Podemos utilizar listas ordenadas (númeradas) y listas sin orden:

##### Listas ordenadas

Los números seguidos de punto los coloca uno mismo:

```markdown
1. Primer item
2. Segundo item
3. Tercer item
```

En markdown se ve así:

1. Primer item
2. Segundo item
3. Tercer item

##### Listas sin orden

Se puede usar signos como `+` `-` `*`:

```markdown
- Primer item
- Segundo item
- Tercer item
```

En markdown se ve así:

- Primer item
- Segundo item
- Tercer item

##### Listas anidadas

Solo hace falta dar sangría izquierda (_espacio con la tecla `tab`_) y markdown hace el resto:

```markdown
- Primer item
- Segundo item
    1. El primer anidado y númerado (lista ordenada)
    2. Pos el segundo y síguela
        - O mejor anidamos más verdad
        - Bueno ya entendí la idea
    3. Entendido, Gracias.
- Tercer item
```

Entonces se ve así:

- Primer item
- Segundo item
    1. El primer anidado y númerado (lista ordenada)
    2. Pos el segundo y síguela
        - O mejor anidamos más verdad
        - Bueno ya entendí la idea
    3. Entendido, Gracias.
- Tercer item

#### Código

Es esencial que en los README podamos escribir código, esto para especificar la instalación o partes que debemos resaltar de nuestro proyecto. Hay dos formas en las que podemos resaltar código, dentro de un párrafo o en una sección completa.

Este es un pedazo de código dentro de un párrafo `console.log('Hola Mundo')`, y se escribe el texto dentro de las tildes invertidas ` `` `.

Para insertar código en bloque lo que hacemos es dejar cambios de líneas vacías antes y después, para luego dar una tabulación y automáticamente lo reconocerá como código:

    const miName = 'Simon Bolívar'
    console.log(`Hola Mundo soy ${yo}`)

Y la última y más profesional en bloque, según yo claro, es etiquetar así:

1. Dejar espaciado vertical _(cambio de línea)_
2. Triple tilde invertida seguidas (```)
3. De nuevo cambio de línea
4. Escribir el código como si se estuviera en un archivo con la extensión de ese lenguaje
5. Luego de todo el código otro cambio de línea
6. Y se finaliza la etiqueta con una Triple tilde invertida (```)

```
let name = "Escuela de Javascript"
console.log(name)
```

Ahora, con este etiquetado _cool_ se puede escribir varias líneas sin tener que estar dando una tabulación para cada línea de código.

> Además, se puede mejorar un poco más si el código no es genérico, como el caso anterior que todos reconocen como lenguaje ***javascript***.
> > Para hacer esto es tan simple como: en el paso 2, luego de las tildes invertidas escribir el nombre del lenguaje en cuestión: javascript, python, ruby, etc. Así o mas padre, si con colores de sintaxis.

**Código javascript**:

```javascript
let name = "Escuela de Javascript"

console.log(name)
```

**Código python**:

```python
arreglo = [10, 40, 'Hola', -100.67]

for valor in arreglo:
    print(valor)

""" Este es un comentario de varias líneas en Python, los resultados sería
10
40
Hola
-100.67
"""
```

---
---

## Crea llaves SSH

Las llaves SSH van a ayudar para la autentificar los mensajes con servidores. SSH utiliza criptografía asimétrica, o sea, tenemos dos llaves:

- __Pública__: la llave pública la podemos compartir por internet.
- __Privada__: debes tenerla en un sitio seguro y no debe ser compartida.

Tener una llave SSH permite una conexión fácil y segura con servidores. Para crear una llave SSH utilizamos el siguiente comando:

```sh
ssh-keygen -t rsa -b 4096 -C "comentario para recordar el pasado"
```

- _`ssh-keygen`_: comando para crear llaves ssh
- _`-t rsa`_: donde `-t` es el parámetro para usar un tipo de algoritmo especifico. En este caso es el algoritmo `rsa`, en nombre de sus creadores Rivest, Shamir y Adelman.
- _`-b 4096`_: y `-b` que indica la cantidad de bits de la llave. Con 2048 podría ser suficiente pero con el doble es mejor y tampoco es excesivo.
- _`-C "comentario ..."`_: finalmente `-C` para darle un comentario a la llave.

En este momento sólo se ha pedido la creación de las llaves correspondientes, y lo más probable es que el comando nos pregunte si deseamos usar la ruta por defecto para guardar los archivos. Se generan dos archivos, la llave privada y la pública que es el archivo con extensión `.pub`

Es probable que haga falta:

- Iniciar el agente generador de llaves con: `eval $(ssh-agent -s)`
- Agregar la llave generada al servidor ssh iniciado con: `ssh-add /YourDirLocalPrivateKey`
- Ver el contenido de la llave pública para copiar y pegar en el servidor: `cat id_rsa.pub`

---
---

## Git y GitHub

-> Si se quiere un resumen introductorio rápido _ver la sección de Git y GitHub en el_ _**curso de Prework: Buenas Prácticas y Entorno de Desarrollo**_ de Platzi.

-> Para una introducción al mundo de Git y GitHub ir al  _**Curso profesional de Git y GitHub**_ de Platzi.

-> Y para tener acceso a las notas de la clase: busca en [mi repositorio de GitHub](https://github.com/Nemo1Co/notasCursos-Platzi)

---
---

## Conclusiones

Seguir con la ruta de la escuela de JavaScript:

1. FrontEnd developer.
2. Fundamentos de JavaScript.
3. JavaScript profesional.
4. ReactJS
   - ... continua pero por ahora eso.
