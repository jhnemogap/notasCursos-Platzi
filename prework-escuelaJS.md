# Prework: Buenas Prácticas y Entorno de Desarrollo

## ___Escuela de JavaScript 2019 - Platzi___


---


## Configurando la terminal o consola de comandos

En este apartado he decidido según el sistema operativo en el que este trabajando:
- ***Microsoft Windows***: he instalado git y su terminal git bash. Que para efectos prácticos hace lo que se necesita e incluso puede ser un reemplazo a Hyper o la terminal de Ubuntu para M. Windows. Si se va a trabar es este S.O. igualmente se deberá instalar [Git para M. Windows](https://gitforwindows.org), por lo que no instalaré adornos o duplicados hasta que no vea la real necesidad. Para este momento a mi gusto sería mejor una maquina virtual con GNU/Linux que instalar el ubuntu terminal.
- ***GNU/Linux***: Ya tenemos terminal por defecto un aliado que saludamos con gusto. Y debería estar instalado git pero en caso de que no pues a instalarlo. Cualquier adorno extra cada quien verá si en el transcurso lo pone o no.
- ***MacOS***: también se tiene terminal adecuada por defecto. Para más detalles mirar los videos del curso de Platzi . . . no conozco MacOS.

[Lleva tu terminal al siguiente nivel - Platzi](https://platzi.com/blog/lleva-tu-terminal-al-siguiente-nivel/) by demian


---


## Manejo archivos y directorios desde la terminal

__Comandos básico en la terminal - _tipo Unix___
- __clear__: limpia la pantalla de la terminal.
- __history__: Muestra el histórico de todos los comandos que hemos ejecutado. Para ejecutar un comando previo del historial existen dos formas básicas:
  1. Usar las fechas de navegación del teclado _arriba_ y _abajo_ para buscar comandos previos.
  2. Conociendo el número de ejecución en el archivo __history__, se ejecuta con un signo de admiración y el numero: __`!134`__


### Listar archivos

- __ls__: permite listar los archivos y directorios que se encuentren dentro de la carpeta en la que estamos ubicados, podemos pasar distintos parámetros a este comando, ej `ls -la`:
  - __a__: ver los archivos ocultos.
  - __l__: lista los contenidos mostrando sus permisos y propiedades. Algunos comandos solo operan acompañados, ej:
  - __lt__: lista los contenidos según su fecha de modificación.
  - __lh__: indica el tamaño del elemento en una presentación más "humana" - fácil. 


### Navegar entre carpetas

- __pwd__: retorna la ruta absoluta en la cual nos encontramos.
- __cd__: mueve a alguna carpeta que le indiquemos, dentro de los archivos ocultos vimos que existe:
  - __.__: refiere a la carpeta en la cual se está ubicados.
  - __..__: se refiere a la carpeta padre de la actual ubicación.
  - __~__: se ubica en la carpeta home de la computadora


### Creación, modificación y eliminación de archivos / carpetas

- __mkdir__: crea una carpeta con el nombre indicado, ej: `mkdir docsPlatzi`
- __touch__: crea un archivo vacío con el nombre que le indiquemos. Ej: `touch file.txt`
- __mv__: permite mover archivos entre distintas carpetas, se debe indicar el nombre del archivo y la ruta de destino.
- __rm__: elimina únicamente un archivo, añadiendo el parámetro `-rf` puede eliminar directorios también.
- __rmdir__: elimina directorios pero sólo si está vacío.
- __nano__: es un editor dentro de la consola, permite abrir cualquier archivo y modificarlo.


### Visualizar y abrir archivos en terminal

- __cat__: permite visualizar un archivo completo en la terminal.
  - para copiar: `cat file.txt > file-copy.txt`
- __more__ (en M.W. puede ser __less__): muestra por partes un archivo dentro de la terminal.
- __tail__: muestra las últimas 10 líneas de cada archivo, se puede modificar pasándo el parámetro con el número de líneas _-15_ y luego el archivo.
- __open__ (en M.W. puede ser __explorer__): abre un archivo con el programa que tengamos por defecto, puede o no ser de texto plano (fotos, videos, texto, etc.).


---
---


## Instalación y configuración de Visual Studio Code


### La instalación

Hay varios editores de código estupendos, pero la escuela de javascript _Platzi_ a decidido que VSCode sería el editor de todos los cursos de ésta. Para instalar el editor vamos a https://code.visualstudio.com/#alt-downloads


### La configuración base

Se agregan algunos plugins que le darán mayor capacidad al editor. Estos son los primeros de varios que se irán agregando en el transcurso de la escuela de javascript o de tus intereses:

+ __Git Blame__: va a mostrar el autor de la línea de código en la que estemos trabajando.
+ __ESLint__: es una herramienta de análisis de código estático para identificar patrones problemáticos encontrados en el código JavaScript, o sea, nuestro linter. Debemos instalar y configurar eslint para que siga el estilo de código que le indiquemos.
+ __Color Highlight__: resalta el color que estemos escribiendo.
+ __SASS__: es un pre-procesador de CSS.


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

En este momento sólo se ha pedido la creación de las llaves correspondientes, y lo más probable es que el comando nos pregunte si deseamos usar la ruta por defecto para guardar los archivos. Se generan dos archivos, la llave privada y la pública, el archivo con extensión `.pub`

Es probable que haga falta:
- Iniciar el agente generador de llaves con: `eval $(ssh-agent -s)`
- Agregar la llave generada al servidor ssh iniciado con: `ssh-add /YourDirLocalPrivateKey`
- Ver el contenido de la llave pública para copiar y pegar en el servidor: `cat id_rsa.pub` 

