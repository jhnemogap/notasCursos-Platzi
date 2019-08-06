
# <span style="font-size: 1.2em">Fundamentos de JavaScript</span>
---

# Variables
Las variables son contenedores en los que puedes almacenar valores. Primero debes declarar la variable con la palabra clave `var`, seguida del nombre que le quieras dar:
```JavaScript
var nombreDeLaVariable;
```
Todas las líneas en JS deben acabar en punto y coma para indicar que es ahí donde termina la línea. Si no los incluyes puedes obtener resultados inesperados.

Puedes llamar a una variable con casi cualquier nombre, pero hay algunas restricciones.

JavaScript distingue entre mayúsculas y minúsculas — `miVariable` es una variable distinta a `mivariable`. Si estás teniendo problemas en tu código, revisa las mayúsculas y minúsculas.

[Fundamentos de JavaScript (MDN web docs) - Variables](https://developer.mozilla.org/es/docs/Learn/Getting_started_with_the_web/JavaScript_basics#Variables)

## Strings

Los _strings_ son cadenas de texto. Para indicar que estamos usando una cadena de texto debemos de colocar las comillas simples.

En este curso utilizamos los métodos:
- __toUpperCase__, que sirve para transformar un _string_ a mayúsculas.
- __toLowerCase__, transforma el _string_ a minúsculas.
- __charAt_, sirve par obtener un carácter especifico según su posición en la cadena de texto.
- __substr__, obtiene una subcadena de la cadena principal de acuerdo a los dos parámetros que indican:
  1. Posición de carácter de inicio sobre la cadena principal.
  2. Cantidad de caracteres a tomar.

También usamos el atributo:
- __length__, que nos indica la cantidad de caracteres que tiene un _string_.
Para concatenar dos _strings_ se utiliza el símbolo (+)
```JavaScript
var nombreCompleto = nombre + ’ ’ + apellido
```

Existe una forma más adecuada de concatenar texto y es por medio de la _interpolación de texto_: [Plantillas de cadena de texto - MDN web docs](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/template_strings#Summary)

## Números
Los operadores matemáticos más comunes son:
- suma ( + )
- resta ( - )
- multiplicación ( * )
- división ( / )

Operaciones con decimales debemos realizar operaciones adicionales para conseguir un resultado preciso, dado que JS no es tan preciso al guardar decimales. Ej:
```JavaScript
var total = ( precioDeVino * 100 * 3) / 100
```
* Para redondear una operación se utiliza la función: `Math.round(x)`
* Para pasar de decimal a cadena de caracteres, donde el parámetro es la cantidad de decimales a tener en cuenta: `.toFixed(#)`
* Y para convertir de string a decimal: `parseFloat("200.09")`

[JavaScript Arithmetic - w3schools.com](https://www.w3schools.com/js/js_arithmetic.asp)

---

# Funciones
Las funciones son fracciones de código reutilizable. Para definir una función se utiliza la palabra reservada `function`. [Definición de funciones - MDN web docs](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Funciones#Definici%C3%B3n_de_funciones)

En términos generales, una función es un "subprograma" que puede ser llamado por código externo (o interno en caso de recursión) a la función. Al igual que el programa en sí mismo, una función se compone de una secuencia de declaraciones, que conforman el llamado cuerpo de la función. Se pueden pasar valores a una función, y la función puede devolver un valor.

Delimitamos el cuerpo de la función usando llaves `{ }`. Los parámetros de la función son variables que se pasan a la función escribiéndolos entre paréntesis `()`.
```JavaScript
function nombre([param [,param [, ...param]]]) {
   instrucciones
}
```
JavaScript es un lenguaje interpretado, esto quiere decir que intentará ejecutar el código sin importar si los argumentos que se le pasen a la función estén invertidos o incluso incompletos.


### Alcance de las funciones

[Ámbito de las variables](https://uniwebsidad.com/libros/javascript/capitulo-4/ambito-de-las-variables)

El ámbito de una variable (llamado "_scope_" en inglés) es la zona del programa en la que se define la variable. JavaScript define dos ámbitos para las variables: global y local.

Si una variable se declara fuera de cualquier función, automáticamente se transforma en variable global independientemente de si se define utilizando la palabra reservada var o no. Sin embargo, las variables definidas dentro de una función pueden ser globales o locales.

Si en el interior de una función, las variables se declaran mediante var se consideran locales y las variables que no se han declarado mediante var, se transforman automáticamente en variables globales.
