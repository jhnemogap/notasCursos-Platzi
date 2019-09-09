# Curso profesional de Git y GitHub

## _**Notas conjuntas curso versión 2017 y 2019 - Platzi**_

---

## Sistemas de Control de Versiones

Un control de versiones es un sistema que registra los cambios realizados en un archivo o conjunto de archivos a lo largo del tiempo, de modo que puedas recuperar versiones específicas más adelante.

Dicho sistema permite regresar a versiones anteriores de tus archivos, regresar a una versión anterior del proyecto completo, comparar cambios a lo largo del tiempo, ver quién modificó por última vez algo que pueda estar causando problemas, ver quién introdujo un problema y cuándo, y mucho más. Usar un VCS también significa generalmente que si arruinas o pierdes archivos, será posible recuperarlos fácilmente. Adicionalmente, obtendrás todos estos beneficios a un costo muy bajo.

Existen tres modos de mantener los repositorios:

1. Solo en Local
2. Centralizado
3. Distribuido

[Extraído de Git Book](https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Acerca-del-Control-de-Versiones)

## Una breve historia de Git

Como muchas de las grandes cosas en esta vida, Git comenzó con un poco de destrucción creativa y una gran polémica.

El kernel de Linux es un proyecto de software de código abierto con un alcance bastante amplio. Durante la mayor parte del mantenimiento del kernel de Linux (1991-2002), los cambios en el software se realizaban a través de parches y archivos. En el 2002, el proyecto del kernel de Linux empezó a usar un DVCS propietario llamado BitKeeper.

En el 2005, la relación entre la comunidad que desarrollaba el kernel de Linux y la compañía que desarrollaba BitKeeper se vino abajo y la herramienta dejó de ser ofrecida de manera gratuita. Esto impulsó a la comunidad de desarrollo de Linux (y en particular a Linus Torvalds, el creador de Linux) a desarrollar su propia herramienta basada en algunas de las lecciones que aprendieron mientras usaban BitKeeper. Algunos de los objetivos del nuevo sistema fueron los siguientes:

- Velocidad
- Diseño sencillo
- Gran soporte para desarrollo no lineal (miles de ramas paralelas)
- Completamente distribuido
- Capaz de manejar grandes proyectos (como el kernel de Linux) eficientemente (velocidad y tamaño de los datos)

Desde su nacimiento en el 2005, Git ha evolucionado y madurado para ser fácil de usar y conservar sus características iniciales. Es tremendamente rápido, muy eficiente con grandes proyectos y tiene un increíble sistema de ramificación (_branching_) para desarrollo no lineal.

---

---

## Introducción a la terminal y línea de comandos REVISAR

Diferencias entre la estructura de archivos de Windows, Mac o Linux.

La ruta principal en Windows es `C:\`, en UNIX es solo `/`. Windows no hace diferencia entre mayúsculas y minúsculas pero UNIX sí. Recuerda que GitBash usa la ruta `/c` para dirigirse a `C:\` (o `/d` para dirigirse a `D:\`) en Windows. Por lo tanto, la ruta del usuario con el que estás trabajando es `/c/Users/Nombre-del-Usuario`

Todos estos comandos tiene una función de autocompletado, o sea, puedes escribir la primera parte y presionar la tecla `Tab` para que la terminal nos muestre todas las posibles carpetas o comandos que podemos ejecutar. Si presionas la tecla Arriba puedes ver el último comando que ejecutamos.

Recuerda que podemos descubrir todos los argumentos de un comando con el argumento `--help` (por ejemplo, `cat --help`).

__Comandos básico en la terminal - _tipo Unix___

- __clear__: limpia la pantalla de la terminal. También se puede usar los atajos de teclado `Ctrl + l` o `Command + L`.
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
- __cd__: nos permite navegar entre carpetas:
  - __cd .__: refiere a la carpeta en la cual se está ubicados.
  - __cd ..__: se refiere a la carpeta padre de la actual ubicación. Regresar una carpeta hacia atrás.
  - __cd__ o __cd ~__: se ubica en la carpeta home de la computadora
  - __cd sub-carpeta__: Navegar a una ruta dentro de la carpeta donde estamos ahora mismo.

### Creación, modificación y eliminación de archivos o carpetas

- __mkdir__: crea una carpeta con el nombre indicado, ej: `mkdir docsPlatzi`
- __touch__: crea un archivo vacío con el nombre que le indiquemos. Ej: `touch file.txt`
- __mv__: permite mover archivos entre distintas carpetas, se debe indicar el nombre del archivo y la ruta de destino.
- __rm__: elimina únicamente un archivo, añadiendo el parámetro `-rf` puede eliminar directorios también. Mucho cuidado con este comando, puedes borrar todo tu disco duro.
- __rmdir__: elimina directorios pero sólo si está vacío.
- __nano__ o __vim__: es un editor dentro de la consola, permite abrir cualquier archivo y modificarlo.

### Visualizar y abrir archivos en terminal

- __cat__: permite visualizar un archivo completo en la terminal (por ejemplo, `cat nombre-archivo.txt`).
  - para copiar: `cat file.txt > file-copy.txt`
- __more__ (en M.W. puede ser __less__): muestra por partes un archivo dentro de la terminal.
- __tail__: muestra las últimas 10 líneas de cada archivo, se puede modificar pasándo el parámetro con el número de líneas _-15_ y luego el archivo.
- __open__ (en M.W. puede ser __explorer__): abre un archivo con el programa que tengamos por defecto, puede o no ser de texto plano (fotos, videos, texto, etc.).

---

---

---

## [Instalación de Git](https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Instalaci%C3%B3n-de-Git)

Desde la propia página de GIT o revisando los videos del curso. Mas desde la página oficial de Git en español es rápido revisar.

```bash
$ git --version
git version 2.22.0.windows.1
```

## Configurando Git por primera vez

Git trae una herramienta llamada git config que te permite obtener y establecer variables de configuración, que controlan el aspecto y funcionamiento de Git. Se puede listar todas las variables de configuración con `git config --list` y con otro parámetro extra ej. `git config --list --show-origin` indicará la ruta local donde se almacena cada archivo de configuración por variable.

### Tu identidad

Lo primero que deberías hacer cuando instalas Git es establecer tu nombre de usuario y dirección de correo electrónico. Esto es importante porque las confirmaciones de cambios (_commits_) en Git usan esta información, y es introducida de manera inmutable en los _commits_ que envías:

```bash
git config --global user.name "John Doe"
git config --global user.email "johndoe@example.com"
```

De nuevo, sólo necesitas hacer esto una vez si especificas la opción `--global`, ya que Git siempre usará esta información para todo lo que hagas en ese sistema. Si quieres sobrescribir esta información con otro nombre o dirección de correo para proyectos específicos, puedes ejecutar el comando sin la opción `--global` cuando estés en ese proyecto.

### Tu editor

Ahora que tu identidad está configurada, puedes elegir el editor de texto por defecto que se utilizará cuando Git necesite que introduzcas un mensaje. Si no indicas nada, Git usa el editor por defecto de tu sistema, que generalmente es Vi o Vim. Si quieres usar otro editor de texto, como _Emacs_ o _VScode_, puedes hacer lo siguiente:

```bash
git config --global core.editor code
```

### Colores en Git

Git puede marcar con colores los resultados que muestra en tu terminal, ayudando así a leer más fácilmente. Hay unos cuantos parámetros que te pueden ayudar a configurar tus colores favoritos.

Si se lo pides, Git coloreará automáticamente la mayor parte de los resultados que muestre. Puedes ajustar con precisión cada una de las partes a colorear; pero si deseas activar de un golpe todos los colores por defecto, no tienes más que poner a "true" el parámetro 'color.ui'.

```bash
git config --global color.ui true
```

Ajustando así este parámetro, Git colorea sus resultados cuando estos se muestran en un terminal. Otros ajustes posibles son `false`, para indicar a Git no colorear nunca ninguno de sus resultados; y `always`, para indicar colorear siempre, incluso cuando se redirija la salida a un archivo o a otro comando.

Será muy raro ajustar `color.ui = always`. En la mayor parte de las ocasiones, cuando necesites códigos de color en los resultados, es mejor indicar puntualmente la opción `--color` en el comando concreto, para obligar a utilizar códigos de color. Habitualmente, se trabajará con el ajuste `color.ui = true`.

## [Fundamentos de Git](https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Fundamentos-de-Git)

Para iniciar un repositorio, o sea, activar el sistema de control de versiones de Git en tu proyecto, sólo debes ejecutar el comando `git init`.

Este comando se encargará de dos cosas: _**primero**_, crear una carpeta `.git` donde se guardará toda la base de datos con cambios atómicos de nuestro proyecto; y _**segundo**_, crear un área en la memoria RAM, que conocemos como _Staging_, que guardará temporalmente nuestros archivos (cuando ejecutemos un comando especial para eso) y nos permitirá, más adelante, guardar estos cambios en el repositorio (también con un comando especial).

**_Ciclo de vida o estados de los archivos en Git:_**

Cuando trabajamos con Git, nuestros archivos pueden vivir y moverse entre 4 diferentes estados (cuando trabajamos con repositorios remotos pueden ser más estados pero lo estudiaremos más adelante):

- __Archivos Untracked__: Son archivos que NO viven dentro de Git, sólo en el disco duro. Nunca han sido afectados por `git add`, así que Git no tiene registros de su existencia.
- __Archivos Tracked__: Son los archivos que viven dentro de Git, no tienen cambios pendientes y sus últimas actualizaciones han sido guardadas en el repositorio gracias a los comandos `git add` y `git commit`.
- __Archivos Unstaged__: Se entiende como archivos “_Tracked_ pero _Unstaged_”. Son archivos que viven dentro de Git pero no han sido afectados por el comando `git add` y mucho menos por `git commit`. Git tiene un registro de estos archivos pero está desactualizado, sus últimas versiones sólo están guardadas en el disco duro.
- __Archivos Staged__: Son archivos en _Staging_. Viven dentro de Git y hay registro de ellos porque han sido afectados por el comando `git add`, aunque no sus últimos cambios. Git ya sabe de la existencia de estos últimos cambios pero todavía no han sido guardados definitivamente en el repositorio porque falta ejecutar el comando `git commit`.

**NOTA**: Recuerda que hay un caso muy raro donde los archivos tienen dos estados al mismo tiempo: _Staged_ y _Untracked_. Esto pasa guardas los cambios de un archivo en el área de _Staging_ (con el comando `git add`) pero, antes de hacer _commit_ para guardar los cambios en el repositorio, haces nuevos cambios que todavía no han sido guardados en el área de _Staging_ (en realidad, todo sigue funcionando igual pero es un poco divertido).

---

---

---

## Git - Comandos iniciales

Cuando se ingresa desde git a una carpeta ya iniciada como repositorio, la terminal mostrará una marca ej: `(master)`, indicando la rama actual.

### Iniciar un repositorio

- En la carpeta actual se usa: **`git init`**
- En otra carpeta se agrega el directorio: **`git init Nuevo-Directorio`**

### Borrar repositorio manualmente

Para borrar un repositorio de forma manual sólo hace falta borrar la carpeta oculta _`.git`_ dentro la carpeta anfitrión del proyecto. O se puede visualmente con el navegador de archivos del sistema operativo.

```bash
rm -rf .git
```

### Cambiando archivos de estado en el repositorio

Estando dentro de un repositorio se puede usar el siguiente comando para conocer el estado de cada archivo:

```bash
git status
```

#### Archivos hacia el _Staging area_ y _Repository_

Con `add` se puede pasar archivos del _working directory_ al _staging area_.

```bash
git add file1.txt file.html file2.txt file1.css file2.css
```

Agrega todos los archivos del estado _working_ al _staging_

```bash
git add -A
```

Confirma si un archivo existe en el directorio

```bash
git add -n file.js
```

También es posible sacar un archivo del _staging_ y devolverlo al _working directory_

```bash
git rm --cached file.js
```

Aun, si lo que se quiere es eliminar en un solo paso un elemento por completo y ya fue agregado al _staging_, se puede aplicar el siguiente comando. Mucho cuidado con esto pues también elimina los elementos del directorio de trabajo.

```bash
git rm -f index.css
```

Para comprometer los archivos del _staging_ hacia el repositorio (_git directory_):

```bash
git commit -m "comentario sobre el commit realizado"
```

Si por alguna razón en el último _commit_ se olvido agregar un elemento o edición a un archivo, es posible agregar lo que falte al _staging_ para luego pedirle a git que realize una concatenación de lo nuevo con el _commit_ previo usando `--amend`

```bash
git commit --amend -m "comentario opcional que reemplaza el último realizado"
```

---

---

## Historial de _commits_

Este comando sin más banderas por defecto presenta toda la historia de cada _commit_, donde cada uno muestra los siguientes detalles:

```git
commit: 124325455365745...2342342
Author: Felipe Manter <felipe.manter@email.com>
Date: Jueves agosto 29 22:43:30 2019
    Mensaje del commit, si es que tiene. Es el comentario.
```

Dado que con el tiempo se agregan más y más _commits_, la gran cantidad de datos hará difícil leer el log. Existen opciones o configuraciones para mejorar la visualización según la necesidad. _**Es uno de los comandos más personalizables**_

### Ver solamente los 'n' últimos _commits_

```bash
# Muestra los tres más recientes
git log -3
```

### git reflog

Muestra todo el historial de los _sha1_ y _HEAD_ con el comando ejecutado.

```bash
git reflog
```

### Opciones mejoradas de una sola línea

#### Versión acortada

```bash
git log --oneline
```

#### Versión acortada más gráfica de ramificación

```bash
git log --oneline --graph
```

#### Resumen de cada _commit_ decorado y gráfica del paso por rama

```bash
git log --all --oneline --graph --decorate
```

---

## git blame

Es un comando muy útil que permite ver quién modificó específicamente una o varias líneas.

```bash
git blame archivo_34.txt
```

Permite escoger un intervalo de líneas a revisar:

```bash
git blame -L35,53 style.scss
```

Similar al anterior pero agrega un poco más de formato

```bash
git blame -L12,20 -c index.html
```

---

---

## Las ramas (_branch_) en Git

---

## git stash

---

---

## git diff

Sirve para revisar los cambios / diferencias entre dos _commits_, se le debe pasar el _sha1_ del _commit_ requerido.

Cuando solo se coloca un _sha1_ la comparación se realiza contra el _commit_ más reciente de la rama en la que se está.

```bash
git diff 45376ac765d45e58fa65ab95698bdc56
```

Ahora, si se comparan dos _commits_ distintos es importante el orden de cada uno de los _sha1_ correspondiente. Donde el primer argumento debería ser el del _commit_ más antiguo y el segundo el _sha1_ del _commit_ más reciente.

```bash
# git diff _sha1-antiguo_ _sha1-reciente_
git diff def34b14 aab345f1
```

---

---

## git reset

Existen tres tipos de _reset_ básicos que realizan tareas similares pero con diferencias importantes.

Para evitar grandes perdidas por un reset mal aplicado, se recomienda tener un _backup_ del `git log` o `git log --oneline`.

### reset --soft

El HEAD de la rama apuntará al _sha1_ indicado, en consecuencia cualquier _commit_ más reciente / nuevo a ese se "pierde".

```bash
git reset --soft _sha1_
```

### reset --mixed

Inicialmente realiza la misma operación del caso `--soft`. Seguidamente actualiza el área _index/staging_ con la instancia a la que apunta ahora el HEAD en el repositorio / _commit_.

```bash
git reset --mixed _sha1_
```

### reset --hard

De manera idéntica opera al `--mixed` para luego generar una la misma instancia del repositorio en el directorio de trabajo (_working directory_).

```bash
git reset --hard _sha1_
```

---

---

## git tags (etiquetas de hitos en un proyecto)

---

---

## git clean

Borra archivos del directorio de trabajo que no estén en seguimiento (_tracked_)

```bash
git clean
```

Con `--dry-run` git simula que archivos serán borrados y con `-f` fuerza el borrado dicho (tampoco borra archivos ignorados y ya _tracked_).

```bash
git clean --dry-run
> file20 file13 ...

git clean -f
# borra -> file20 file13 ...
```

Agregando `d` al parámetro de borrado forzado, se le permite borrar directorios.

```bash
git clean -df
```

---

## Buscar palabras

### En los archivos del proyecto

`git grep _word_`: donde _word_ es la palabra a buscar, si es una etiqueta ejemplo de html se debe colocar entre comillas "\<p>"

```bash
git grep "<p>"
git grep red
```

Muestra el número de línea donde está

```bash
git grep -n red
```

Entrega el conteo de esa palabra en los archivos

```bash
git grep -c "<p>"
```

### En el historial de _commits_

En mayúsculas la "S" y la palabra entre comillas:

```bash
git log -S "sass"
```

---

---

## Alias para comandos de Git

### Del mundo GNU/Linux

```bash
alias miComandoLog = "git log --all --graph --decorate --oneline"
```

### Directamente con Git

El parámetro global se puede retirar, así solamente sería un alias para el repositorio actual.

```bash
git config --global alias.miComandoLog "git log --all --graph --decorate --oneline"
```

---

---

---

## GitHub
