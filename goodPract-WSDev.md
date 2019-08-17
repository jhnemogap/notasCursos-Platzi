# Buenas Prácticas y Entorno de Desarrollo
---

## Manejo archivos y directorios
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

#### Visualizar en terminal y abrir archivos
- __cat__: permite visualizar un archivo completo en la terminal.
- __more__ (en M.W. puede ser __less__): muestra por partes un archivo dentro de la terminal.
- __tail__: muestra las últimas 10 líneas de cada archivo, se puede modificar pasándo el parámetro con el número de líneas _-15_.
- __open__ (en M.W. puede ser __explorer__): abre un archivo con el programa que tengamos por defecto.