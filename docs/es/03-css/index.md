# CSS

CSS permite dar estilo a las páginas web mediante hojas de estilo externas,
lo que hace posible modificar muchos ficheros HTML actualizando un único
documento CSS. Escribir el estilo directamente en cada etiqueta es **muy
poco práctico**; lo recomendable es usar hojas de estilo externas.

## Sintaxis básica

```css
selector {
    propiedad: valor;
}
```

Una regla CSS tiene tres partes: el **selector** (qué elementos se ven
afectados), la **propiedad** (qué se va a cambiar) y el **valor** (cuánto o
cómo se cambia).

## Formas de incluir CSS

1. En línea: `<p style="color:red;">`
2. Interna: `<style>` dentro del `<head>`
3. Externa: `<link rel="stylesheet" href="estilos.css">`

## Selectores

| Selector | Ejemplo | Descripción |
|---|---|---|
| Elemento | `h1` | Todos los `<h1>` |
| Varios elementos | `h1, h2` | Todos los `<h1>` y `<h2>` |
| Clase | `.destacado` | Elementos con `class="destacado"` |
| ID | `#menu` | Elemento con `id="menu"` |
| Elemento + clase | `h1.titular` | `<h1>` con `class="titular"` |
| Elemento + id | `h1#titulonoticia` | `<h1>` con `id="titulonoticia"` |
| Descendiente | `ul li` | `<li>` en cualquier nivel dentro de `<ul>` |
| Hijo directo | `ul>li` | `<li>` hijo directo de `<ul>` |
| Hermano adyacente | `div + p` | `<p>` inmediatamente después de un `<div>` |

**Clases vs. IDs:** un **id** identifica de forma única a un único
elemento (solo debería usarse una vez por página); una **clase** puede
aplicarse a varios elementos que comparten el mismo estilo. En el
selector, el id se referencia con `#` y la clase con `.`.

## Pseudo-clases

Aplican estilo según el estado del elemento:

- `a:link` — enlace no visitado.
- `a:visited` — enlace ya visitado.
- `a:active` — enlace mientras se hace clic sobre él.
- `p:hover` — mientras el cursor está encima del elemento.
- `input:checked` — casillas o radios seleccionados.
- `p:first-of-type` — primer elemento de su tipo.
- `p:first-child` / `p:last-child` — primer/último hijo de su padre.
- `p:nth-child(4)` — el cuarto hijo.
- `p:nth-child(even)` / `p:nth-child(odd)` — hijos pares/impares.

## Fondos e imágenes

- `background-image: url("ruta")` — imagen de fondo.
- `background-repeat: no-repeat | repeat-x | repeat-y` — control del
  mosaico de la imagen.
- `background-position: top | bottom | left | right | center` — posición
  de la imagen.
- `background-size` — controla las dimensiones de la imagen.
- `background-attachment: fixed` — crea efectos de fondo fijo al hacer
  scroll.

## Bordes

- `border-style: solid | double | dashed | dotted | inset | outset`
- `border-color` — admite cualquier notación de color de CSS.
- `border-width` — grosor del borde.
- Variantes por posición: `border-bottom-style`, `border-top-color`, etc.
- `border-radius: 2px` — redondea las esquinas.

## Propiedades de texto

- `text-align: left | right | center | justify`
- `font-family` — indica la tipografía (Google Fonts permite usar fuentes
  incrustadas sin depender de las instaladas en el sistema).
- `text-decoration: underline | line-through | none`
- `letter-spacing: 2px` — espacio entre caracteres.
- `word-spacing` — espacio entre palabras.
- `line-height` — separación entre líneas.
- `text-shadow: 2px 3px blue` — sombra de texto (desplazamiento
  horizontal, desplazamiento vertical, color).
- `text-transform: uppercase | lowercase | capitalize`

## Outlines (bordes externos)

A diferencia del `border`, el `outline` no afecta a las dimensiones del
elemento, pero puede solaparse fácilmente con otros elementos:

- `outline-style: solid | dotted`
- `outline-width: thin | medium | thick`
- `outline-color`
- `outline-offset` — separación entre el outline y el borde.

## Tablas

- `border: solid 1px black` — añade bordes a los elementos de la tabla.
- `border-collapse: collapse` — fusiona los bordes adyacentes.
- `tr:nth-child(even)` — filas alternas.
- `tr:hover { background-color: red; }` — resalta la fila al pasar el
  ratón.

## Modelo de caja (Box Model)

En CSS **todo es una caja**, formada por cuatro capas:

`content` → `padding` → `border` → `margin`

- **Elementos en línea** (`<b>`, `<span>`, `<img>`): no rompen el flujo de
  línea e ignoran los cambios de `width`/`height`.
- **Elementos de bloque** (`<div>`, `<p>`, `<ul>`): generan una nueva línea
  y sí aceptan modificaciones de tamaño.

La propiedad `display` controla este comportamiento:

- `display: block` — se comporta como un bloque.
- `display: inline` — fluye en línea.
- `display: inline-block` — fluye en línea pero admite `width`/`height`.

### `box-sizing`

- `box-sizing: content-box` (por defecto) — el `width` se refiere solo al
  contenido; los bordes se suman aumentando el tamaño total.
- `box-sizing: border-box` — el `width` incluye los bordes; el contenido
  se reduce al añadir bordes.

## Posicionamiento

- `position: static` — colocación por defecto controlada por el
  navegador.
- `position: relative` — se desplaza respecto a su posición natural.
- `position: absolute` — se posiciona respecto a un antecesor
  posicionado, pudiendo "desaparecer" del flujo al hacer scroll.
- `position: fixed` — permanece fijo en pantalla al margen del scroll.
- `position: sticky` — semi-fijo: se desplaza con la página hasta alcanzar
  una posición mínima (definida con `top`, `left`...) y a partir de ahí se
  queda fijo.

### Centrado de elementos

**Horizontal:**

- Elementos en línea: al contenedor padre se le aplica
  `text-align: center`.
- Elementos de bloque: se les da un `width` y `margin: auto` (o
  `margin: 40px auto`).
- Elementos `inline-block`: el propio elemento necesita `width`, y al
  padre se le aplica `text-align: center`.

**Vertical:**

- Padre con `display: table` e hijos con `display: table-cell` más
  `vertical-align: middle`.
- Alternativa sencilla: mismo `padding` arriba y abajo.

## Float

`float` permite que el contenido de alrededor ocupe el espacio restante
junto al elemento flotante. Cuando hay varios elementos flotantes puede
ser necesario `clear: both` para evitar solapamientos no deseados; en
diseños complejos suele hacer falta un contenedor extra para "limpiar" los
flotantes.

## Márgenes y padding

Las propiedades `padding-` y `margin-` (con las variantes `-top`,
`-bottom`, `-left`, `-right`) controlan el espaciado interno y externo,
respectivamente.

## Colores

- Nombres de color: `red`, `yellow`, `green`...
- RGB: `rgb(255, 0, 0)` (valores de 0 a 255).
- Hexadecimal: `#ffffff` (componentes rojo, verde y azul).
- HSL: `hsl(num, num, num)`.

## Unidades de medida

- `1cm`, `1in` — útiles para hojas de estilo de impresión.
- `1px` — depende de la resolución de pantalla.
- `1%` — adecuado para maquetación en pantalla.
- `1em` — aproximadamente el ancho de la letra "m" en la fuente actual.

## Flexbox

`display: flex` crea contenedores flexibles que distribuyen a sus hijos de
forma eficiente.

**Dirección:**

- `flex-direction: row` — horizontal, izquierda a derecha (por defecto).
- `flex-direction: row-reverse` — horizontal, derecha a izquierda.
- `flex-direction: column` — vertical, arriba a abajo.
- `flex-direction: column-reverse` — vertical, abajo a arriba.

**Ajuste de línea:**

- `flex-wrap: nowrap` — los elementos se aprietan en una sola fila (por
  defecto).
- `flex-wrap: wrap` — los elementos que sobran pasan a la siguiente fila.
- `flex-wrap: wrap-reverse` — los elementos que sobran pasan a la fila
  anterior.

Se puede usar la forma abreviada `flex-flow: column wrap`.

**Distribución horizontal (`justify-content`):**

- `flex-start` — alineados a la izquierda, espacio a la derecha.
- `flex-end` — alineados a la derecha, espacio a la izquierda.
- `space-between` — los elementos de los extremos tocan los bordes; el
  espacio se reparte entre el resto.
- `space-around` — el espacio se reparte de forma no uniforme, con
  márgenes más pequeños en los extremos.
- `space-evenly` — el espacio se reparte de forma completamente uniforme.

## Grid Layout

`display: grid` crea estructuras tipo tabla con colocación flexible de
celdas.

```css
.contenedor {
    display: grid;
    grid-template-rows: 20% 20% 20% 20% 20%;
    grid-template-columns: 20% 20% 20% 20% 20%;
}
.elemento {
    grid-row: 1/3;
    grid-column: 4/6;
}
```

- `grid-template-rows` / `grid-template-columns` definen las proporciones
  de filas y columnas.
- `grid-row: 1/3` — ocupa desde la fila 1 hasta la 3 (filas 1 y 2).
- `grid-column: 4/6` — ocupa desde la columna 4 hasta la 6 (columnas 4 y
  5).

## Media Queries

Permiten aplicar CSS condicional según el medio de salida:

```css
@media screen {
    div { font-size: xx-large; }
}
@media print {
    div { margin: 15px; }
}
```

**Puntos de ruptura responsive:**

- `@media screen and (min-width: 800px)` — pantallas de 800px o más.
- `@media screen and (max-width: 799px)` — pantallas más estrechas de
  800px.
- `@media (orientation: portrait)` — orientación vertical.
- `@media (orientation: landscape)` — orientación horizontal.

## Tipografía

`font-family: "Arial"` permite indicar varias preferencias separadas por
comas, como alternativa por si la primera no está disponible. Existen
varias familias de fuentes: **serif** (con remates decorativos),
**sans-serif** (líneas limpias, sin remates) y **monoespaciadas** (todos
los caracteres ocupan el mismo ancho).

## Estilando formularios

Enfoques habituales:

- `display: block` en labels/inputs para apilar los controles
  verticalmente.
- `margin-bottom: 50px` para separar elementos.
- `width: 80%` para dar una anchura uniforme a los campos.
- `padding: 10px` para el espaciado interno.
- `input:focus` para aplicar estilo cuando el campo está activo.
- `padding` en el `fieldset` para crear un margen interno.

## Bootstrap

Framework CSS que requiere una estructura HTML mínima con un
`<div class="container">` envolvente. Usa un sistema de rejilla
(*grid*) responsive de 12 columnas.

**Clases de columna según el ancho del dispositivo:**

- `col-xs-3` — extra pequeño (< 768px).
- `col-sm-3` — pequeño (768–992px).
- `col-md-6` — mediano (~992px).
- `col-lg-9` — grande (> 992px).

**Otras utilidades:**

- `class="lead"` — resalta un párrafo.
- `<mark>` — resalta texto en amarillo.

## LESS (preprocesador)

Extiende CSS con características de programación y genera CSS estándar
como salida.

**Variables** (prefijo `@`, admiten operaciones matemáticas):

```less
@grosorborde: 3px;
@grosorcabecera: @grosorborde + 2px;
border: solid @grosorborde black;
```

**Mixins** (definiciones reutilizables que se invocan como funciones,
evitando repetir código):

```less
.margenesnoticias {
    padding-top: 10px;
    margin: 20px 10px 20px 10px;
}
#caja1 { .margenesnoticias(); }
```
