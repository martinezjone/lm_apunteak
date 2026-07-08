# HTML

HTML5 es la revisión más reciente del estándar HTML e introduce nuevas
etiquetas semánticas que dan estructura y significado al contenido de la
página.

## ¿Qué es HTML?

1. HTML significa **HyperText Markup Language** (lenguaje de marcado de
   hipertexto).
2. Es el **lenguaje estándar para crear páginas web**.
3. **Define la estructura** de una página web mediante "etiquetas".
4. Las **etiquetas HTML indican cómo deben mostrarse** los elementos
   (texto, imágenes, enlaces, etc.).
5. No es un lenguaje de programación, sino un lenguaje de marcado.
6. Funciona junto con **CSS** (para el diseño) y **JavaScript** (para la
   interacción).
7. Los archivos HTML tienen la extensión **.html o .htm**.

!!! tip "Editor"
    Para escribir código, se recomienda usar **[Visual Studio Code](https://code.visualstudio.com/){: target="_blank" rel="noopener" }**.



## Estructura básica de un documento

```html
<!DOCTYPE html>
<html lang="eu">
<head>
    <meta charset="UTF-8">
    <title>Nire orria</title>
</head>
<body>
    <h1>Kaixo mundua</h1>
</body>
</html>
```

- El `doctype` identifica el estándar HTML que se está utilizando.
- Las etiquetas `<html>`...`</html>` engloban el documento completo.
- `<head>` contiene los metadatos; `<body>` contiene el contenido visible.
- `<title>` establece el título de la página (el que aparece en la
  pestaña del navegador).

Todos los elementos dentro de `<head>` son opcionales excepto `<title>`:
ese es el único que debe estar presente obligatoriamente.

## Atributos

Modifican el comportamiento general de las etiquetas (color, alineación,
estilos...). El atributo se compone del nombre, el signo `=` y el valor
que toma, escrito entre comillas:

```html
<elementu_izena atributu1="balio1" atributu2="balio2">...</elementu_izena>
```



!!! example "Ariketa 1"
    Empezaremos a practicar, para ello haremos el primer ejercicio: [Ariketa 1](https://docs.google.com/document/d/1bX3VveTiWPALXlwyk2_bzWR_Lmldd4CsQWVppNYj1LA/edit?usp=sharing){: target="_blank" rel="noopener" }
    
## Metadatos (`<head>`)

- `<meta charset="UTF-8">`: garantiza que los símbolos y acentos se
  muestren correctamente.
- `<meta name="viewport" content="width=device-width, initial-scale=1">`:
  optimiza la vista en dispositivos móviles.
- `<meta name="description" content="...">`: descripción de la página
  (la que utilizan los buscadores).
- `<style>`: permite incrustar CSS directamente en el documento.
- `<link rel="icon" sizes="192x192" href="/bidea/ikonoa.png">`: añade un
  favicon.
- `<base>`: indica la **dirección raíz** del sitio web, lo que permite
  que todas las direcciones relativas de los enlaces de la página
  (`href`, `src`...) se resuelvan a partir de esa dirección raíz.

**Control de rastreo de buscadores (`robots`):**

```html
<meta name="robots" content="index, follow">
<meta name="robots" content="noindex, follow">
<meta name="robots" content="index, nofollow">
```

- `index, follow`: indexa la página y sigue sus enlaces.
- `noindex, follow`: no la indexa, pero sí sigue sus enlaces.
- `index, nofollow`: la indexa, pero deja de lado sus enlaces.

**Ejemplo de un `<head>` completo:**

```html
<head>
    <title>Nire web orria</title>
    <base href="https://www.URL.com/" target="_blank">
    <meta charset="UTF-8">
    <meta name="description" content="Nire web orriari buruz hitz egingo dugu">
    <meta name="keywords" content="HTML, CSS, JavaScript">
    <meta name="author" content="Jone">
    <link rel="stylesheet" type="text/css" href="URL">
</head>
```

## Títulos (`<h1>`-`<h6>`) y línea horizontal

Los encabezados de `<h1>` a `<h6>` ordenan los títulos estrictamente
según su tamaño, del más grande al más pequeño. Son elementos de bloque.

```html
<body>
    <h1>Goiburua H1</h1><h2>Goiburua H2</h2>
    <h3>Goiburua H3</h3><h4>Goiburua H4</h4>
    <h5>Goiburua H5</h5><h6>Goiburua H6</h6>
</body>
```

La etiqueta `<hr>` crea una línea horizontal para separar párrafos.
Puede usarse junto con `<hgroup>` para agrupar títulos relacionados
entre sí:

```html
<body>
    <hgroup>
        <h1>TITULU NAGUSIA</h1>
        <h2>Bigarren titulua</h2>
    </hgroup>
    <p>hau lehen paragrafoa da.</p>
    <hr/>
    <p>hau bigarren paragrafoa da.</p>
</body>
```

## Comentarios

Sirve para insertar comentarios, en una línea o en varias, que el
navegador no interpretará: se escriben como `<!-- contenido -->` y el
navegador no los muestra. Sin embargo, al ver el código fuente, esos
comentarios sí pueden verse.

```html
<!--nireorrialdea.html-->
<html>
<head> ... </head>
<!--Hemen hasten da dokumentuaren gorputza -->
<body> ... </body>
</html>
```

## Formato de texto

## Formato básico de texto

En HTML5 se recomienda definir **el aspecto mediante CSS**. Aun así,
existen algunas etiquetas que aportan un significado semántico:

| Etiqueta | Uso |
|---------|-----------|
| `<strong>` | Texto de gran importancia (normalmente se muestra en negrita). |
| `<em>` | Énfasis o subrayado semántico (normalmente en cursiva). |
| `<b>` | Texto al que se quiere llamar la atención, sin significado especial. |
| `<i>` | Palabras extranjeras, términos técnicos u otro tipo de texto especial. |
| `<u>` | Texto subrayado (uso muy limitado). |
| `<sup>` | Superíndice. |
| `<sub>` | Subíndice. |
| `<small>` | Comentarios aparte; reduce el tamaño del texto (se suele usar para mostrar derechos de autor). |

```html
-- Ambos se verán en negrita en el navegador, pero no significan lo mismo.
<b>Kaixo</b>

<strong>Kaixo</strong>
-- Ambos se escribirán en negrita, pero el navegador distinguirá el segundo como texto de gran importancia
```

!!! tip
    HTML debe expresar el **significado**; el **aspecto**, en cambio,
    debe definirlo CSS.

## Párrafos y saltos de línea

- `<p>`: define un párrafo.
- `<br>`: inserta un salto de línea dentro del párrafo.

Usar:

- `<p>` para separar ideas o temas distintos.
- `<br>` en casos en los que haya que separar direcciones, poemas,
  letras de canciones o líneas.

No se recomienda usar `<br>` para separar párrafos.

!!! example "Ariketa 2"
    Para practicar todo lo anterior, crearemos este segundo ejercicio: [Ariketa 2](https://docs.google.com/document/d/1uGno9mUAN5DKdeTdbDz3JHxJCzQ_hNfYbqgqv9hz5GA/edit?usp=sharing){: target="_blank" rel="noopener" }
    

**Abreviaturas, definiciones y citas:**

```html
<abbr title="World Wide Web Consortium">W3C</abbr>
```

- `<dfn>` indica una definición.
- `<blockquote>` marca una cita larga (como bloque).
- `<cite>` marca una cita breve.

**Cambios de texto:**

- `<del>` texto tachado (eliminado).
- `<ins>` texto insertado (normalmente en cursiva).
- `<mark>` resalta el texto.
- `<samp>` salida de ejemplo de un programa.
- `<tt>` estilo de máquina de escribir/monoespaciado.
- `<wbr>` sugiere un punto en el que el texto puede romperse al hacer
  *wrap*.
- `<output>` muestra el resultado de un cálculo.

## Estilo con el atributo `style`

El atributo `style` puede colocarse junto con cualquier etiqueta HTML
para cambiar el aspecto del texto que le sigue. Hoy en día, sin embargo,
se recomienda definir el estilo de una letra **mediante CSS**, no en la
propia etiqueta.

Propiedades más habituales utilizadas en el atributo de estilo:
`background-color`, `color`, `font-family`, `font-size`, `text-align`.

```html
<p style="text-align:center; color:red">kaixo</p>
```

!!! example "Ariketa 3"
    Tomaremos el ejercicio anterior y le daremos un poco de formato: [Ariketa 3](https://docs.google.com/document/d/1-elSPF7C4rMSja-fL5CdYVIvKhH__P7gnhU4qNS9XNc/edit?usp=sharing){: target="_blank" rel="noopener" }
    

## Espacios en blanco

Los navegadores pliegan en un único espacio en blanco los múltiples
espacios en blanco y saltos de línea del código original. Para
controlar el espacio:

- `&nbsp;` crea un espacio en blanco que no se puede romper (espacio
  duro).
- `<br/>` fuerza el salto de línea.
- `<p>` separa párrafos lógicos.

## Entidades HTML

| Entidad | Resultado | Significado |
|---|---|---|
| `&lt;` | < | menor que |
| `&gt;` | > | mayor que |
| `&amp;` | & | ampersand |
| `&copy;` | © | copyright |
| `&trade;` | ™ | marca comercial |
| `&reg;` | ® | marca registrada |
| `&euro;` | € | euro |
| `&yen;` | ¥ | yen |
| `&quot;` | " | comillas |
| `&aacute;` / `&Aacute;` | á / Á | a con acento |
| `&eacute;` / `&Eacute;` | é / É | e con acento |
| `&iacute;` / `&Iacute;` | í / Í | i con acento |
| `&oacute;` / `&Oacute;` | ó / Ó | o con acento |
| `&uacute;` / `&Uacute;` | ú / Ú | u con acento |

!!! note
    Dado que las etiquetas se definen con los símbolos `<` y `>`, puede
    generarse ambigüedad cuando esos símbolos deben escribirse en el
    propio texto; por eso hay que usar códigos como `&lt;` y `&gt;` en
    lugar de escribir directamente `<`/`>`.

## Texto preformateado

- `<pre>` obliga al navegador a respetar los espacios en blanco y los
  saltos de línea del código original.
- `<kbd>` indica el texto introducido por el usuario mediante el
  teclado.
- `<var>` indica una variable.
- `<code>` marca código de programación.

## Listas

**Listas ordenadas y desordenadas:**

```html
<ol>
    <li>Lehen elementua</li>
    <li>Bigarren elementua</li>
</ol>

<ul>
    <li>Ordenik gabeko elementua</li>
    <li>Beste elementu bat</li>
</ul>
```

Las listas pueden anidarse dentro de otras listas; se pueden combinar
todo tipo de listas (ordenadas, desordenadas y de definición).

**Aspecto de las listas desordenadas (`list-style-type`):**

La propiedad `list-style-type` de CSS cambia el aspecto de las viñetas
de las listas desordenadas:

- `disc`: por defecto, círculo negro relleno.
- `circle`: círculo (hueco).
- `square`: cuadrado.
- `none`: sin viñeta.

**Atributos de las listas ordenadas:**

| Atributo | Valor | Descripción |
|---|---|---|
| `reversed` | `reversed` | Ordena la lista en orden descendente (9, 8, 7...). |
| `start` | número | Indica en qué número empieza. |
| `type` | `1 \| A \| a \| I \| i` | Para poner el tipo de viñeta: `1` números normales, `A` letras mayúsculas, `a` letras minúsculas, `I` números romanos mayúsculos, `i` números romanos minúsculos. |

**Listas de definición:**

```html
<dl>
    <dt>Terminoa</dt>
    <dd>Terminoa deskribatzen duen definizioa</dd>
</dl>
```

!!! example "Ariketa 4"
    Practicaremos todas las listas vistas, para ello haremos el
    siguiente ejercicio: [Ariketa 4](https://docs.google.com/document/d/1pveaqygPBLPr78U9XzY_ine5uHqWn9uhMmzeColxKY8/edit?usp=sharing){: target="_blank" rel="noopener" }
    

!!! example "Ariketa 5 (Errepasoa)"
    Haremos este ejercicio de repaso antes de empezar con las tablas: [Ariketa 5](https://docs.google.com/document/d/1yNLnRmuh3gRfOAYjq5qQ2CAdDA78987bK7IwfbBcPkw/edit?usp=sharing){: target="_blank" rel="noopener" }

    Para hacer el ejercicio de repaso, necesitaremos este texto: [Ariketa5_Testua.txt](https://drive.google.com/file/d/1BURGxTBSFa6vFExP35HiloBQfq5gmY2Y/view?usp=sharing){: target="_blank" rel="noopener" }
    
## Enlaces (`<a>`)

La fuerza de la WWW reside en la capacidad de saltar de una página a
otra: se puede navegar fácilmente de una página a otra y acceder de
inmediato a la información, mediante enlaces. Los enlaces se hacen con
el elemento `<a>`:

```html
<a href="estekaren helbidea" target="_blank">Estekaren testua</a>
```

**Direcciones relativas:** supongamos que el proyecto está organizado
así:

```
01_PROIEKTUA/
├── hasiera.html
├── nire_orria1.html
├── nire_orria2.html
├── nire_orria3.html
└── 01_ARGAZKIAK/
    ├── argazkien_orria.html
    └── ikonoa
```

Para enlazar el resto de páginas desde `hasiera.html`:

```html
<a href="nire_orria1.html" target="_self">Lehenengo orria</a>
<br>
<a href="nire_orria2.html" target="_blank">Bigarren orria</a>
<br>
<a href="nire_orria3.html" target="_self">Hirugarren orria</a>
```

Como la página de fotos está en la subcarpeta `01_ARGAZKIAK`, para ir
hasta allí el enlace debe escribirse así:

```html
<a href="01_ARGAZKIAK/argazkien_orria.html" target="_blank">Argazkien orria</a>
```

El navegador siempre mantiene la dirección de la página en la que
estamos trabajando. Por tanto, para volver desde
`argazkien_orria.html` a `hasiera.html`, hay que subir una carpeta
usando `../`:

```html
<a href="../hasiera.html" target="_self">Hasiera orria</a>
```

**Atributo `target`:**

| Valor | Descripción |
|---|---|
| `_blank` | Lo abre en una ventana o pestaña nueva. |
| `_self` | Lo abre en la misma pestaña en la que se hizo clic (por defecto). |
| `_parent` | Lo abre en la pestaña de origen. |
| `_top` | Lo abre en todo el cuerpo de la página. |
| `frame-izena` | Lo abre en el *frame* especificado. |

**Atributo `rel`:** indica la relación entre el enlace y el documento.

| Valor | Significado |
|---|---|
| `alternate` | Versión que se encuentra en otro soporte (página para imprimir, traducida...). |
| `author` | Enlace al autor del documento. |
| `bookmark` | URL utilizada en el apartado de "Favoritos". |
| `external` | Enlace externo. |
| `help` | Enlace al documento de ayuda. |
| `license` | Enlace al documento de licencia. |
| `next` | Enlace para ir al siguiente documento. |
| `nofollow` | Enlace que no se seguirá. |
| `noreferrer` | Que el navegador envíe la cabecera sin referencia HTTP. |
| `prev` | Enlace para ir al documento anterior. |
| `search` | Enlace para presentar una herramienta de búsqueda. |
| `tag` | Enlace a una etiqueta del documento de trabajo. |

```html
<a rel="nofollow" href="http://www.funcexample.com/">Hegaldi merkeak</a>
```

!!! example "Ariketa 6"
    Haremos este ejercicio para trabajar los enlaces: [Ariketa 6](https://docs.google.com/document/d/1yNLnRmuh3gRfOAYjq5qQ2CAdDA78987bK7IwfbBcPkw/edit?usp=sharing){: target="_blank" rel="noopener" }

**Salto a un apartado dentro de la misma página:** primero hay que
nombrar el apartado al que vamos a saltar; después, crear el enlace que
nos lleve a ese apartado:

```html
<!-- Se marca el apartado del documento -->
<a name="aurkezpena">AURKEZPENA</a>

<!-- Llamada desde otro apartado al apartado de presentación -->
<a href="#aurkezpena">Joan AURKEZPEN atalera</a>
```

## Imágenes (`<img>`)

En un sitio web, las imágenes son elementos imprescindibles para captar
la atención del usuario y despertar las ganas de usarlo, pero no pueden
utilizarse sin permiso de licencia. Existen varios formatos de imagen:

- **GIF**: tiene una compresión sin calidad. Solo admite 256 colores. Es
  adecuado para gráficos, dibujos o iconos (`*.gif`).
- **JPG / JPEG**: con la compresión se pierde calidad. Admite 16,7
  millones de colores. Es adecuado para gestionar fotografías (`*.jpg` /
  `*.jpeg`).
- **PNG**: imagen sin compresión. Admite entre 16,7 millones de colores
  y transparencias (`*.png`).

Para insertar imágenes se usa la etiqueta `<img>`, y no tiene etiqueta de
cierre:

```html
<img src="images/pacman.jpg" alt="Pacman jokoa">
```

Es mejor meter todas las imágenes en una carpeta, para mantener el
proyecto ordenado; hay que tener cuidado con la ruta que se introduce en
el atributo `src`.

**Atributos de la etiqueta `<img>`:**

| Atributo | Valor | Descripción |
|---|---|---|
| `src` | URL | URL de la imagen. |
| `alt` | texto | Indica qué texto aparecerá si la imagen no aparece. |
| `width` | píxeles | Indica la anchura de la imagen. |
| `height` | píxeles | Indica la altura de la imagen. |
| `longdesc` | URL | Da a conocer la URL de la descripción detallada de la imagen. |
| `usemap` | `#mapa_izena` | Para especificar el mapa de la imagen. |

**Imágenes con enlaces:** en las páginas web se usa mucho combinar
imágenes con enlaces (por ejemplo, la imagen de un anuncio). Hay que
juntar las etiquetas de la imagen y del enlace:

```html
<a target="_blank" href="estekaren helbidea">
    <img src="irudiaren helbidea" alt="testu deskribatzailea">
</a>
```

**Imagen como "icono" (favicon):** una página web suele llevar un
pequeño icono. Debe insertarse en el apartado `<head>`:

```html
<link rel="icon" type="image/png" href="images/ikonoa.ico">
```

**Mapa de imagen (`usemap`):** se usa para vincular distintos enlaces a
distintas regiones sobre una misma imagen:

```html
<img src="planetak.gif" width="145" height="126" alt="Planetak" usemap="#planetamap">
<map name="planetamap">
    <area shape="rect" coords="0,0,82,126" alt="Eguzkia" href="eguzkia.htm">
    <area shape="circle" coords="90,58,3" alt="Merkurio" href="merkurio.htm">
    <area shape="circle" coords="124,58,8" alt="Artizarra" href="artizarra.htm">
</map>
```

!!! example "Ariketa 7"
    Tomando el ejercicio anterior, le añadiremos algunas imágenes: [Ariketa 7](https://docs.google.com/document/d/1_CJtRfB0itwi-28CKiPz1CjdhrMXO0GOdG8Josb7oWc/edit?usp=sharing){: target="_blank" rel="noopener" }

## Tablas

```html
<table>
    <caption>Taularen titulua</caption>
    <thead>
        <tr><th>Izena</th><th>Adina</th></tr>
    </thead>
    <tbody>
        <tr><td>Ana</td><td>25</td></tr>
    </tbody>
    <tfoot>
        <tr><td colspan="2">Guztira: 1 errenkada</td></tr>
    </tfoot>
</table>
```

- `<table>` engloba la tabla completa.
- `<thead>` contiene las filas de cabecera, con celdas `<th>`.
- `<tbody>` contiene las filas de datos, con celdas `<td>`.
- `<tfoot>` agrupa las filas de pie (totales, resúmenes...).
- `<caption>` da un título a la tabla.
- `<colgroup>` y `<col>` asocian información a columnas concretas.
- `<tr>` define una fila.

**Atributos para combinar celdas:**

| Atributo | Valor | Descripción |
|---|---|---|
| `colspan` | número | Para combinar columnas en una sola celda. |
| `rowspan` | número | Para combinar filas en una sola celda. |

Por ejemplo, si se pone `<td colspan="3">`, se combinarán tres columnas
en esa celda; si se pone `<td rowspan="2">`, en cambio, se combinarán
esa fila y la siguiente en una sola celda.

!!! example "Ariketa 8"
    En este ejercicio usaremos todos los elementos vistos hasta ahora: [Ariketa 8](https://docs.google.com/document/d/10OdWh8rRAqE4MvS2_rgTyeBhYnarij9VyPsRNPoP5fc/edit?usp=sharing){: target="_blank" rel="noopener" } 

!!! warning "Regla importante"
    Todo dato, o incluso una subtabla entera, siempre debe estar dentro
    de una celda `<td>`. Es obligatorio: las tablas pueden anidarse
    dentro de otras celdas para construir maquetaciones complejas.

## Etiquetas semánticas (HTML5)

HTML5 añadió **nuevas etiquetas semánticas** para organizar las páginas web de forma más clara y comprensible. Gracias a ello, tanto los navegadores como los buscadores, e incluso los propios desarrolladores, entienden mejor la estructura de la página.

> **Importante:** las etiquetas semánticas no cambian el aspecto por sí mismas; dan **significado** al contenido.

---

### Estructura de una página

- `<header>`: **cabecera** de una página o de una sección. En ella se suele colocar el logo, el nombre del sitio web o el título principal.
- `<nav>`: **menú de navegación**. Agrupa los enlaces que llevan a otras páginas o apartados.
- `<main>`: **contenido principal** de la página.
- `<section>`: agrupa contenido relacionado con un tema o apartado concreto.
- `<article>`: representa un **contenido independiente** (una entrada de blog, una noticia, la ficha de un producto...).
- `<aside>`: **contenido complementario** o barra lateral. Suelen colocarse enlaces de interés, anuncios o información adicional.
- `<footer>`: **pie** de una página o de una sección. Suele contener información del autor, el copyright o el contacto.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Nire webgunea</title>
</head>

<body>

    <header>
        <h1>Nire webgunea</h1>

        <nav>
            <ul>
                <li><a href="#">Hasiera</a></li>
                <li><a href="#">Produktuak</a></li>
                <li><a href="#">Kontaktua</a></li>
            </ul>
        </nav>
    </header>

    <main>

        <section>

            <article>
                <h2>Lehen artikulua</h2>
                <p>Artikuluaren edukia...</p>
            </article>

            <article>
                <h2>Bigarren artikulua</h2>
                <p>Artikuluaren edukia...</p>
            </article>

        </section>

        <aside>
            Informazio osagarria
        </aside>

    </main>

    <footer>
        &copy; 2026 - Nire webgunea
    </footer>

</body>
</html>
```

### Explicación de cada etiqueta

#### `<header>`

Indica la cabecera de una página o sección. Normalmente contiene:

- El nombre del sitio web
- El logo
- El título principal
- El menú de navegación (a menudo dentro de `<nav>`)

---

#### `<nav>`

Agrupa los elementos de navegación.

Normalmente contiene dentro una lista de enlaces (`<ul>` y `<li>`), pero también pueden usarse imágenes o botones.

Por ejemplo:

- Hasiera
- Guri buruz
- Produktuak
- Kontaktua

---

#### `<main>`

Agrupa el **contenido principal** de la página web.

En cada página debe haber **un único `<main>`**.

---

#### `<section>`

Agrupa contenido del mismo tema.

Por ejemplo:

- Albisteak
- Zerbitzuak
- Produktuak
- Harremanetarako atala

Normalmente contiene varios `<article>` dentro.

---

#### `<article>`

Indica un contenido que tiene sentido por sí mismo.

Algunos ejemplos:

- Una entrada de un blog
- Una noticia
- Un mensaje de un foro
- La descripción de un producto

Dentro suele haber un título (`<h2>` o `<h3>`), texto, imágenes o vídeos.

---

#### `<aside>`

Muestra información que complementa el contenido principal.

Por ejemplo:

- Enlaces de interés
- Anuncios
- Encuestas
- Últimas noticias

Normalmente se coloca a un lado.

---

#### `<footer>`

Indica el final de la página o de una sección.

En él suele aparecer:

- El copyright
- El contacto
- Enlaces a redes sociales
- Avisos legales

---

### Etiquetas para organizar el contenido

- `<hgroup>`: agrupa varios títulos relacionados entre sí.
- `<h1>` - `<h6>`: establecen la jerarquía de los títulos.
- `<div>`: etiqueta genérica para agrupar contenido de bloque.
- `<span>`: etiqueta genérica para agrupar contenido en línea.

#### `<div>`

Se usa para agrupar bloques de contenido.

No tiene significado semántico; se usa sobre todo para organización y para aplicar estilos.

#### `<span>`

Se usa para dar un estilo o comportamiento especial a un pequeño fragmento de texto.

No genera salto de línea.

```html
<p>
    Hau testu normala da eta
    <span class="gorria">hau gorriz agertuko da</span>.
</p>
```

### Contenido complementario

- `<address>`: indica información de contacto.
- `<details>` y `<summary>`: crean información desplegable.
- `<hr>`: indica una separación temática entre contenidos.

![HTML5 etiketa semantikoen egitura](../../images/html_semantic_elements.png)

!!! tip "Recomendaciones"

    ✅ Usa siempre la etiqueta semántica adecuada.

    ❌ No hagas toda la web mediante etiquetas `<div>`.

    Usar etiquetas semánticas tiene las siguientes ventajas:

    - Código más limpio y comprensible.
    - Mejor accesibilidad.
    - Mejor SEO.
    - Mantenimiento más sencillo.

!!! note "Idea principal"
    Las etiquetas semánticas de HTML5 dan **significado** al contenido, no solo estructura.


## Contenido incrustado y multimedia

HTML5 permite incrustar directamente en la página web **audio, vídeo y otros contenidos multimedia**, sin usar plugins.

Además, estas etiquetas usan el **reproductor nativo** del navegador, y ofrecen controles sin necesidad de JavaScript adicional (reproducir, pausar, volumen, barra de tiempo...).

---

### Contenidos incrustados genéricos (`<object>`)

La etiqueta `<object>` se usa para incrustar distintos tipos de recursos externos (imágenes, PDF, documentos...).

```html
<object data="irudia.png" width="550" height="150">
    Irudia ezin izan da kargatu.
</object>
```

---

### Audio (`<audio>`)

La etiqueta `<audio>` se usa para incrustar archivos de audio en la página web.

```html
<audio controls src="media/abestia.mp3">
    Zure nabigatzaileak ez du audio txertatua onartzen.
</audio>
```

#### Formatos de audio principales

| Formato | Explicación |
|----------|----------|
| **MP3** | El formato más utilizado. Lo admiten todos los navegadores. |
| **WAV** | De alta calidad, pero los archivos son muy pesados. Se usa para audios cortos. |
| **OGG** | Formato libre. Ofrece buena calidad y una compresión alta. |

### Ofrecer varios formatos de audio

No todos los navegadores admiten los mismos formatos. Por eso, es recomendable usar la etiqueta `<source>`.

```html
<audio controls>

    <source src="media/abestia.mp3" type="audio/mpeg">
    <source src="media/abestia.ogg" type="audio/ogg">

    Zure nabigatzaileak ez du audioa onartzen.

</audio>
```

El navegador usará el **primer formato que admita**.

---

### Vídeo (`<video>`)

La etiqueta `<video>` se usa para incrustar vídeos directamente en la página web.

```html
<video controls src="videos/filma.mp4">
    Zure nabigatzaileak ez du bideo txertatua onartzen.
</video>
```

#### Formatos de vídeo principales

| Formato | Explicación |
|----------|----------|
| **MP4** | El formato más utilizado. También lo recomienda YouTube. |
| **WebM** | Formato libre optimizado para la web. |
| **OGG / OGV** | Formato libre, usado en algunos navegadores. |

### Ofrecer varios formatos de vídeo

```html
<video controls width="640">

    <source src="videos/filma.mp4" type="video/mp4">
    <source src="videos/filma.webm" type="video/webm">

    Zure nabigatzaileak ez du bideoa onartzen.

</video>
```

El navegador elegirá automáticamente el más compatible.

---

### Atributos más usados de las etiquetas `<audio>` y `<video>`

| Atributo | Explicación |
|-----------|----------|
| `controls` | Muestra los controles del reproductor. |
| `autoplay` | Empieza automáticamente al abrir la página. |
| `loop` | Vuelve a empezar al terminar. |
| `muted` | Se carga silenciado al principio. |
| `preload` | Indica cuándo debe cargarse el contenido multimedia. |
| `width` | Establece la anchura del vídeo. (solo `<video>`) |
| `height` | Establece la altura del vídeo. (solo `<video>`) |
| `poster` | Imagen que se muestra antes de que empiece el vídeo. (solo `<video>`) |

---

### Incrustar vídeos externos (`<iframe>`)

Los vídeos de YouTube, Vimeo o plataformas similares **no se incrustan usando la etiqueta `<video>`**.

En estos casos se usa `<iframe>`.

```html
<iframe
    src="https://www.youtube.com/embed/XXXXXXXX"
    width="560"
    height="315"
    allowfullscreen>
</iframe>
```

Este código se obtiene en YouTube haciendo clic en **Compartir → Insertar (Embed)**.

---

!!! tip "Recomendaciones"

    ✅ Usa siempre **MP3** para los audios y **MP4** para los vídeos, porque ofrecen la mayor compatibilidad.

    ✅ Usa la etiqueta `<source>` si quieres ofrecer más de un formato.

    ✅ Añade siempre un texto alternativo (`Zure nabigatzaileak...`) para los navegadores que no admitan multimedia.

    ✅ Respeta los **derechos de autor** de los archivos multimedia. No todo lo que se encuentra en Internet **se puede usar libremente**; comprueba siempre la licencia (por ejemplo, Creative Commons).

!!! example "Ariketa 9"
    Este ejercicio nos servirá para repasar todo lo anterior: [Ariketa 9](https://docs.google.com/document/d/11uI0NrI0OdJXkDNqBq0T9JxlLd77c4mzLti7Q4yVel4/edit?usp=sharing){: target="_blank" rel="noopener" } 


## Formularios

Los formularios se usan para recoger información del usuario (registros, inicios de sesión, formularios de contacto, encuestas...).

Dentro de un formulario puede haber varios controles: cajas de texto, contraseñas, opciones, botones, listas...

---

### Etiqueta `<form>`

Todos los formularios se definen dentro de la etiqueta `<form>`.

```html
<form action="/bidali" method="post">

    <!-- formularioaren kontrolak -->

</form>
```

#### Atributos principales

| Atributo | Explicación |
|-----------|----------|
| `action` | Dirección a la que se enviarán los datos. |
| `method` | Método para enviar los datos (`get` o `post`). |

!!! note "Nota" 
    Por ahora no usaremos ningún servidor; por tanto, el atributo `action` no tendrá una función real.
    Pero en este atributo indicaremos cuál será el archivo que recibirá los elementos del formulario

---

### `<label>`

Se usa para dar nombre a un control de un formulario.

El atributo `for` debe coincidir con el atributo `id` del control.

```html
<label for="izena">Izena:</label>
<input type="text" id="izena" name="izena">
```

--- 

### `id` y `name`

Ambos atributos son muy importantes, pero **no hacen lo mismo**. Hay que tener claro cuál es la diferencia entre ellos.

| Atributo | ¿Para qué se usa? |
|-----------|--------------------------|
| `id` | Para identificar el elemento de forma única. Se vincula con la etiqueta `<label>`. |
| `name` | Será el nombre del dato al enviar el formulario. |

Ejemplo:

```html
<label for="izena">Izena</label>

<input
    type="text"
    id="izena"
    name="izena">
```

En este caso:

- `for="izena"` → se vincula con el atributo `id="izena"`.
- `name="izena"` → será el nombre del dato que se enviará al servidor.

---

### Campo de texto (`text`)

Se usa para escribir textos cortos.

```html
<label for="id_izena">Erabiltzailea</label>

<input type="text" id="id_izena" name="izena" value="Testu lehenetsia" size="20">
```

#### Atributos más usados

| Atributo | Explicación |
|-----------|----------|
| `name` | Nombre del dato. |
| `value` | Valor inicial. |
| `placeholder` | Texto de ayuda. |
| `size` | Anchura de la caja. |
| `maxlength` | Número máximo de caracteres. |
| `required` | Campo obligatorio. |

Ejemplo:

```html
<input
    type="text"
    placeholder="Idatzi zure izena"
    required>
```

---

### Contraseña (`password`)

Oculta los caracteres escritos.

```html
<input type="password" name="pwd">
```

---

### Email (`email`)

Se usa para introducir una dirección de correo electrónico.

El navegador comprueba automáticamente que tenga el formato adecuado.

```html
<input type="email" name="email">
```

---

### Otros tipos de `input` útiles

| Tipo | Uso |
|------|-----------|
| `number` | Para introducir números. |
| `date` | Para elegir una fecha. |
| `color` | Selector de color. |
| `file` | Para subir archivos. |
| `range` | Para elegir un valor mediante una barra. |

Ejemplo:

```html
<input type="date">

<input type="number" min="0" max="100">

<input type="color">

<input type="file">

<input type="range" min="0" max="10">
```

---

### Botones de opción (`radio`)

Se usan para seleccionar **una única** opción.

Para que todos los botones de radio pertenezcan al mismo grupo, deben tener el mismo `name`.

```html
<input type="radio" name="generoa" value="gizona"> Gizona

<input type="radio" name="generoa" value="emakumea"> Emakumea
```

![Radio buttom adibidea](../../images/form_radio.png)

Opción por defecto:

```html
<input type="radio" name="generoa" checked> Gizona
```
![Radio buttom checked](../../images/form_radio_checked.png)

---

### Casillas de verificación (`checkbox`)

Se usan para seleccionar **una o más** opciones.

```html
<input type="checkbox" name="ibilgailua[]" value="autoa"> Autoa

<input type="checkbox" name="ibilgailua[]" value="motoa"> Motoa
```

![Checkbox adibidea](../../images/form_checkbox.png)

Opción por defecto:

```html
<input type="checkbox" name="ibilgailua[]" value="motoa" checked> Motoa
```

![Radio buttom checekc](../../images/form_checkbox_checked.png)

---

### Lista desplegable (`select`)

Muestra una lista de opciones.

```html
<select name="probintzia">

    <option value="AB">Araba</option>

    <option value="BI">Bizkaia</option>

    <option value="GI" selected>Gipuzkoa</option>

</select>
```

![Select adibidea](../../images/form_select.png)

#### Atributos disponibles

| Atributo | Explicación |
|-----------|----------|
| `selected` | Opción por defecto. |
| `multiple` | Permite seleccionar más de una opción. |

```html
<select multiple>

    <option>Euskara</option>

    <option>Gaztelania</option>

    <option>Ingelesa</option>

</select>
```

---

### Área de texto (`textarea`)

Se usa para escribir textos de varias líneas.

```html
<textarea rows="6" cols="40">

Hemen idatzi zure mezua...

</textarea>
```

---

### Sugerencias de datos (`datalist`)

Muestra sugerencias mientras el usuario escribe.

```html
<input
    type="text"
    list="hizkuntzak">

<datalist id="hizkuntzak">

    <option value="Euskara">

    <option value="Gaztelania">

    <option value="Ingelesa">

</datalist>
```

El usuario también puede escribir otro valor distinto.

![Datalist adibidea](../../images/form_datalist.png)

---

### Agrupación de controles (`fieldset` y `legend`)

Se usan para organizar los distintos apartados de un formulario.

```html
<fieldset>

    <legend>Datu pertsonalak</legend>

    <label>Izena:</label>
    <input type="text">

    <label>Abizenak:</label>
    <input type="text">

</fieldset>
```

---

### Botones

En los formularios pueden usarse varios tipos de botones.

```html
<button type="submit">Bidali</button>

<button type="reset">Garbitu</button>

<button type="button">Beste ekintza</button>
```

| Tipo | Explicación |
|-------|----------|
| `submit` | Envía el formulario. |
| `reset` | Devuelve todos los valores a su estado inicial. |
| `button` | Se usa para controlarlo mediante JavaScript. |

---
### Validación HTML5

HTML5 realiza algunas validaciones automáticas sin usar JavaScript.

Por ejemplo:

- `required`
- `email`
- `min`
- `max`
- `maxlength`
- `pattern`

```html
<input
    type="email"
    required>

<input
    type="number"
    min="0"
    max="100">
```

Gracias a esto, el usuario no podrá enviar datos incorrectos.

---

### `GET` y `POST`

Un formulario tiene dos maneras principales de enviar datos.

| GET | POST |
|-----|------|
| Los datos se envían en la URL. | Los datos se envían en el cuerpo de la petición. |
| Se usa para búsquedas. | Se usa en la mayoría de logins, registros y formularios. |
| No es adecuado para contraseñas. | Es más seguro. |

Ejemplo:

```html
<form method="get">
```

```html
<form method="post">
```

---

### Ejemplo completo de un formulario

```html
<form action="/bidali" method="post">

    <fieldset>

        <legend>Erregistroa</legend>

        <label for="izena">Izena</label>
        <input
            type="text"
            id="izena"
            name="izena"
            required>

        <br><br>

        <label for="email">Emaila</label>
        <input
            type="email"
            id="email"
            name="email">

        <br><br>

        <label>Generoa</label>

        <input
            type="radio"
            name="generoa"
            value="gizona">

        Gizona

        <input
            type="radio"
            name="generoa"
            value="emakumea">

        Emakumea

        <br><br>

        <label>Hobien dituzun hizkuntzak</label>

        <input
            type="checkbox"
            name="hizkuntzak[]"
            value="eu">

        Euskara

        <input
            type="checkbox"
            name="hizkuntzak[]"
            value="es">

        Gaztelania

        <br><br>

        <label for="oharrak">Oharrak</label>

        <textarea
            id="oharrak"
            rows="5"
            cols="40"></textarea>

        <br><br>

        <button type="submit">
            Bidali
        </button>

    </fieldset>

</form>
```

![Formulario adibidea](../../images/form_example.png)


!!! tip "Recomendaciones"

    ✅ Usa siempre la etiqueta `<label>`.

    ✅ Todos los controles deben tener el atributo `name`.

    ✅ Usa `required` en los campos obligatorios.

    ✅ Los botones de radio deben tener el mismo `name`.

    ✅ Usa `fieldset` para organizar formularios largos.



## Enlaces útiles

- [MDN: HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)