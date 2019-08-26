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

## [Instalación de Git](https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Instalaci%C3%B3n-de-Git)

Desde la propia página de GIT o revisando los videos del curso. Mas desde la página oficial de Git en español es rápido revisar.

```bash
$ git --version
git version 2.22.0.windows.1
```

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

## Configurando Git por primera vez

Git trae una herramienta llamada git config que te permite obtener y establecer variables de configuración, que controlan el aspecto y funcionamiento de Git. Se puede listar todas las variables de configuración con `git config --list` y con otro parámetro extra ej. `git config --list --show-origin` indicará la ruta local donde se almacena cada archivo de configuración por variable.

### Tu identidad

Lo primero que deberías hacer cuando instalas Git es establecer tu nombre de usuario y dirección de correo electrónico. Esto es importante porque las confirmaciones de cambios (_commits_) en Git usan esta información, y es introducida de manera inmutable en los _commits_ que envías:

```sv
git config --global user.name "John Doe"
git config --global user.email "johndoe@example.com"
```

De nuevo, sólo necesitas hacer esto una vez si especificas la opción `--global`, ya que Git siempre usará esta información para todo lo que hagas en ese sistema. Si quieres sobrescribir esta información con otro nombre o dirección de correo para proyectos específicos, puedes ejecutar el comando sin la opción `--global` cuando estés en ese proyecto.

### Tu editor

Ahora que tu identidad está configurada, puedes elegir el editor de texto por defecto que se utilizará cuando Git necesite que introduzcas un mensaje. Si no indicas nada, Git usa el editor por defecto de tu sistema, que generalmente es Vi o Vim. Si quieres usar otro editor de texto, como _Emacs_ o _VScode_, puedes hacer lo siguiente:

```sv
git config --global core.editor code
```

### Colores en Git

Git puede marcar con colores los resultados que muestra en tu terminal, ayudando así a leer más fácilmente. Hay unos cuantos parámetros que te pueden ayudar a configurar tus colores favoritos.

Si se lo pides, Git coloreará automáticamente la mayor parte de los resultados que muestre. Puedes ajustar con precisión cada una de las partes a colorear; pero si deseas activar de un golpe todos los colores por defecto, no tienes más que poner a "true" el parámetro 'color.ui'.

```sv
git config --global color.ui true
```

Ajustando así este parámetro, Git colorea sus resultados cuando estos se muestran en un terminal. Otros ajustes posibles son `false`, para indicar a Git no colorear nunca ninguno de sus resultados; y `always`, para indicar colorear siempre, incluso cuando se redirija la salida a un archivo o a otro comando.

Será muy raro ajustar `color.ui = always`. En la mayor parte de las ocasiones, cuando necesites códigos de color en los resultados, es mejor indicar puntualmente la opción `--color` en el comando concreto, para obligar a utilizar códigos de color. Habitualmente, se trabajará con el ajuste `color.ui = true`.
