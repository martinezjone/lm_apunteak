# JavaScript

## Introducción

JavaScript surgió en Netscape y **no tiene nada que ver con Java**, más
allá del nombre. Características clave:

- Es **interpretado** por el navegador, no se compila a bytecode.
- Está estandarizado como **ECMAScript**, aunque el grado de cumplimiento
  varía entre navegadores.
- Está basado en **prototipos**, no en clases (aunque ES6 añade una
  sintaxis de clases sobre ese mismo modelo).
- Tiene **tipado débil**: permite conversiones de tipo automáticas.

## Tipos de datos

JavaScript admite: números, cadenas de texto, booleanos (valores lógicos),
`undefined` (al acceder a una variable no inicializada) y `null`
(representa la ausencia intencionada de valor).

La directiva `"use strict"` obliga a cumplir reglas más estrictas del
lenguaje, por ejemplo impidiendo el acceso a variables no declaradas.

## Constantes y variables

Las variables se declaran con `let` (el estándar actual) o con el
obsoleto `var`; los valores inmutables se declaran con `const`:

```javascript
"use strict"
const gravedad = 9.81;
let posicion = 42;
```

## Concatenación de cadenas

La concatenación tradicional usa el operador `+`:

```javascript
let nombreCompleto = nombre + " " + apellido1 + " " + apellido2;
```

Los *template literals* de ES6 (comillas invertidas) ofrecen una sintaxis
más limpia:

```javascript
let nombreCompleto = `${nombre} ${apellido1} ${apellido2}`;
```

## Inclusión en HTML

```html
<script src="script.js" defer></script>
```

El código también puede incluirse directamente entre `<script>` y
`</script>`, tanto en el `<head>` como en el `<body>`:

```javascript
"use strict"
let miVariable = 42;
document.write(miVariable);
```

## Estructuras de control

El `if-else` funciona igual que en Java, con los mismos operadores
lógicos (`&&`, `||`):

```javascript
if (varA > varB) {
    document.write("El primero es mayor");
} else {
    document.write("El segundo es mayor");
}
```

## Arrays

Los arrays admiten elementos de distintos tipos y se redimensionan
dinámicamente:

```javascript
let nombres = new Array();
nombres[0] = "Juan Perez";
nombres[1] = "Pedro Diaz";

let numeros = new Array(2);
numeros[0] = 23;
numeros[1] = -45.23;
```

## Bucle `for`

For clásico, accediendo a la longitud del array con `.length`:

```javascript
for (let i = 0; i < numeros.length; i++) {
    document.write("Posición " + i + ": " + numeros[i]);
}
```

Iteración estilo *foreach* con `for...in`:

```javascript
for (let posicion in numeros) {
    document.write("Posición " + posicion + ": " + numeros[posicion]);
}
```

## Bucle `while`

```javascript
let pos = 0;
while (pos < numeros.length) {
    document.write(numeros[pos]);
    pos++;
}
```

## Funciones

Las funciones aceptan parámetros y devuelven un valor con `return`:

```javascript
function calcularMedia(valores) {
    let suma = 0;
    for (let pos in valores) {
        suma = suma + valores[pos];
    }
    return suma / valores.length;
}
```

Las funciones son valores asignables: se omiten los paréntesis al
asignarlas y se incluyen al ejecutarlas:

```javascript
let despedida = decirAdios; // asignación
despedida("Tom");            // ejecución
```

ES6 permite parámetros con valor por defecto:

```javascript
function saludar(saludo = "Hola", persona = "Juan") {
    alert(`${saludo} ${persona}`);
}
```

## Programación orientada a objetos

JavaScript permite crear objetos sin necesidad de definir una clase:

```javascript
let empleado = {
    nombre: "Pepe Perez",
    edad: 27,
    estaJubilado: function() {
        return this.edad > 65;
    }
};
document.write(empleado.nombre);
document.write(empleado.estaJubilado());
```

## Manipulación del DOM

```js
const titulo = document.querySelector("h1");
titulo.textContent = "Nuevo título";
```

## Eventos

```js
document.querySelector("button").addEventListener("click", () => {
    alert("¡Hola!");
});
```

## jQuery

jQuery utiliza la función `$` para seleccionar elementos mediante
selectores CSS, devolviendo un objeto con métodos y propiedades propios.

### Gestión de eventos

El método `click` asocia una función al evento de pulsación:

```javascript
$(document).ready(inicio);

function inicio() {
    let boton = $("#id-boton");
    boton.click(gestionarClick);
}

function gestionarClick() {
    let div = $("#div-texto");
    div.fadeOut();
}
```

!!! warning "Importante"
    Las funciones se pasan por referencia (sin paréntesis) a `.ready()` y
    a `.click()`. Si se añaden paréntesis, la función se ejecuta
    inmediatamente en lugar de asociarse al evento.

Otros eventos habituales: `click`, `dblclick`, `mouseover`.

### Lectura y escritura de atributos

Para leer el valor de un campo se usa `.val()`, y para comprobar si un
checkbox o radio está marcado, `.prop("checked")`:

```javascript
function gestionarGenero() {
    let cuadroTexto = $("#informe");
    cuadroTexto.val("Bienvenido Sr.");
}

let checkbox = $("#bus");
checkbox.click(contarSeleccionados);

function contarSeleccionados() {
    let total = 0;
    let ids = ["#bus", "#coche", "#bici", "#tren"];
    for (let pos in ids) {
        if ($(ids[pos]).prop("checked")) {
            total++;
        }
    }
}
```

Los valores de listas desplegables se leen igualmente con `.val()`.

### Otros métodos útiles

- `.slideDown()` / `.slideUp()` — muestran/ocultan con animación de
  deslizamiento.
- `.fadeOut()` / `.fadeIn()` — efectos de desvanecido.
- `.addClass()` / `.removeClass()` — añaden/quitan clases CSS
  dinámicamente.
- `.html()` — modifica el contenido interno de un elemento.

### Validación de reglas de negocio

Un patrón habitual es validar combinaciones de opciones incompatibles,
por ejemplo "un motor diésel no puede superar los 2300cc":

```javascript
function esConfiguracionValida() {
    if ($("#diesel").prop("checked") && $("#2300cc").prop("checked")) {
        alert("Incompatible: diésel con 2300cc");
        return false;
    }
    return true;
}
```

Este tipo de comprobaciones permite construir aplicaciones interactivas:
formularios con validación, calculadoras de precios, configuradores de
productos, etc., actualizando la interfaz según las selecciones del
usuario.

## Fetch de datos

```js
fetch("datos.json")
    .then(response => response.json())
    .then(datos => console.log(datos));
```
