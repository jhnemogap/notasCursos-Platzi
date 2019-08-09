
# Fundamentos de JavaScript

## Variables
Las variables son contenedores en los que puedes almacenar valores. Primero debes declarar la variable con la palabra clave `var`, seguida del nombre que le quieras dar:
```JavaScript
var nombreDeLaVariable;
```
Todas las líneas en JS deben acabar en punto y coma para indicar que es ahí donde termina la línea. Si no los incluyes puedes obtener resultados inesperados.

Puedes llamar a una variable con casi cualquier nombre, pero hay algunas restricciones.

JavaScript distingue entre mayúsculas y minúsculas — `miVariable` es una variable distinta a `mivariable`. Si estás teniendo problemas en tu código, revisa las mayúsculas y minúsculas.

[Fundamentos de JavaScript (MDN web docs) - Variables](https://developer.mozilla.org/es/docs/Learn/Getting_started_with_the_web/JavaScript_basics#Variables)

### Strings

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

## Funciones
Las funciones son fracciones de código reutilizable. Para definir una función se utiliza la palabra reservada `function`. [Definición de funciones - MDN web docs](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Funciones#Definici%C3%B3n_de_funciones)

En términos generales, una función es un "subprograma" que puede ser llamado por código externo (o interno en caso de recursión) a la función. Al igual que el programa en sí mismo, una función se compone de una secuencia de declaraciones, que conforman el llamado cuerpo de la función. Se pueden pasar valores a una función, y la función puede devolver un valor.

Delimitamos el cuerpo de la función usando llaves `{ }`. Los parámetros de la función son variables que se pasan a la función escribiéndolos entre paréntesis `()`.

```JavaScript
function nombre([param [,param [, ...param]]]) {
   instrucciones
}
```

JavaScript es un lenguaje interpretado, esto quiere decir que intentará ejecutar el código sin importar si los argumentos que se le pasen a la función estén invertidos o incluso incompletos.

Un ejemplo de una función que devuelve un verdadero o falso:

```javascript
function aMayorb(a, b){
  return a > b
}

console.log( aMayorb(5, 2) ); // true
console.log( aMayorb(20, 37) ); // false
console.log( aMayorb(13, 13) ); // false
```


### Alcance de las funciones

[Ámbito de las variables](https://uniwebsidad.com/libros/javascript/capitulo-4/ambito-de-las-variables)

El ámbito de una variable (llamado "_scope_" en inglés) es la zona del programa en la que se define la variable. JavaScript define dos ámbitos para las variables: global y local.

Si una variable se declara fuera de cualquier función, automáticamente se transforma en variable global independientemente de si se define utilizando la palabra reservada `var` o no. Sin embargo, las variables definidas dentro de una función pueden ser globales o locales.

Si en el interior de una función, las variables se declaran mediante `var` se consideran locales y las variables que no se han declarado mediante `var`, se transforman automáticamente en variables globales.


### Arrow Functions
Las funciones de flecha, o _arrow functions_ son una nueva forma de definir funciones y hay distintas variantes en la sintaxis.

#### Un solo parámetro
Al crear una arrow function de un solo parámetro no es necesario escribír los paréntesis, tampoco es necesario escribír las llaves, esto se puede cuando la función es de una sola línea y devuelve un valor.
```javascript
// convencional
function saludo (nombre){
  return `Hola ${nombre}`
}
console.log( saludo('Carlos') )

// con arrow function
let saludo = nombre => `Hola ${nombre}`;
console.log( saludo('Carlos') ) //Imprime Hola Jonathan
```

#### Varios parámetros
Cuando la función tenga más de un parámetro es necesario envolver el nombre de estos entre paréntesis.
```javascript
// convencional
function sumar(a, b) {
  return a + b;
}
console.log( sumar(10, 9) ) //Imprime 19

// con arrow function
let sumar = (a, b) => a + b;
console.log( sumar(10, 9) ); //Imprime 19
```

#### Sin parámetros
Cuando la función no reciba parámetros también son necesarios los paréntesis.
```javascript
// convencional
function saludo() {
  return 'Hola a todos';
}
console.log( saludo() ); // Imprime Hola a todos

// con arrow function
let saludo = () => `Hola a todos`;
console.log( saludo() ); // Imprime Hola a todos
```

#### Con cuerpo
Cuando la función tiene más de una línea (o no devuelve ningún valor) es necesario utilizar las llaves.
```javascript
let fecha = new Date(),
hora = fecha.getHours()

// convencional
function saludarCompa(hr) {
  if (hr <= 5) {
    return 'No me jodas!!!'
  }
  else if (hr >= 6 && hr <= 11) {
    return 'Buenos días!!!'
  }
  else if (hr >= 12 && hr <= 18) {
    return 'Buenas tardes!!!'
  }
  else {
    return 'Buenas noches!!!'
  }
}
console.log( saludarCompa(hora) ) //Imprime el saludo dependiendo la hora del día

// con arrow function
let saludarCompa = hr => {
  if (hr <= 5) {
    return 'No me jodas!!!'
  } else if(hr >= 6 && hr <= 11) {
    return 'Buenos días!!!'
  } else if(hr >= 12 && hr <= 18) {
    return 'Buenas tardes!!!'
  } else {
    return 'Buenas noches!!!'
  }
}
console.log( saludarCompa(hora) ) //Imprime el saludo dependiendo la hora del día
```

#### Evitar generar un nuevo contexto en `this`
Tomado de [Arrow Functions en ES6](https://desarrolloweb.com/articulos/arrow-functions-es6.html)
Cuando se usa funciones callback éstas generan un nuevo contexto sobre la variable "_this_". Es un efecto que si se tiene experiencia con Javascript se conoce de sobra; pero si no solo tener la idea es bueno para más adelante . En estos casos, para poder acceder al `this` anterior se hacían cosas como "``var that = this``", o quizás hayas el "``.bind(this)``" para _bindear_ el contexto.

Por si no queda claro, miremos el siguiente código:
```javascript
var objTest = {
  retardo: function() {
    setTimeout(function() {
      this.hacerAlgo();
    }, 1000)
  },
  hacerAlgo: function() {
    alert('hice algo')
  }
}

objTest.retardo()
```

En la función ``setTimeout()`` se envia un _callback_ que genera un nuevo contexto, por tanto, no se puede acceder a ``this`` dentro de esa función. O mejor dicho, sí se puede acceder, pero no devolverá lo que quizás se espere, que sería el propio objeto ``objTest``. Es por eso que al ejecutar ese código saldría un error: `Uncaught TypeError: this.hacerAlgo is not a function`

Realmente no importa mucho ver el código para resolver esto en ES5, ya que en ES6 y con las funciones flecha se podría resolver de una manera mucho más elegante.
```javascript
var objTest = {
  retardo: function() {
    setTimeout( () => {
      this.hacerAlgo();
    }, 1000)
  },
  hacerAlgo: function() {
    alert('hice algo')
  }
}

objTest.retardo()
```

Ahora la función enviada como _callback_ a `setTimeout()` está definida con una _arrow function_ y por tanto no genera contexto nuevo en la variable `this`. Es por ello que al intentar invocar a ``this.hacerAlgo()`` no generará ningún error y se ejecutará perfectamente ese método ``hacerAlgo()``.

---


## Objetos
Es aquel material que ha sido creado y que tiene ciertos atributos o características que lo definen. Los atributos van entre llaves y separados por comas.

Un atributo se compone de una clave (_key_) y un valor (_value_), que se separan entre sí por dos puntos `:`. Los valores pueden ser de tipo _string_, número, booleano, etc. Cada atributo está separado del siguiente por una coma. Un objeto puede tener todos los atributos que sean necesarios.
```javascript
var viejoFer = {
  //Clave: valor,
  nombre:'Fernando', // -----> 'nombre' es un atributo de el objeto 'viejoFer'
  apellido:'Huaman', // -----> 'apellido' es un atributo de el objeto 'viejoFer'
  edad:18// -----> 'edad' es un atributo de el objeto 'viejoFer'
}
```

#### Desglosar un objeto
En las nuevas versiones de JS, se puede desglosar un objeto en uno de sus atributos, de esta forma solo se obtiene de manera simplificada lo que se requiere y no todo el objeto.
```javascript
function impNameObjeto(persona){
  return persona.name.toUpperCase()
}

// Dado que solo se requiere el nombre de persona, se podría desglosar así ->
function impNameObjeto( {name} ){
  return name.toUpperCase()
}
```

#### Asignación por _destructuring_ (_destructuring assignment_)
La sintaxis de _destructuring assignment_ es una expresión de JavaScript que hace posible la extracción de datos de arreglos u objetos usando una sintaxis que equivale a la construcción de arreglos y objetos literales.

**Object destructuring**
```javascript
// Convencional
var edad = persona.edad

// Destructuranto
var { edad } = persona
```

```JavaScript
var o = {p: 42, q: true};
var {p, q} = o;

console.log(p); // 42
console.log(q); // true

// Asigna nuevos nombres de variable
var {p: foo, q: bar} = o;

console.log(foo); // 42
console.log(bar); // true  
```

---

## Parámetros por valor o como referencia
Javascript se comporta de manera distinta cuando le pasamos un objeto como parámetro y cuando se pasa un dato primitivo.

>En JavaScript, cuando asignamos un valor a una variable, o pasamos un argumento a una función, este proceso siempre se hace “por valor” (_by value_ en inglés). Estrictamente hablando, JavaScript no nos ofrece la opción de pasar o asignar “por referencia” (_by reference_ en inglés), como en otros lenguajes. Lo interesante en nuestro caso, es que cuando una variable hace referencia a un objeto (``Object``, ``Array`` o ``Function``), el “valor” es la referencia en sí.

>#### Asignando valores primitivos
Cuando asignamos valores primitivos (Boolean, Null, Undefined, Number, String y Symbol), el valor asignado es una copia del valor que estamos asignando.
```javascript
let a = 'hola';
let b = a; // asignamos valor de 'a' a 'b'.
a += '!'; // cambiamos valor de 'a' añadiendo ! al final
console.log(a); // hola!
console.log(b); // hola
```

>#### Asignando valores complejos
Pero cuando asignamos valores __NO primitivos o complejos__ (`Object`, `Array` y `Function`), JavaScript copia “__la referencia__”, lo que implica que no se copia el valor en sí, si no una referencia a través de la cual accedemos al valor original.
```javascript
const a = [1, 2, 3];
const b = a;
a.push(4);
console.log(a); // [ 1, 2, 3, 4 ]
console.log(b); // [ 1, 2, 3, 4 ]
```
Tomado de [Por valor vs por referencia en JavaScript - medium.com](https://medium.com/laboratoria-developers/por-valor-vs-por-referencia-en-javascript-de3daf53a8b9)

Cuando los objetos se pasan como una referencia, estos se modifican fuera de la función. Para solucionar esto en caso de que no se quiera este cambio, entonces se puede crear un objeto diferente. Esto lo podemos hacer colocando tres puntos antes del nombre. Ej `...persona`:
```javascript
var persona {
  name: theName,
  age: 20
}

function orale(prsn){
  return {
    // Aquí se copia la estructura pero se hace una copia independiente
    ...prsn,
    // Se puede modificar la estructura inicial, agregar o eliminar.
    age: age + 1
  }
}
```

## Comparaciones en JavaScript
Existen cinco tipos de datos que son primitivos:
- Boolean
- Null
- Undefined
- Number
- String

JavaScript tiene comparaciones estrictas y de conversión de tipos. Una comparación estricta (por ejemplo, ``===``) solo es verdadera si los operandos son del mismo tipo y los contenidos coinciden. La comparación abstracta más comúnmente utilizada (por ejemplo, ``==``) convierte los operandos al mismo tipo antes de hacer la comparación. Para las comparaciones abstractas relacionales (p. Ej., ``<=``), Los operandos primero se convierten en primitivos, y luego en el mismo tipo, antes de la comparación.

#### Igualdad (``==``)
El operador de igualdad convierte los operandos __si no son del mismo tipo__, luego aplica una comparación estricta. __Si ambos operandos son objetos__, entonces JavaScript compara las referencias internas que son iguales cuando los operandos se refieren al mismo objeto en la memoria.
```javascript
1    ==  1         // true
'1'  ==  1         // true
1    == '1'        // true
0    == false      // true
0    == null       // false
var object1 = {'key': 'value'}, object2 = {'key': 'value'};
object1 == object2 // false
0    == undefined  // false
null == undefined  // true
```

#### Identidad / igualdad estricta (``===``)
El operador de identidad devuelve verdadero si los operandos son estrictamente iguales __sin conversión de tipo__.
```javascript
3 === 3   // true
3 === '3' // false
var object1 = {'key': 'value'}, object2 = {'key': 'value'};
object1 === object2 // false
```

> "__Se recomienda usar el triple igual siempre que se este comparando variables.__"
Sacha Lifszyc

---


## Estructuras de control de flujo
Tomado de [Estructuras de control de flujo](https://uniwebsidad.com/libros/javascript/capitulo-3/estructuras-de-control-de-flujo) y [Otras estructuras de control](https://uniwebsidad.com/libros/javascript/capitulo-4/otras-estructuras-de-control)

Si se utilizan estructuras de control de flujo, los programas dejan de ser una sucesión lineal de instrucciones para convertirse en programas inteligentes que pueden tomar decisiones en función del valor de las variables.

Para este caso es necesario un nuevo tipo de datos primitivos: el booleano, que determina si un valor es falso (`false`) o verdadero (`true`).


### Estructura ``if``
La estructura más utilizada en JavaScript y en la mayoría de lenguajes de programación es la estructura if. Se emplea para tomar decisiones en función de una condición. Su definición formal es:
```JavaScript
if ( condicion ) {
  ...
}
```
Si la condición se cumple (es decir, si su valor es ``true``) se ejecutan todas las instrucciones que se encuentran dentro de ``{...}``. Si la condición no se cumple (es decir, si su valor es ``false``) no se ejecuta ninguna instrucción contenida en ``{...}`` y el programa continúa ejecutando el resto de instrucciones del script.

Ejemplo:
```JavaScript
var mostrarMensaje = true;

if(mostrarMensaje) {
  alert("Hola Mundo"); // Muestra la alerta "Hola Mundo"
}

var number = 30
if(number < 20) {
  alert("Pos no va"); // No muestra la alerta, dado que la condición no se cumple
}
```


### Estructura `if ... else`
En ocasiones, las decisiones que se deben realizar no son del tipo _"si se cumple la condición, hazlo; si no se cumple, no hagas nada"_. Normalmente las condiciones suelen ser del tipo _"si se cumple esta condición, hazlo; si no se cumple, haz esto otro"_.

Para este segundo tipo de decisiones, existe una variante de la estructura `if` llamada `if...else`. Su definición formal es la siguiente:
```JavaScript
if ( condicion ) {
  ...
}
else {
  ...
}
```

Si la condición se cumple (es decir, si su valor es ``true``) se ejecutan todas las instrucciones que se encuentran dentro del ``if()``. Si la condición no se cumple (es decir, si su valor es ``false``) se ejecutan todas las instrucciones contenidas en ``else { }``. Ejemplo:
```JavaScript
var edad = 15;

if(edad >= 18) { // Este bloque no se ejecutará porque la condición es falsa
  alert("Eres mayor de edad");
}
else { // Ya que el if encadenado previo no se ejecuta este se ejecutará en reemplazo
  alert("Todavía eres menor de edad");
}
```


#### `if...else if...else`
Una extensión del `if...else` es agregar sentencias intermedias encadenadas de `else if`. De este modo abarcar opciones continuas si las previas no se cumplen.
```javascript
if(numero == 5) {
  ...
}
else if(numero == 8) {
  ...
}
else if(numero == 20) {
  ...
}
else {
  ...
}
```


### Estructura `switch`
La estructura ``if...else`` se puede utilizar para realizar comprobaciones múltiples y tomar decisiones complejas. Sin embargo, si todas las condiciones dependen siempre de la misma variable, el código JavaScript resultante es demasiado redundante:

En estos casos, la estructura ``switch`` es la más eficiente, ya que está especialmente diseñada para manejar de forma sencilla múltiples condiciones sobre la misma variable.
El anterior ejemplo realizado con ``if...else`` se puede rehacer mediante ``switch``:
```javascript
switch(numero) {
  case 5:
    ...
    break;
  case 8:
    ...
    break;
  case 20:
    ...
    break;
  default:
    ...
    break;
}
```


### Estructura ``while``
La estructura ``while`` permite crear bucles que se ejecutan ninguna o más veces, dependiendo de la condición indicada. El funcionamiento del bucle ``while`` se resume en: ___"mientras se cumpla la condición indicada, repite indefinidamente las instrucciones incluidas dentro del bucle"___.

Evidentemente, las variables que controlan la condición deben modificarse dentro del propio bucle, ya que de otra forma, la condición se cumpliría siempre y el bucle ``while`` se repetiría indefinidamente.

El siguiente ejemplo utiliza el bucle ``while`` para sumar todos los números menores o iguales que otro número. El programa debe sumar todos los números menores o igual que otro dado.
```javascript
var resultado = 0;
var numero = 100;
var i = 0;

while(i <= numero) {
  resultado += i;
  i++;
}
alert(resultado);
```


### Estructura ``do...while``
El bucle de tipo ``do...while`` es muy similar al bucle ``while``, salvo que en este caso __siempre__ se ejecutan las instrucciones del bucle al menos la primera vez. De esta forma, como la condición se comprueba después de cada repetición, la primera vez siempre se ejecutan las instrucciones del bucle. Es importante no olvidar que después del ``while()`` se debe añadir el carácter ``;`` (al contrario de lo que sucede con el bucle ``while`` simple).

Utilizando este bucle se puede calcular fácilmente el factorial de un número:
```javascript
var resultado = 1;
var numero = 5;

do {
  resultado *= numero;  // resultado = resultado * numero
  numero--;
} while(numero > 0);
alert(resultado);
```

En el código anterior, el _resultado_ se multiplica en cada repetición por el valor de la variable _numero_. Además, en cada repetición se decrementa el valor de esta variable numero. La condición del bucle ``do...while`` es que el valor de numero sea mayor que ``0``, ya que el factorial de un número multiplica todos los números menores o iguales que él mismo, pero hasta el número ``1`` (el factorial de 5 por ejemplo es ``5 x 4 x 3 x 2 x 1 = 120``).


### Estructura ``for``
La estructura ``for`` permite realizar repeticiones (también llamadas bucles) de una forma muy sencilla. No obstante, su definición formal no es tan sencilla como la de _if()_:
```javascript
for(inicializacion; condicion; actualizacion) {
  ...
}
```

La idea del funcionamiento de un bucle ``for`` es la siguiente: _"mientras la condición indicada se siga cumpliendo, repite la ejecución de las instrucciones definidas dentro del for. Además, después de cada repetición, actualiza el valor de las variables que se utilizan en la condición"_.

- La "_inicialización_" es la zona en la que se establece los valores iniciales de las variables que controlan la repetición.
- La "_condición_" es el único elemento que decide si continua o se detiene la repetición.
- La "_actualización_" es el nuevo valor que se asigna después de cada repetición a las variables que controlan la repetición.

```javascript
var mensaje = "Hola, estoy dentro de un bucle";

for(var i = 0; i < 5; i++) {
  alert(mensaje);
}
```


### Estructura ``for...in``
Una estructura de control derivada de ``for`` es la estructura ``for...in``. Su definición exacta implica el uso de objetos, por ahora, solamente se va a presentar la estructura ``for...in`` adaptada a su uso en _arrays_.

Si se quieren recorrer todos los elementos que forman un array, la estructura for...in es la forma más eficiente de hacerlo, como se muestra en el siguiente ejemplo:

```javascript
var dias = ["Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado", "Domingo"];

for(i in dias) {
  alert(dias[i]);
}
```

La variable que se indica como índice es la que se puede utilizar dentro del bucle ``for...in`` para acceder a los elementos del array. De esta forma, en la primera repetición del bucle la variable ``i`` vale ``0`` y en la última vale ``6``.

Esta estructura de control es la más adecuada para recorrer _arrays_ (y objetos), ya que evita tener que indicar la inicialización y las condiciones del bucle ``for`` simple y funciona correctamente cualquiera que sea la longitud del array. De hecho, sigue funcionando igual aunque varíe el número de elementos del array.

---

## Arreglos de datos _Array_
Los _arrays_ son estructuras que nos permiten organizar elementos dentro de una colección. Estos elementos pueden ser números, strings, booleanos, objetos, etc.

Los _arrays_ (arreglo o matrices) son objetos de tipo lista cuyo prototipo tiene métodos para realizar operaciones de recorrido y mutación. Ni la longitud o los tipos de los elementos del array son fijos. Dado que la longitud de un _array_ puede cambiar en cualquier momento, y los datos pueden almacenarse en ubicaciones no contiguas en él, no se garantiza que los _arrays_ JavaScript sean densos, esto depende de cómo el programador opte por usarlos. En general, estas son características convenientes, pero si estas características no son deseables para su uso en particular, se podría considerar usar _arrays_ tipados

#### Crear un Array
```javascript
var frutas = ['Manzana', 'Banana']
console.log(frutas.length) // se imprime un: 2
```

#### Acceder (por índice) a un elemento Array
```javascript
var primero = frutas[0] // Manzana
var ultimo = frutas[frutas.length - 1] // Banana
```

#### Bucle sobre un Array
Modo convencional
```javascript
for (var i = 0; i < frutas.length; i++) {
  console.log(frutas[i])
}
// Manzana 0
// Banana 1
```
Usando el método interno de los arreglos:
```javascript
frutas.forEach( function (elemento, indice, array) {
    console.log(elemento, indice)
})
// Manzana 0
// Banana 1
```

#### Añadir elemento al final de un Array
```javascript
var nuevaLongitud = frutas.push('Naranja')
// ["Manzana", "Banana", "Naranja"]
```

#### Eliminar elemento del final de un Array
```javascript
var ultimo = frutas.pop() // elimina Naranja del final
// ["Manzana", "Banana"]
```

#### Añadir elemento al inicio de un Array
```javascript
var nuevaLongitud = frutas.unshift('Fresa') // añade al inicio
// ["Fresa", "Banana"]
```

#### Eliminar elemento del inicio de un Array
```javascript
var primero = frutas.shift() // elimina Manzana del inicio
// ["Banana"]
```

#### Encontrar el índice de un elemento en el Array
```javascript
frutas.push('Mango')
// ["Fresa", "Banana", "Mango"]

var pos = frutas.indexOf('Banana')
// 1
```

#### Eliminar un elemento con el índice de posición
```javascript
var elementoEliminado = frutas.splice(pos, 1) // así es como se elimina un elemento
// ["Fresa", "Mango"]
```

#### Eliminar elementos con el índice de posición
```javascript
var vegetales = ['Repollo', 'Nabo', 'Rábano', 'Zanahoria']
console.log(vegetales)
// ["Repollo", "Nabo", "Rábano", "Zanahoria"]

var pos = 1, n = 2;
var elementosEliminados = vegetales.splice(pos, n)
// así es como se eliminan elementos, n define la cantidad de elementos a eliminar,
// de esa posicion(pos) en adelante hasta el final del array.

console.log(vegetales)
// ["Repollo", "Zanahoria"] (el array original ha cambiado)
console.log(elementosEliminados)
// ["Nabo", "Rábano"]
```

#### Copiar un Array
```javascript
var copiaSuperficial = frutas.slice() // esta es la forma de crear una copia
// ["Fresa", "Mango"]
```

### Filtrar un array
Para filtrar siempre se necesita establecer una condición. El método `.filter()` crea una nueva matriz con todos los elementos que pasan la prueba implementada por la función proporcionada.

Recuerda que si no hay elementos que pasen la prueba, filter devuelve un _array_ vacío.
```javascript
var words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present']

const result = words.filter(word => word.length > 6);
console.log(result);
// expected output: Array ["exuberant", "destruction", "present"]
```

### Transformar un array `.map()` ("mapeo")
El método `.map()` itera sobre los elementos de un array en el orden de inserción y devuelve array nuevo con los elementos modificados.
```javascript
var numbers = [1, 5, 10, 15];
let doubles = numbers.map(x => x * 2)
// numbers is still [1, 5, 10, 15]
// doubles is now [2, 10, 20, 30]

numbers = [1, 4, 9];
let roots = numbers.map( num => Math.sqrt(num) )
// numbers is still [1, 4, 9]
// roots is now [1, 2, 3]
```

### Reducir `.reduce()`
El método ``.reduce()`` aplica una función a un acumulador y a cada valor de un array (de izquierda a derecha) para reducirlo a un único valor.
Los invito a revisar un poco más de los parámetros de la función parámetro del método, en: [Array.prototype.reduce()](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/Array/reduce#Sintaxis)

```javascript
[1, 3, 5, 7, 11].reduce( (acumulador, nuevoValor) => acumulador + nuevoValor, 10 )

// Primera llamada
acumulador = 11, nuevoValor = 1

// Segunda llamada
acumulador = 14, nuevoValor = 3

// Tercera llamada
acumulador = 19, nuevoValor = 5

// Cuarta llamada
acumulador = 26, nuevoValor = 7

// Quinta llamada
acumulador = 37, nuevoValor = 11

// el array sobre el que se llama a reduce siempre es el objeto [1,3,5,7,11] 
// Valor Devuelto: 37
```