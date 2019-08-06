
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
- multiplicación
- división /

Operaciones con decimales debemos realizar operaciones adicionales para conseguir un resultado preciso, ej:
```JavaScript
var total = ( precioDeVino * 100 * 3) / 100
```

Para redondear una operación se utiliza la función: Math.round
